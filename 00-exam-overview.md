# Exam Overview

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

## Exam facts

| Item | Value |
|---|---|
| Exam code | AZ-900 |
| Certification | Microsoft Certified: Azure Fundamentals |
| Skills measured | Outline dated July 20, 2026. Microsoft revises the outline periodically; check the AZ-900 study guide (https://aka.ms/AZ900-StudyGuide) before booking. |
| Questions | Microsoft does not publish the count for this exam and says it can change (it gives 40–60 as typical across its certification exams). Plan for roughly 40; that is the number the practice site uses. |
| Time | 45 minutes of exam time (allow about 65 minutes of seat time for instructions, the candidate agreement, and comments) |
| Scoring | Scaled 1–1000 |
| Passing score | 700 |
| Delivery | Proctored, through Pearson VUE (test center or online) or through Certiport for students and educators |
| Languages | English, Japanese, Chinese (Simplified), Chinese (Traditional), Korean, Spanish, German, French, Italian, Portuguese (Brazil), Russian, Indonesian, Arabic |
| Price | Depends on the country or region in which the exam is proctored; see the exam page |
| Retake | Wait 24 hours after a first failed attempt, then 14 days between later attempts; at most 5 attempts in 12 months; a passed exam cannot be retaken |
| Expiry | Fundamentals certifications do not expire and have no renewal assessment |
| Open book | No. Microsoft Learn access during the exam exists only on role-based exams, not fundamentals exams |
| Recommended experience | General IT background; no Azure experience is required |

## Domains and weights

| # | Domain | Weight | Objectives |
|---|---|---|---|
| 1 | Describe cloud concepts | 25–30% | 1.1 Describe cloud computing; 1.2 Describe the benefits of using cloud services; 1.3 Describe cloud service types |
| 2 | Describe Azure architecture and services | 35–40% | 2.1 Core architectural components; 2.2 Compute and networking; 2.3 Storage; 2.4 Identity, access, and security |
| 3 | Describe Azure management and governance | 30–35% | 3.1 Cost management; 3.2 Governance and compliance; 3.3 Managing and deploying resources; 3.4 Monitoring |

Microsoft does not number its skill groups. The 1.1–3.4 numbering is this kit's own and is used the same way in the chapters and on the practice site.

Domain 2 is the largest, but no domain is small: Domain 1 alone is more than a quarter of the exam, and it is the easiest place to pick up points.

## Question types

Microsoft does not announce which formats a given exam uses, but the exam sandbox shows the full set, and these are the ones candidates meet on AZ-900:

| Type | What it looks like | How it is scored |
|---|---|---|
| Multiple choice, one answer | Short scenario or direct question with four options | One point |
| Multiple choice, several answers | The stem states how many to select | Usually one point per correct selection |
| Yes/No statement grid | Three or so independent statements; mark each Yes or No | One point per statement |
| Drag and drop | Match services or terms to descriptions; some items may be left over | One point per correct match |
| Dropdown sentence completion | A sentence with one or more dropdown lists | One point per dropdown |

- There are no labs or case studies to plan for on a 45-minute fundamentals exam; labs are a feature of some role-based exams.
- Multi-part items give **partial credit**: each correct component earns its point.
- Microsoft exams can include a short series of items that cannot be revisited once you move on. If yours does, the exam warns you on screen first; answer carefully and continue.

## Question-style patterns

| Stem wording | How to read it |
|---|---|
| "What should you use?" / "Which service should you recommend?" | A requirement-to-service lookup. Find the one or two requirement words that decide it (see the service picker, sheet 90). |
| "Which cloud model…" / "Which cloud service type…" | Public, private, or hybrid; IaaS, PaaS, or SaaS. Look for who manages what. |
| "Which benefit of cloud computing does this describe?" | Match the scenario to one term: high availability, scalability, elasticity, reliability, predictability, security, governance, manageability. |
| "Select Yes if the statement is true" | Each statement stands alone. Absolutes ("always", "only", "all", "cannot") deserve a second look. |
| "To complete the sentence, select the appropriate option" | A definition recall; read the full sentence with each option in place. |
| "minimize cost" / "minimize administrative effort" | A tiebreaker. Cost points to the cheaper tier or commitment; effort points to PaaS, SaaS, or the built-in tool. |

- Microsoft does not capitalize qualifiers such as best or most; read every word of the stem.
- Scenario stems usually hide the answer in one clue: "without managing servers", "private connection that does not use the internet", "accessed rarely but must be available immediately", "prevent accidental deletion", "across multiple subscriptions".
- Old product names can still appear in parentheses. Know that Microsoft Entra ID was formerly Azure Active Directory.
- The exam tests what a service is for, not how to configure it. If an answer depends on a setting or a command, it is probably a distractor.

## Time management

- 45 minutes for roughly 40 questions is about one minute each. Most recall items take 20–30 seconds, which banks time for grids and matching.
- Do not stall: if an item passes 90 seconds, pick the best remaining option, mark it for review, and move on.
- Check the clock at the halfway mark (about 22 minutes); you should be past question 20.
- A break is allowed, but the clock keeps running and you cannot return to questions seen before the break. On a 45-minute exam, do not take one.
- There is no penalty for guessing. Answer every question, including every row of a grid.

## Elimination tactics

1. Remove answers from the wrong family (a monitoring tool offered for a governance requirement, a storage option for a compute need).
2. Remove retired or renamed products offered as the current choice.
3. Remove answers that break a stated constraint (cost, no internet exposure, no server management).
4. Between two survivors, find the scope or the verb: "enforce" is Azure Policy, "grant access" is Azure RBAC, "prevent deletion" is a resource lock, "organize for billing" is a tag.
5. Personalized versus general: recommendations for your resources are Azure Advisor, incidents affecting your resources are Azure Service Health, the global picture is the Azure Status page.
6. When unsure on a "minimize administrative effort" question, prefer the most managed option that still meets the requirement.

## Scoring and the score report

- Results appear within minutes of finishing; the score reaches your Microsoft Learn profile within 24 hours.
- The report gives an overall scaled score, pass or fail, and a bar chart of performance per skill area. It does not give a score per section or tell you which questions you missed.
- 700 is a scaled score, not 70% of the questions. The pass line reflects question difficulty, so the percent needed varies by form.
- Some questions may be unscored trial items. You cannot tell which, so treat every question as scored.

## Logistics

| Topic | Details |
|---|---|
| Scheduling | From the certification page on Microsoft Learn, which hands off to Pearson VUE. Students and educators can schedule through Certiport. |
| Account | Register with a personal Microsoft account. Microsoft warns that records tied to a work or school account can be lost when you leave the organization. |
| Options | A Pearson VUE test center, or online proctoring (OnVUE) at home |
| ID | Valid government-issued photo ID; the name must match your registration. Check the current Pearson VUE requirements for your country. |
| Online | Quiet room, clear desk, webcam, microphone, stable connection; run the system test beforehand; no notes, phones, or second monitors |
| Rescheduling | Reschedule or cancel well ahead of the appointment (check the current deadline when you book) to avoid losing the fee |
| Accommodations | Extra time and assistive devices must be requested and approved before you register |
| Discounts | Student pricing, Microsoft Virtual Training Day vouchers, and occasional retake offers; availability varies |

## Microsoft's free practice tools

- **Practice assessment:** free on the AZ-900 certification page on Microsoft Learn. It shows the style, wording, and difficulty of exam questions with explanations and links. Its questions are not the live exam's questions.
- **Exam sandbox:** https://aka.ms/examdemo. It is the real exam interface with sample items of each question type, the review screen, and the mark-for-review control. Spend ten minutes there before exam day so the interface costs you nothing.
- **Microsoft Learn path:** the free "Azure Fundamentals" learning paths follow the outline unit by unit and are the source of truth when this guide and another source disagree.

## How this kit's practice site maps to the exam

| Site mode | What it does | Use it for |
|---|---|---|
| Final exam | 40 items on a 45:00 clock: 4 interactive items first, then 36 multiple-choice questions split 10 / 14 / 12 across domains 1, 2, and 3. No feedback until you submit. Ends with an estimated scaled score against a pass line of 700. | Timing practice and a readiness check |
| Module quiz | 10, 25, 50, or all questions from one domain, untimed, with up to 2 of that domain's interactive items if you want them. Practice mode shows the explanation after each answer; exam mode holds feedback to the end. | Learning a domain right after reading its chapter |
| Missed drill | Only the questions whose most recent answer was wrong; a question leaves the list when you answer it correctly | Closing gaps before the next final |

- The site's interactive items stand in for the exam's formats: Yes/No grids and drag-and-drop matching (match), build lists (order), and dropdown tables (config).
- The estimated scaled score is simply your percentage of points multiplied by 1000 (75% correct shows as 750), with the pass line at 700. It is a straight percentage estimate, not Microsoft's scaling; treat a steady 800 or more on fresh finals as ready.
- Each domain card carries a readiness badge. It turns green ("Ready") after three module quiz attempts in a row for that domain at 80% or higher.

## Study schedules

### 1-week plan (about 2–3 hours per day)

| Day | Focus | Tasks |
|---|---|---|
| 1 | Overview and Domain 1 | Read 00 and 01; Domain 1 module quiz; try the exam sandbox |
| 2 | Domain 2, first half | Read 2.1 and 2.2; quiz; start the acronym list (91) |
| 3 | Domain 2, second half | Read 2.3 and 2.4; quiz; missed drill |
| 4 | Domain 3 | Read 03; quiz; missed drill |
| 5 | Reference sheets | Read 90 and 92; skim 91; first timed final |
| 6 | Practice | Microsoft practice assessment; second final; drill every miss |
| 7 | Light review | "Most-tested distinctions" in each chapter, sheet 90, rest |

### 2-week plan (about 1 hour per day)

| Days | Focus | Tasks |
|---|---|---|
| 1–2 | Overview and Domain 1 | Read 00 and 01; module quiz until 85% or better |
| 3–4 | Domain 2: 2.1 and 2.2 | Read; quiz; exam sandbox |
| 5–6 | Domain 2: 2.3 and 2.4 | Read; quiz; missed drill |
| 7–9 | Domain 3 | Read 03 over two days; quiz; missed drill |
| 10 | Reference sheets | 90, 91, 92 |
| 11–12 | Finals | One timed final per day; drill misses; reread weak objectives |
| 13 | Microsoft practice assessment | Compare its weak areas with the site's results |
| 14 | Light review | Sheets 90 and 92, "Most-tested distinctions", rest |
