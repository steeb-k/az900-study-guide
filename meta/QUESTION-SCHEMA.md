# Question bank schema (authoritative)

All bank files are plain browser scripts (no modules, no JSON files). They are loaded by `index.html` **after**
`data/objectives.js` and **before** the app scripts.

## MCQ files: `data/domain1.js` … `data/domain3.js`
```js
// data/domain2.js
window.AZ_BANK = window.AZ_BANK || [];
window.AZ_BANK.push(
  {
    id: "d2-001",                 // "d<domain>-<3 digit>", unique across all files, sequential within file
    domain: 2,                    // 1..3
    objective: "2.3",             // must exist in window.AZ_OBJECTIVES[domain].objectives
    type: "single",               // "single" | "multi"
    question: "A company must keep seven years of invoices that are almost never read. Retrieval within several hours is acceptable. Which blob access tier should the company use to minimize storage cost?",
    options: [                    // 4 options normally; 5–6 allowed for multi. Plain strings, no "A." prefixes.
      "Hot",
      "Cool",
      "Cold",
      "Archive"
    ],
    answer: [3],                  // array of 0-based indexes into options. single → exactly 1; multi → 2 or 3
    explanation: "Archive has the lowest storage cost and suits data that is rarely read and can wait hours for rehydration. Hot, cool and cold are online tiers that cost more to store.",
    difficulty: 2,                // 1 easy recall, 2 scenario, 3 close distinction
    tags: ["access tiers", "archive"] // 1–4 short keywords, used for drill filtering and QA
  },
  // ...
);
```
Rules for every question (the validator, `node tests/validate-bank.js`, enforces the mechanical ones):
- **Style = Microsoft's AZ-900.** A short scenario and then "What should you use?", "Which Azure service should you recommend?",
  "Which cloud model …?", "Which benefit of cloud computing does this describe?", plus direct recall and sentence completion
  ("Which term completes the sentence: …"). Microsoft does not capitalize BEST/MOST; neither does the bank. Target mix per domain:
  ~35% difficulty 1, ~50% difficulty 2, ~15% difficulty 3 (the validator warns above 45% difficulty 1). About 12–15% of questions
  `multi` ("Choose TWO." / "Choose THREE." must appear at the end of the stem, exactly in that form).
- **Original wording only.** Nothing copied from Microsoft's practice assessment, from an exam, or from a dump site.
- Stay inside the current skills outline (see `data/objectives.js` and the chapters). Use current product names (Microsoft Entra ID,
  Microsoft Defender for Cloud, Microsoft Purview). Do not test retired or removed items (TCO calculator, Azure Blueprints), prices
  in currency, or preview features.
- Distractors must be plausible items from the same family (other redundancy options, other governance tools; not obviously wrong,
  never jokes). No "All of the above", no "None of the above", no "Both A and B".
- Spread questions across every bullet of every objective; **minimum 3 per objective**.
- Explanation: 1–3 sentences, states why the right answer is right AND briefly why the key distractors are wrong. ≥ 60 chars.
- One unambiguous correct answer (or set). If a question could be argued two ways, rewrite it.
- No duplicated stems or near-duplicates within a domain. Vary the scenario organization (retailer, hospital, startup, school, bank).
- Every question must be answerable from the matching chapter of the guide.
- Option order inside the file does not matter (the app shuffles), but keep `answer` indexes correct.
- Escape double quotes inside strings or use single-quoted JS strings. No trailing-comma problems; the file must parse.

## Interactive items: `data/pbq.js`
The real AZ-900 has no labs, but it does have yes/no statement grids, drag-and-drop matching and dropdown completion. The site
serves those with the engine the Security+ kit uses for performance-based questions, which is why the code says `PBQ`.
```js
window.AZ_PBQ = window.AZ_PBQ || [];
window.AZ_PBQ.push(
  // type "match": each left item gets one choice from a shared list of right-hand options (dropdown). Right options may be
  // reused across left items unless `unique: true`. Score = correct left items / total left items.
  // Yes/No statement grid = match with right ["Yes", "No"] and no `unique`.
  {
    id: "pbq-001", domain: 1, objective: "1.1", type: "match",
    title: "Shared responsibility",
    instructions: "For each statement, select Yes if the statement is true. Otherwise, select No.",
    left: [
      "In an IaaS deployment, the customer is responsible for patching the guest operating system.",
      "In a SaaS deployment, the cloud provider is responsible for the accounts and identities the customer creates.",
      "In every cloud service type, the cloud provider is responsible for the physical datacenter."
    ],
    right: ["Yes", "No"],
    answer: [0, 1, 0],                 // index into `right` for each `left` item
    explanation: "The customer patches the guest OS in IaaS. Accounts and identities are always the customer's. Physical hosts, network and datacenter are always the provider's."
  },
  // Drag-and-drop matching = match with `unique: true` and one or two extra distractors in `right`.
  {
    id: "pbq-002", domain: 2, objective: "2.3", type: "match",
    title: "Match the storage service",
    instructions: "Match each requirement to the Azure Storage service that meets it.",
    left: ["A file share that Windows and Linux VMs mount over SMB", "Unstructured images and video for a website", "Messages that decouple two application components"],
    right: ["Azure Files", "Azure Blobs", "Azure Queues", "Azure Tables", "Azure Disks"],
    answer: [0, 1, 2],
    unique: true,
    explanation: "Files provides managed SMB/NFS shares; Blobs hold unstructured objects; Queues store messages between components."
  },
  // type "order": arrange items into the correct sequence (Up/Down buttons). Score = items in the correct position / total.
  {
    id: "pbq-003", domain: 2, objective: "2.1", type: "order",
    title: "Management hierarchy",
    instructions: "Arrange the levels of the Azure management hierarchy from the broadest scope to the narrowest.",
    items: ["Resource groups", "Management groups", "Resources", "Subscriptions"],
    answer: [1, 3, 0, 2],               // indexes of `items` in correct order
    explanation: "Management groups contain subscriptions, subscriptions contain resource groups, and resource groups contain resources."
  },
  // type "config": a table where each row has one or more cells to fill from per-column dropdowns. Score = correct cells / total cells.
  {
    id: "pbq-004", domain: 3, objective: "3.2", type: "config",
    title: "Choose the governance tool",
    instructions: "For each requirement, select the tool to use and the narrowest scope that meets it.",
    columns: [
      { key: "tool",  label: "Tool",  choices: ["Azure Policy", "Resource lock", "Azure RBAC", "Tag"] },
      { key: "scope", label: "Scope", choices: ["Management group", "Subscription", "Resource group", "Resource"] }
    ],
    rows: [
      { label: "Only allow resources in two regions, in every subscription of the company", fixed: { }, answer: { tool: "Azure Policy", scope: "Management group" } },
      { label: "Stop anyone from deleting one production database", fixed: { scope: "Resource" }, answer: { tool: "Resource lock" } }
    ],
    // `fixed` cells are shown read-only and not scored; `answer` lists only the scorable cells for that row.
    explanation: "Policy at the management group reaches every subscription under it. A Delete lock on the resource blocks deletion even for Owners."
  }
);
```
Rules: at least 18 items total and at least 3 per domain (validator limits), a mix of the three types. Each solvable in 1–2 minutes;
statements must be unambiguous. Every item has an `explanation`. For `config`, every row's `answer` keys must be a subset of column
keys and every answer value must be in that column's `choices`. For `order`, `answer` must be a permutation of all item indexes.
For `match`, `answer.length === left.length`, each value indexes `right`, and `right` has at least 2 options.

## `data/objectives.js` (shape is fixed)
```js
window.AZ_OBJECTIVES = {
  1: { name: "Cloud Concepts", weight: 0.275, objectives: { "1.1": "Describe cloud computing", ... } },
  ...
};
window.AZ_EXAM = { totalQuestions: 40, pbqCount: 4, mcqPerDomain: {1:10, 2:14, 3:12}, minutes: 45, passScaled: 700, scaledMin: 0, scaledMax: 1000 };
```
