# Microsoft Azure Fundamentals AZ-900 — Complete Study Guide

> **⚠ AI-generated, not yet vetted.** This guide was written by AI against Microsoft's AZ-900 skills outline (July 20, 2026) and has **not yet been reviewed by a human for accuracy**. Cross-check anything surprising against Microsoft Learn before relying on it.

## Contents

- [Exam Overview](#exam-overview)
- [Domain 1 — Cloud Concepts (25–30%)](#domain-1--cloud-concepts-2530)
- [Domain 2 — Azure Architecture and Services (35–40%)](#domain-2--azure-architecture-and-services-3540)
- [Domain 3 — Azure Management and Governance (30–35%)](#domain-3--azure-management-and-governance-3035)
- [Service Picker](#service-picker)
- [Acronyms](#acronyms)
- [Numbers and Comparisons](#numbers-and-comparisons)

---

## Exam Overview

### Exam facts

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

### Domains and weights

| # | Domain | Weight | Objectives |
|---|---|---|---|
| 1 | Describe cloud concepts | 25–30% | 1.1 Describe cloud computing; 1.2 Describe the benefits of using cloud services; 1.3 Describe cloud service types |
| 2 | Describe Azure architecture and services | 35–40% | 2.1 Core architectural components; 2.2 Compute and networking; 2.3 Storage; 2.4 Identity, access, and security |
| 3 | Describe Azure management and governance | 30–35% | 3.1 Cost management; 3.2 Governance and compliance; 3.3 Managing and deploying resources; 3.4 Monitoring |

Microsoft does not number its skill groups. The 1.1–3.4 numbering is this kit's own and is used the same way in the chapters and on the practice site.

Domain 2 is the largest, but no domain is small: Domain 1 alone is more than a quarter of the exam, and it is the easiest place to pick up points.

### Question types

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

### Question-style patterns

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

### Time management

- 45 minutes for roughly 40 questions is about one minute each. Most recall items take 20–30 seconds, which banks time for grids and matching.
- Do not stall: if an item passes 90 seconds, pick the best remaining option, mark it for review, and move on.
- Check the clock at the halfway mark (about 22 minutes); you should be past question 20.
- A break is allowed, but the clock keeps running and you cannot return to questions seen before the break. On a 45-minute exam, do not take one.
- There is no penalty for guessing. Answer every question, including every row of a grid.

### Elimination tactics

1. Remove answers from the wrong family (a monitoring tool offered for a governance requirement, a storage option for a compute need).
2. Remove retired or renamed products offered as the current choice.
3. Remove answers that break a stated constraint (cost, no internet exposure, no server management).
4. Between two survivors, find the scope or the verb: "enforce" is Azure Policy, "grant access" is Azure RBAC, "prevent deletion" is a resource lock, "organize for billing" is a tag.
5. Personalized versus general: recommendations for your resources are Azure Advisor, incidents affecting your resources are Azure Service Health, the global picture is the Azure Status page.
6. When unsure on a "minimize administrative effort" question, prefer the most managed option that still meets the requirement.

### Scoring and the score report

- Results appear within minutes of finishing; the score reaches your Microsoft Learn profile within 24 hours.
- The report gives an overall scaled score, pass or fail, and a bar chart of performance per skill area. It does not give a score per section or tell you which questions you missed.
- 700 is a scaled score, not 70% of the questions. The pass line reflects question difficulty, so the percent needed varies by form.
- Some questions may be unscored trial items. You cannot tell which, so treat every question as scored.

### Logistics

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

### Microsoft's free practice tools

- **Practice assessment:** free on the AZ-900 certification page on Microsoft Learn. It shows the style, wording, and difficulty of exam questions with explanations and links. Its questions are not the live exam's questions.
- **Exam sandbox:** https://aka.ms/examdemo. It is the real exam interface with sample items of each question type, the review screen, and the mark-for-review control. Spend ten minutes there before exam day so the interface costs you nothing.
- **Microsoft Learn path:** the free "Azure Fundamentals" learning paths follow the outline unit by unit and are the source of truth when this guide and another source disagree.

### How this kit's practice site maps to the exam

| Site mode | What it does | Use it for |
|---|---|---|
| Final exam | 40 items on a 45:00 clock: 4 interactive items first, then 36 multiple-choice questions split 10 / 14 / 12 across domains 1, 2, and 3. No feedback until you submit. Ends with an estimated scaled score against a pass line of 700. | Timing practice and a readiness check |
| Module quiz | 10, 25, 50, or all questions from one domain, untimed, with up to 2 of that domain's interactive items if you want them. Practice mode shows the explanation after each answer; exam mode holds feedback to the end. | Learning a domain right after reading its chapter |
| Missed drill | Only the questions whose most recent answer was wrong; a question leaves the list when you answer it correctly | Closing gaps before the next final |

- The site's interactive items stand in for the exam's formats: Yes/No grids and drag-and-drop matching (match), build lists (order), and dropdown tables (config).
- The estimated scaled score is simply your percentage of points multiplied by 1000 (75% correct shows as 750), with the pass line at 700. It is a straight percentage estimate, not Microsoft's scaling; treat a steady 800 or more on fresh finals as ready.
- Each domain card carries a readiness badge. It turns green ("Ready") after three module quiz attempts in a row for that domain at 80% or higher.

### Study schedules

#### 1-week plan (about 2–3 hours per day)

| Day | Focus | Tasks |
|---|---|---|
| 1 | Overview and Domain 1 | Read 00 and 01; Domain 1 module quiz; try the exam sandbox |
| 2 | Domain 2, first half | Read 2.1 and 2.2; quiz; start the acronym list (91) |
| 3 | Domain 2, second half | Read 2.3 and 2.4; quiz; missed drill |
| 4 | Domain 3 | Read 03; quiz; missed drill |
| 5 | Reference sheets | Read 90 and 92; skim 91; first timed final |
| 6 | Practice | Microsoft practice assessment; second final; drill every miss |
| 7 | Light review | "Most-tested distinctions" in each chapter, sheet 90, rest |

#### 2-week plan (about 1 hour per day)

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

---

## Domain 1 — Cloud Concepts (25–30%)

Objectives 1.1–1.3. Almost no Azure product knowledge is needed here; the questions test vocabulary. Most of them describe a situation and ask which cloud model, service type, or benefit it illustrates.

---

### 1.1 Describe cloud computing

#### Define cloud computing

**Cloud computing** is the delivery of computing services over the internet: virtual machines, storage, databases, and networking, plus newer services such as Internet of Things (IoT), machine learning, and AI. You rent capacity from a provider's datacenters instead of buying and running hardware, you can add or remove capacity in minutes, and you are billed for what you use.

Compared with a traditional datacenter, the cloud removes the need to buy hardware, provide power and cooling, secure a building, or guess capacity years ahead.

#### Shared responsibility model

Security and operations are split between the cloud provider and the customer. The split depends on the service type (1.3): the more the provider manages, the less the customer is responsible for.

| Responsibility | On-premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Information and data | Customer | Customer | Customer | Customer |
| Devices (phones, PCs) that connect | Customer | Customer | Customer | Customer |
| Accounts and identities | Customer | Customer | Customer | Customer |
| Identity and directory infrastructure ("identity and access") | Customer | Customer | Shared | Shared |
| Applications | Customer | Customer | Shared | Provider |
| Network controls | Customer | Customer | Shared | Provider |
| Operating system | Customer | Customer | Provider | Provider |
| Physical hosts | Customer | Provider | Provider | Provider |
| Physical network | Customer | Provider | Provider | Provider |
| Physical datacenter | Customer | Provider | Provider | Provider |

- **Always the customer:** the information and data stored in the cloud, the devices allowed to connect, and the accounts and identities (who has access, and to what).
- **Always the provider (for any cloud service):** the physical datacenter, the physical network, and the physical hosts (the underlying infrastructure, including power, cooling, and connectivity).
- **Depends on the service type:** operating systems, network controls, applications, and identity and access (identity and directory infrastructure).
- **On-premises:** the customer owns every row.

Shared identity and access in PaaS and SaaS means the provider runs the authentication platform (such as Microsoft Entra ID) while you manage your own users, roles, and policies. IaaS places the most responsibility on the customer, SaaS places the most on the provider, and PaaS sits in the middle.

The table follows the diagram in the Microsoft training. Some Microsoft documentation draws the gray areas a little differently (for example, describing applications as shared in SaaS because you still configure the application). The rows the exam relies on do not change: data, devices, and accounts are always yours; the physical layers are always the provider's; the operating system is yours only in IaaS.

> **Exam tip:** "Who patches the operating system?" IaaS: the customer. PaaS and SaaS: the provider. This one row answers a large share of shared responsibility questions.

> **Exam tip:** No service type moves responsibility for your data or your user accounts to the provider. If a stem asks what the customer is responsible for "regardless of the service type," pick data, devices, or accounts and identities.

#### Cloud models (public, private, hybrid)

The cloud model (deployment model) says where the resources run and who can use them.

| Model | Definition | Characteristics |
|---|---|---|
| Public cloud | Built, owned, and run by a third-party provider and offered to anyone who wants to buy services | No capital expenditure to scale up; resources provisioned and deprovisioned quickly; pay only for what you use; you do not have complete control over resources and security |
| Private cloud | A cloud used by a single organization. It can run in your own datacenter or in a dedicated datacenter hosted by a third party | Complete control over resources and security; data is not collocated with other organizations' data; hardware must be bought for startup and maintenance; the organization is responsible for hardware maintenance and updates |
| Hybrid cloud | Public and private clouds used together as one interconnected environment | Most flexibility; you decide where each application runs; you control security, compliance, and legal requirements; can use the public cloud for extra capacity during temporary peaks |

**Multicloud** means using two or more public cloud providers at the same time, for example because you use different features from each or are migrating from one to another. Microsoft presents it as a fourth scenario next to the three cloud models; it is not a synonym for hybrid.

Two Azure products appear in this part of the Microsoft training:

- **Azure Arc** is a set of technologies for managing your cloud environment from Azure, whether that environment is only in Azure, a private cloud in your datacenter, a hybrid configuration, or a multicloud environment on several providers. See 3.3.
- **Azure VMware Solution** runs VMware workloads in Azure, for organizations that already use VMware in a private cloud and want to migrate to a public or hybrid cloud.

> **Exam tip:** Private cloud is defined by having a single tenant, not by location. A cloud dedicated to one organization is private even when a third party hosts it.

#### Use cases for each cloud model

| Requirement in the stem | Model |
|---|---|
| New company with no datacenter; wants no upfront hardware cost; wants to deploy fast | Public |
| Unpredictable or rapidly growing demand; pay only for what is used | Public |
| Must keep complete control of hardware and security; data must not share infrastructure with other organizations | Private |
| Legacy system that cannot move, or data that regulation requires to stay on-premises, combined with new cloud workloads | Hybrid |
| Keep the existing datacenter investment and use the public cloud for peak demand ("cloud bursting") or for disaster recovery | Hybrid |
| Migrate gradually, running some systems on-premises and some in Azure during the move | Hybrid |

> **Exam tip:** Any stem that mentions keeping something on-premises *and* using public cloud services is hybrid. "Most flexibility" also points to hybrid; "complete control" points to private; "no capital expenditure" points to public.

#### Consumption-based model

Two kinds of spending:

| | Capital expenditure (CapEx) | Operational expenditure (OpEx) |
|---|---|---|
| What it is | Upfront spending on physical infrastructure | Ongoing spending on services over time, billed as they are used |
| Examples | Buying servers and network hardware, building or buying datacenter space | Paying for cloud VMs, storage, or a software subscription |
| Capacity planning | Must predict demand in advance and buy for the peak | Add or remove resources as demand changes |

Cloud computing is OpEx because it follows a **consumption-based model**: you pay for the IT resources you use and nothing else. Benefits tested by the exam:

- No upfront costs for hardware or datacenter infrastructure.
- No need to buy and manage capacity that may sit underused.
- You can add resources when demand increases.
- You can release resources, and stop paying for them, when demand decreases.

A traditional datacenter forces you to estimate future needs. Overestimating wastes money on idle hardware; underestimating degrades performance until more hardware is ordered and installed. In the cloud you adjust resources to match actual demand.

> **Exam tip:** Buying servers is CapEx. Paying a monthly bill for VMs is OpEx. A stem about "moving from CapEx to OpEx" or "no upfront investment" is describing the consumption-based model.

#### Compare cloud pricing models

Cloud providers use a **pay-as-you-go** pricing model: you typically pay only for the services you consume. Microsoft lists three things this helps you do: plan and manage operating costs, run infrastructure more efficiently, and scale as workload needs change. The provider maintains the underlying infrastructure (power, cooling, hardware, networking).

The comparison the exam expects is pay-as-you-go against the traditional model of buying capacity in advance:

| | Traditional (owned) infrastructure | Cloud (pay-as-you-go) |
|---|---|---|
| Cost type | Mostly CapEx, plus running costs | OpEx |
| Upfront cost | High | None |
| Paying for unused capacity | Yes, hardware bought for the peak sits idle | No, you release what you do not need |
| Cost when demand rises | Buy and wait for hardware | Add resources and pay more for the period you use them |

Pricing by cloud model: the public cloud is pay-as-you-go with no capital expenditure; a private cloud still needs hardware purchases; a hybrid cloud mixes both. Azure also offers discounts for committing to usage in advance (reservations) and tools for estimating cost; those belong to 3.1.

> **Exam tip:** The cloud is not automatically cheaper. A virtual machine left running keeps billing whether or not anyone uses it. The benefit the exam wants is paying only for what you use, with no upfront cost.

#### Describe serverless

**Serverless** computing means the provider provisions, scales, and maintains the servers that run your code. Servers still exist; you just never manage them. Characteristics:

- No infrastructure management. You deploy code, not servers.
- Automatic scaling with demand, typically down to zero when nothing is running.
- Billing based on actual consumption, such as the number of executions and the resources each one uses. In a consumption-based plan you do not pay for idle time.
- Often event-driven: code runs in response to a trigger such as an HTTP request, a timer, or a new message.

Azure Functions is Azure's serverless compute service; the outline lists it as "functions" (see 2.2).

> **Exam tip:** Serverless vs a virtual machine: a VM bills for every hour it is allocated, even when idle, and you manage its operating system. Serverless code bills only when it runs, and there is no operating system for you to manage.

---

### 1.2 Describe the benefits of using cloud services

#### High availability and scalability

**High availability** means resources are available when needed, with minimal downtime, even when something fails or an event disrupts service. Azure backs it with uptime guarantees that depend on the service and are stated in **service-level agreements (SLAs)** as a percentage.

**Scalability** means adjusting resources to meet demand. Because billing is consumption-based, you add capacity for a peak and remove it afterward so you do not overpay.

| Scaling type | How | Terms |
|---|---|---|
| Vertical | Change the capability of an existing resource: more or fewer CPUs, more or less RAM | Scale up, scale down |
| Horizontal | Change the number of resources: add or remove VMs or containers | Scale out, scale in |

Scaling works in both directions, and it can be done manually or automatically (autoscaling).

**Elasticity** is a related term you may still meet: resources that grow and shrink automatically so that they match the workload at any moment. The current Microsoft training does not list elasticity as a separate benefit; it treats automatic scaling as part of scalability. If an answer set offers both, pick elasticity only when the stem stresses automatic adjustment up and down; if it offers only scalability, that is the answer for any stem about adjusting resources to demand.

> **Exam tip:** Bigger VM = vertical = scale up. More VMs = horizontal = scale out. Watch the direction too: "in" and "down" both remove capacity.

> **Exam tip:** High availability is about staying up. Scalability is about handling more (or less) load. A stem about an outage of one server not affecting users is availability; a stem about adding resources for a holiday traffic spike and removing them afterward is scalability.

#### Reliability and predictability

**Reliability** is the ability of a system to recover from failures and continue to function. The cloud supports it through decentralized design: resources can be deployed in regions around the world, so if one region has a catastrophic event, others keep running.

**Predictability** lets you move forward with confidence. It has two parts:

| | Performance predictability | Cost predictability |
|---|---|---|
| Meaning | Predicting the resources needed to give customers a positive experience | Predicting or forecasting what cloud spending will be |
| Supported by | Autoscaling, load balancing, high availability | Tracking resource use in real time, monitoring for efficient use, analyzing data to find patterns, estimating with the pricing calculator (3.1) |

Both tie back to the **Microsoft Azure Well-Architected Framework**, Microsoft's design guidance for cloud workloads: reliability is one of its pillars, and a solution built around the framework has predictable cost and performance.

> **Exam tip:** Reliability = recovers from failure. High availability = stays accessible with minimal downtime. They are close; choose reliability when the stem stresses recovery or deploying to multiple regions, and high availability when it stresses uptime or an SLA.

> **Exam tip:** Forecasting a bill is cost predictability. Autoscaling and load balancing delivering a consistent user experience is performance predictability.

#### Security and governance

**Governance** means keeping resources aligned with corporate standards and regulatory requirements. Cloud features support it:

- Templates help ensure every deployed resource meets corporate standards and regulatory requirements.
- When standards change, deployed resources can be updated at scale to match.
- Cloud-based auditing flags any resource that is out of compliance and offers mitigation strategies.
- Depending on the service type, software patches and updates are applied automatically, which helps both governance and security.

Azure's governance tools are in 3.2.

**Security** in the cloud lets you choose the level of control you need:

- IaaS gives you maximum control: you manage operating systems and installed software, including patches.
- PaaS and SaaS have patches and maintenance handled for you.
- The provider is well placed to absorb threats such as distributed denial of service (DDoS) attacks, which makes the network more robust.

Security remains a shared responsibility (1.1). The provider secures the infrastructure; you secure what you put in it.

#### Manageability

Two halves, and the exam asks you to tell them apart.

| | Management **of** the cloud | Management **in** the cloud |
|---|---|---|
| Question it answers | How are cloud resources managed? | How do you interact with and manage your cloud environment? |
| Examples | Automatically scale deployments to meet need; deploy resources from a preconfigured template, removing manual configuration; monitor resource health and automatically replace failing resources; receive automatic alerts based on configured metrics | Through a web portal; using a command-line interface; using APIs; using PowerShell |

The Azure tools for the second column (portal, CLI, PowerShell) are in 3.3.

> **Exam tip:** "Of" = what the platform can do to resources (autoscale, templates, self-healing, alerts). "In" = the interface you use (portal, CLI, APIs, PowerShell).

---

### 1.3 Describe cloud service types

The service type decides how much the provider manages and how much you manage. Flexibility and responsibility move together: the most control comes with the most work.

#### Infrastructure as a service (IaaS)

The provider maintains the hardware, network connectivity to the internet, and physical security. You rent compute, storage, and networking and manage everything above them: operating system installation, configuration, patching, network configuration, and applications.

- Most flexible service type; gives the customer the maximum amount of control.
- Places the largest share of responsibility on the customer.
- Example: Azure Virtual Machines.

#### Platform as a service (PaaS)

The provider maintains the physical infrastructure, physical security, and internet connection, and also the operating systems, middleware, development tools, and analytics services. You do not handle licensing or patching for operating systems and databases. You deploy and manage your applications and data.

- Middle ground between IaaS and SaaS.
- A complete development and deployment environment without the infrastructure work.
- Examples: Azure App Service, Azure SQL Database.

#### Software as a service (SaaS)

You use a fully developed application that the provider hosts and manages. You are responsible only for the data you put into it, the devices you allow to connect, and the users who have access.

- Least flexible; you take the application as offered and configure it.
- Easiest to get running; least technical knowledge needed.
- Commonly paid for by subscription, per user, monthly or annually.
- Examples: Microsoft 365 (email, Teams, Office apps), Dynamics 365. Email, messaging, and financial software are the typical SaaS categories.

#### Use cases for each

| Service type | Typical scenarios |
|---|---|
| IaaS | Lift-and-shift migration: recreate on-premises servers as cloud VMs with little change. Testing and development: build and tear down environments quickly while keeping full control of their configuration. Software that needs a custom operating system configuration |
| PaaS | Development framework: developers build on built-in components and features such as scalability and high availability instead of writing them. Analytics or business intelligence: tools provided with the platform to analyze and mine data |
| SaaS | Email and messaging. Business productivity applications. Finance and expense tracking |

| | IaaS | PaaS | SaaS |
|---|---|---|---|
| You manage | Operating system, middleware, runtime, applications, data | Applications, data | Data, devices, user access |
| Flexibility and control | Highest | Medium | Lowest |
| Management effort | Highest | Medium | Lowest |

Serverless (1.1) goes one step past PaaS in abstraction: you supply only code, and the platform runs and scales it on demand.

> **Exam tip:** Identify the type by what the customer touches. Installs or patches an operating system: IaaS. Deploys code or a database without managing servers: PaaS. Signs in and uses an application: SaaS.

> **Exam tip:** "Migrate existing servers with minimal changes" is IaaS, even if PaaS would be better long term. "Developers want to focus on code, not infrastructure" is PaaS. "Minimize administrative effort" for a standard business function such as email is SaaS.

---

### Most-tested distinctions

- **Customer always owns:** information and data, devices, accounts and identities. **Provider always owns:** physical datacenter, network, and hosts.
- **Operating system responsibility:** customer in IaaS; provider in PaaS and SaaS.
- **Public vs private vs hybrid:** no CapEx and pay for what you use; single organization with complete control; a mix that gives the most flexibility.
- **Hybrid vs multicloud:** hybrid joins private and public; multicloud uses several public providers.
- **CapEx vs OpEx:** upfront purchase of physical assets vs ongoing payment for services. Cloud is OpEx.
- **Consumption-based model:** no upfront cost, pay only for what you use, stop paying when you stop using.
- **Serverless:** servers exist but you do not manage them; scales automatically; billed only when code runs.
- **Vertical vs horizontal scaling:** resize an existing resource (up/down) vs change the number of resources (out/in).
- **Scalability vs elasticity:** adjusting resources to meet demand, manually or automatically, vs the older term for automatic adjustment in both directions. Microsoft's current training covers both under scalability.
- **High availability vs reliability:** minimal downtime backed by an SLA vs recovering from failure, helped by deploying to multiple regions.
- **Performance vs cost predictability:** autoscaling, load balancing, and high availability vs forecasting and tracking spending.
- **Management of vs in the cloud:** autoscale, templates, self-healing, and alerts vs portal, CLI, APIs, and PowerShell.
- **IaaS vs PaaS vs SaaS:** rent infrastructure and manage the operating system; deploy applications to a managed platform; use finished software.
- **Use cases:** lift-and-shift and test/dev are IaaS; development framework and analytics are PaaS; email, productivity, and expense tracking are SaaS.

---

## Domain 2 — Azure Architecture and Services (35–40%)

Objectives 2.1–2.4. The largest domain: the physical and logical building blocks of Azure (2.1), compute and networking (2.2), storage (2.3), and identity, access, and security (2.4). Most questions are "which service fits this scenario", so learn each service by the one thing that sets it apart from its neighbors.

---

### 2.1 Describe the core architectural components of Azure

Two layers. **Physical infrastructure**: datacenters, grouped into availability zones, regions, and region pairs. **Management infrastructure**: resources, resource groups, subscriptions, and management groups, which organize what you deploy and control billing and access.

#### Azure regions, region pairs, and sovereign regions

**Region**: a geographical area that contains at least one, and potentially several, datacenters that are close together and connected by a low-latency network. You pick a region when you create most resources. Choose it for proximity to users (latency), data residency requirements, service availability, and price. Not every service or VM size is offered in every region.

**Region pair**: most regions are paired with another region in the same geography (for example US, Europe, or Asia), at least 300 miles away. The pair exists so that a regional disaster does not take out both copies of a workload.

| Region pair behavior | What it means for you |
|---|---|
| Distance (at least 300 miles) | A natural disaster, civil unrest, or power outage is unlikely to hit both regions |
| Prioritized recovery | In a widespread Azure outage, one region of every pair is restored first |
| Sequential updates | Planned Azure updates roll out to one region of a pair at a time |
| Same geography | Replicated data stays in the same geography for tax and legal jurisdiction purposes (Brazil South is the stated exception: its pair is in the US) |

Most pairs work in both directions (West US backs up East US and the reverse). A few are one-directional: Brazil South's secondary region is South Central US, but South Central US's secondary is not Brazil South; West India is paired with South India, but South India's pair is Central India. Some newer regions (for example Italy North, Poland Central, and Israel Central) have no paired region and rely on availability zones for resiliency.

Region pairs are an Azure platform arrangement. Some services replicate to the paired region automatically (geo-redundant storage, see 2.3); for others, you must configure replication yourself. A pair does not make every workload redundant by itself.

**Sovereign regions**: instances of Azure that are isolated from the main Azure cloud, used for compliance or legal reasons.

| Sovereign region | Who it is for | Who operates it |
|---|---|---|
| Azure Government (US DoD Central, US Gov Virginia, US Gov Arizona, and others) | US government agencies and their partners | Microsoft, with screened US persons; physically and logically isolated network |
| Azure operated by 21Vianet (China East, China North, and others) | Customers that need a presence in China | 21Vianet, under a partnership; Microsoft does not directly maintain the datacenters |

> **Exam tip:** "US government agency" or "screened US personnel" means Azure Government. "Operated by a partner, not by Microsoft" means the China regions run by 21Vianet. Both are sovereign regions, separate from the public Azure regions.

#### Availability zones

**Availability zone**: a physically separate location inside one Azure region. Each zone is made up of one or more datacenters with independent power, cooling, and networking, and the zones are connected through high-speed private fiber. If one zone goes down, the others keep working. Regions that support availability zones have a minimum of three; not every region supports them.

Zones protect against a datacenter-level failure inside a region. They do not protect against the loss of the whole region; that is what a second region (usually the paired one) is for.

| Service category | How it uses zones | Examples |
|---|---|---|
| Zonal services | You pin the resource to a specific zone that you choose | VMs, managed disks, IP addresses |
| Zone-redundant services | The platform replicates automatically across zones | Zone-redundant storage, SQL Database |
| Non-regional services | Always available from Azure geographies; resilient to zone-wide and region-wide outages | Global services that do not ask you to pick a region, such as Microsoft Entra ID, Azure Traffic Manager, and Azure DNS |

> **Exam tip:** Scope of each protection. Availability set: hardware failure or maintenance inside one datacenter (see 2.2). Availability zones: failure of an entire datacenter, inside one region. Region pairs: failure of an entire region. Match the size of the outage in the stem to the feature.

> **Exam tip:** "Zonal" = you place the resource in zone 1, 2, or 3 and must deploy copies to other zones yourself. "Zone-redundant" = Azure spreads the copies across zones for you.

#### Azure datacenters

**Datacenter**: a physical facility that houses racks of servers with dedicated power, cooling, and networking. Microsoft operates them around the world, but customers never deploy to an individual datacenter directly. Datacenters are grouped into regions and availability zones, and those are what you select. Physical security of the datacenter is always Microsoft's part of the shared responsibility model (see 1.1).

#### Resources and resource groups

**Resource**: the basic building block of Azure. Anything you create, provision, or deploy is a resource: a VM, a virtual network, a database, a storage account.

**Resource group**: a logical container for resources. It is a management unit, not a network or security boundary by default.

| Rule | Detail |
|---|---|
| Every resource must be in a resource group | You cannot create a resource without one |
| One group per resource | A resource belongs to exactly one resource group at a time |
| Resources can move | Many resources can be moved to a different resource group |
| No nesting, no renaming | A resource group cannot contain another resource group, and it cannot be renamed after it is created |
| Actions apply to the contents | Deleting a resource group deletes every resource in it; access granted on the group applies to every resource in it |
| Location is for metadata | The group's region is where metadata about its resources is stored; the resources themselves can be in any region |

Group resources that share a lifecycle: things you deploy, update, and delete together. A dev/test environment in one resource group can be removed in a single operation.

> **Exam tip:** A resource group in West Europe can hold a VM in East US. The group's location only decides where its metadata lives.

> **Exam tip:** "Remove all resources of a decommissioned project in one step" = delete the resource group. "Stop someone from deleting it by accident" = a resource lock (3.2).

#### Subscriptions

**Subscription**: a unit of management, billing, and scale. It links to an Azure account, which is an identity in Microsoft Entra ID (see 2.4), and it is required before you can create any resource. An account can have more than one subscription.

| Boundary | Meaning |
|---|---|
| Billing boundary | Each subscription gets its own billing reports and invoice, so costs can be separated per subscription |
| Access control boundary | Access management policies are applied at the subscription level, so different teams or departments can be governed separately |

Common reasons to create additional subscriptions: to separate environments (development, test, production), to match organizational structure (one per department), or to separate billing. A subscription also has resource limits (quotas), so very large deployments may need more than one.

> **Exam tip:** "Each department needs its own invoice" = separate subscriptions. "Track cost by project inside one subscription" = tags (3.1) or resource groups.

#### Management groups

**Management group**: a container for subscriptions (and other management groups). Governance settings such as Azure Policy assignments (3.2) and Azure RBAC role assignments (see 2.4) applied to a management group are inherited by every subscription beneath it. Use management groups when an organization has many subscriptions and wants to manage access, policy, and compliance for them together.

Facts Microsoft Learn states:

- 10,000 management groups can be supported in a single directory.
- A management group tree can be up to six levels deep, not counting the root level or the subscription level.
- Each management group and each subscription has exactly one parent.
- Every directory (Microsoft Entra tenant) has one top-level **root management group**, shown as the Tenant Root Group; all other management groups and subscriptions fold up to it.
- Unlike resource groups, management groups can be nested.

#### Hierarchy of resource groups, subscriptions, and management groups

Four levels, top to bottom:

| Level | Contains | Typical use |
|---|---|---|
| Management groups | Subscriptions and other management groups | Policy and access across many subscriptions |
| Subscriptions | Resource groups | Billing and access boundary |
| Resource groups | Resources | Lifecycle and day-to-day management |
| Resources | Nothing | The individual service instance |

**Inheritance** flows downward. A policy or role assigned at a management group applies to its subscriptions, their resource groups, and their resources. A role assigned at a resource group applies to the resources in that group only. Settings applied at a lower level do not flow up.

> **Exam tip:** Management groups nest; resource groups do not. Subscriptions hold resource groups, never other subscriptions.

> **Exam tip:** To apply one rule to several subscriptions in a single assignment, assign it at a management group. Assigning it at the subscription level would require one assignment per subscription.

---

### 2.2 Describe Azure compute and networking services

#### Compare compute types: virtual machines, containers, and functions

| Compute type | What is virtualized | You manage | Service model | Best fit |
|---|---|---|---|---|
| Virtual machines | Hardware; each VM runs a full guest operating system | OS, patches, installed software, configuration | IaaS | Full control of the OS, custom software, lift-and-shift of existing servers |
| Containers | The operating system; a container packages the app and its dependencies and shares the host OS | The container image and the app | PaaS (managed container services) | Lightweight, portable apps; microservices; fast start and scale |
| Functions | Everything below your code | Only the code | Serverless | Short, event-driven code that runs in response to a trigger |

**Containers** start faster and use fewer resources than VMs because they do not include a guest OS. Several containers can run on one host. Azure container services:

| Service | What it is | Choose it when |
|---|---|---|
| Azure Container Instances (ACI) | The fastest and simplest way to run a container; a PaaS offering where you upload a container and Azure runs it, with no VMs to manage | A single container or a simple task, without orchestration |
| Azure Container Apps | Similar to ACI (no container management, PaaS), with added built-in load balancing and scaling | Containerized apps that need elastic scale without running Kubernetes yourself |
| Azure Kubernetes Service (AKS) | A managed Kubernetes container orchestration service | Managing the lifecycle of large numbers of containers: deployment, scaling, and fleet-wide management |

**Azure Functions**: an event-driven, serverless compute option. Code runs when a trigger fires (an HTTP request, a timer, a message arriving in a queue), scales automatically with demand, and you are charged only for the CPU time used while the function runs. Functions can be stateless (the default; each run starts fresh) or stateful (Durable Functions, where a context is passed through to track prior activity). There are no virtual machines or containers for you to maintain.

> **Exam tip:** "Only cares about the code", "runs in response to an event", "pay only while it runs" = Azure Functions. "Needs full control of the operating system" = virtual machine. "Package the app with its dependencies and run it anywhere" = container.

> **Exam tip:** Container orchestration, or "manage many containers", points to AKS. "Run one container quickly with no infrastructure" points to Container Instances.

#### Virtual machine options

**Azure Virtual Machines**: IaaS virtualized servers. You choose the image (Windows or Linux, or a custom image), and you are responsible for the OS and everything installed on it. Use VMs for dev/test, for running applications in the cloud, for extending a datacenter, for disaster recovery, and for lift-and-shift migrations of physical servers.

**Virtual Machine Scale Sets**: a group of identical, load-balanced VMs that you create and manage as a unit. The number of instances can increase or decrease automatically in response to demand or on a schedule (autoscale). Scale sets work with a load balancer so that traffic is spread across the instances. Use it for large-scale compute, big data, and container workloads.

**Availability sets**: a way to make a group of VMs more resilient by spreading them so that they are not all affected by the same event. There is no extra charge for an availability set; you pay only for the VMs.

| Grouping | Protects against | How |
|---|---|---|
| Update domain | Planned maintenance | VMs in one update domain can be rebooted at the same time; Azure updates one update domain at a time, then moves to the next |
| Fault domain | Unplanned hardware failure | VMs in one fault domain share a common power source and network switch; an availability set spreads VMs across up to three fault domains by default |

**Azure Virtual Desktop (AVD)**: a desktop and application virtualization service that runs in the cloud. Users get a full Windows desktop or individual apps from almost any device or browser. Points the exam uses:

- Data and apps stay in Azure, separate from the local hardware, which lowers the risk of data being left on a personal device.
- Sign-in uses Microsoft Entra ID, so multifactor authentication and granular role-based access control apply.
- Windows 10 or Windows 11 Enterprise multi-session lets several users share one VM at the same time, which reduces the number of VMs to run.

| Need | Use |
|---|---|
| One or a few servers with full OS control | Azure Virtual Machines |
| Identical VMs that scale out and in automatically behind a load balancer | Virtual Machine Scale Sets |
| Keep a group of VMs from all going down during maintenance or a rack failure | Availability sets |
| Cloud-hosted Windows desktops and apps for remote users | Azure Virtual Desktop |

> **Exam tip:** Scale sets answer "scale", availability sets answer "stay up". If the stem says demand varies, pick scale sets. If it says planned maintenance or a hardware fault must not take down every VM, pick availability sets. If it says an entire datacenter fails, pick availability zones (see 2.1).

#### Resources required for virtual machines

When you create a VM, you choose or create the resources it depends on:

- **Size**: purpose, number of processor cores, and amount of RAM.
- **Storage disks**: hard disk drives or solid-state drives (an OS disk at minimum).
- **Networking**: a virtual network, a network interface, optionally a public IP address, and port configuration.
- A **resource group** to hold all of it.

These are separate resources that are billed separately. Stopping (deallocating) a VM stops the compute charge, but its disks and any reserved public IP address continue to cost money (3.1).

#### Application hosting options

| Option | Model | You get | Choose it when |
|---|---|---|---|
| Azure App Service | PaaS | A managed, HTTP-based platform with built-in scaling, load balancing, and high availability, on Windows or Linux | You want to host a web app or API and focus on the code, not the servers |
| Containers (ACI, Container Apps, AKS) | PaaS | A portable package of the app and its dependencies | The app is already containerized, or is built as microservices |
| Virtual machines | IaaS | The whole operating system | You need full control of the hosting environment, or the app cannot be changed |

**Azure App Service** hosts web apps, API apps (REST-based web APIs), WebJobs (background tasks), and back ends for mobile apps. It supports many languages, including .NET, Java, Node.js, PHP, and Python, and supports automated deployments from GitHub, Azure DevOps, or any Git repository.

> **Exam tip:** "Host a website without managing the underlying servers" = App Service. If the stem adds "must install custom software on the operating system", it becomes a virtual machine.

#### Virtual networking

**Azure virtual network (VNet)**: a private, isolated network in Azure that lets resources such as VMs and web apps communicate with each other, with the internet, and with on-premises networks. A VNet has a private IP address space that you define, and it exists in a single region and a single subscription.

**Subnets**: divisions of a virtual network's address space. Use them to segment resources (for example a web tier and a database tier) and to apply different filtering rules to each segment.

What virtual networks provide:

| Capability | How |
|---|---|
| Isolation and segmentation | Separate VNets with their own address spaces, divided into subnets |
| Internet communication | Incoming connections from the internet are enabled by assigning a public IP address to a resource or placing it behind a public load balancer |
| Communication between Azure resources | Resources in the same VNet reach each other; service endpoints connect a VNet to other Azure services such as Azure SQL Database and storage accounts |
| Communication with on-premises resources | Point-to-site VPN, site-to-site VPN, or ExpressRoute |
| Routing network traffic | Route tables, or Border Gateway Protocol (BGP) with VPN gateways and ExpressRoute |
| Filtering network traffic | Network security groups (rules by source and destination IP address, port, and protocol) and network virtual appliances |
| Connecting virtual networks | Virtual network peering |

**Virtual network peering**: connects two virtual networks so that resources in each can communicate as if they were on one network. Traffic between peered networks is private and travels on the Microsoft backbone network; it never enters the public internet. The networks can be in different regions (global peering) and in different subscriptions.

**Azure DNS**: a hosting service for DNS domains that provides name resolution using Microsoft Azure infrastructure. You manage DNS records with the same credentials, tools, and billing as your other Azure services.

- Reliability and performance: domains are hosted on Azure's global network of DNS name servers.
- Security: based on Azure Resource Manager, so Azure RBAC, activity logs, and resource locks apply.
- Private domains: private DNS zones let you use your own domain names inside virtual networks.
- Alias records: a record set can point to an Azure resource, such as a public IP address.
- You cannot buy a domain name through Azure DNS. Register the name with an App Service domain or a third-party registrar, then host its zone in Azure DNS.

**Azure VPN Gateway**: a virtual network gateway that sends encrypted traffic between an Azure virtual network and another location over the public internet. A virtual network can have only one VPN gateway, but that gateway can serve several connections.

| Connection type | Connects | Typical scenario |
|---|---|---|
| Site-to-site | An on-premises network (through a VPN device) to a virtual network | A branch office or datacenter that needs a permanent link to Azure |
| Point-to-site | An individual computer to a virtual network | A remote employee's laptop |
| Network-to-network (VNet-to-VNet) | One virtual network to another | Linking virtual networks through their gateways |

| VPN type | How traffic is selected | Notes |
|---|---|---|
| Policy-based | Statically: you specify the IP addresses of packets that should be encrypted through each tunnel | For a small number of fixed connections |
| Route-based | IPsec tunnels are modeled as network interfaces, and IP routing (static routes or dynamic routing protocols) decides which tunnel to use | Preferred for on-premises connectivity; required for point-to-site, multisite, connections between virtual networks, and coexistence with an ExpressRoute gateway |

**Azure ExpressRoute**: extends an on-premises network into the Microsoft cloud over a private connection provided by a connectivity provider. Each connection is called an ExpressRoute circuit.

- Traffic does not go over the public internet, which gives more reliability, faster speeds, consistent latency, and higher security than a typical internet connection.
- It reaches Microsoft cloud services across all regions in a geopolitical region; ExpressRoute Global Reach lets on-premises sites exchange data across their circuits.
- It uses dynamic routing (BGP) and has built-in redundancy in every peering location.
- The connection is private, but traffic on it is not encrypted by default. Add encryption yourself if you need it.
- DNS queries, certificate revocation list checks, and Azure Content Delivery Network requests still travel over the public internet.
- Connectivity models: CloudExchange colocation, point-to-point Ethernet connection, any-to-any networks, and directly from ExpressRoute sites.

| | VPN Gateway | ExpressRoute |
|---|---|---|
| Path | Public internet | Private connection through a connectivity provider |
| Encryption | Encrypted tunnel | Private, not encrypted by default |
| Performance | Depends on the internet connection | Consistent latency, higher speeds |
| Setup | Quick; needs only a VPN device or client | Needs a provider and a provisioned circuit |

> **Exam tip:** "Must not travel over the public internet" or "dedicated private connection from the datacenter" = ExpressRoute. "Encrypted tunnel over the internet" = VPN Gateway. A VPN connection can also be configured as a failover path for ExpressRoute.

> **Exam tip:** Peering connects two virtual networks inside Azure. VPN Gateway and ExpressRoute connect Azure to somewhere outside it. One laptop = point-to-site; an entire office = site-to-site.

#### Public and private endpoints

**Public endpoint**: an address with a public IP that can be reached from anywhere in the world over the internet. Many Azure PaaS services (storage accounts, SQL Database) have a public endpoint by default.

**Private endpoint**: a network interface that lives in your virtual network and has a private IP address from that network's address space. It connects privately to a service by using **Azure Private Link**, so traffic to the service stays on the Microsoft backbone and the service can be reached without using its public endpoint.

**Service endpoint**: enabled on a subnet, it extends the virtual network's identity to an Azure service over the Microsoft backbone, so the service can be restricted to accept traffic only from that subnet. The service is still reached at its public endpoint; it does not get a private IP address in your network.

| | Public endpoint | Service endpoint | Private endpoint (Private Link) |
|---|---|---|---|
| Address used to reach the service | Public IP | The service's public IP | A private IP from your virtual network |
| Reachable from the internet | Yes | Only if the service's firewall allows it | Not through the private endpoint |
| Where traffic travels | Internet | Microsoft backbone | Microsoft backbone |
| Reachable from on-premises over VPN or ExpressRoute by private IP | No | No | Yes |

> **Exam tip:** "The service must have a private IP address in the virtual network" = private endpoint. "Restrict the service to a specific subnet" while it keeps its public address = service endpoint.

---

### 2.3 Describe Azure storage services

A **storage account** is the container for Azure Storage data: it gives you a globally unique namespace reachable over HTTP/HTTPS, and its type and redundancy setting decide which services you get and how many copies are kept. All data written to a storage account is encrypted by the service.

#### Compare Azure Storage services

| Service | What it stores | Use it when | Exam keywords |
|---|---|---|---|
| Azure Blobs | Unstructured object data (text or binary) at massive scale; also the base for Data Lake Storage Gen2 | Images and documents served to a browser, video and audio streaming, backups, archives, log files, data for analytics | "unstructured", "object", "images/video", "backup and archive" |
| Azure Files | Fully managed file shares reached over SMB or NFS; can be mounted at the same time from cloud and on-premises machines | Replacing or extending a file server, "lift and shift" of apps that expect a file share, shared configuration files | "file share", "SMB", "mount", "map a drive" |
| Azure Queues | Messages for asynchronous processing; millions of messages, each up to 64 KB | Decoupling application components, building a backlog of work (often processed by Azure Functions) | "messages", "asynchronous", "decouple" |
| Azure Tables | NoSQL store for structured, non-relational data | Large amounts of schemaless key/attribute data without relational joins | "NoSQL", "structured, non-relational" |
| Azure Disks | Block-level storage volumes (managed disks) attached to Azure VMs | Operating system and data disks for virtual machines (see 2.2) | "VM disk", "block-level", "managed disk" |

- **Blobs** are reached through URLs, the REST API, Azure PowerShell, the Azure CLI, or client libraries. There are three blob types: block blobs (ordinary files), append blobs (logging), and page blobs (random-access files such as virtual hard disks).
- **Azure Files** shares: SMB shares work from Windows, Linux, and macOS; NFS shares work from Linux and macOS. SMB shares can be cached on Windows Servers with Azure File Sync (see "Moving files" below).
- **Azure Disks** are virtualized and managed by Azure; you choose a size and type and Azure handles the underlying storage.

> **Exam tip:** Blob = objects, Files = shares you mount, Queues = messages, Tables = NoSQL rows, Disks = VM volumes. "Shared by several VMs and on-premises PCs at the same time over SMB" is Azure Files, not Disks and not Blobs.

> **Exam tip:** Azure Tables is not a relational database. If the stem says "relational", "SQL queries", or "joins", the answer is a database service, not Table storage.

#### Storage tiers

Blob storage has **access tiers** that trade storage cost against access cost and retrieval speed. The cooler the tier, the cheaper it is to store data and the more expensive it is to read it.

| Tier | Optimized for | Minimum storage period | Online? | Can be the account default? |
|---|---|---|---|---|
| Hot | Data accessed frequently (for example, images for a website) | None | Yes | Yes |
| Cool | Data accessed infrequently and stored for at least 30 days (for example, customer invoices) | 30 days | Yes | Yes |
| Cold | Data accessed infrequently and stored for at least 90 days | 90 days | Yes | Yes |
| Archive | Data that is rarely accessed, stored for at least 180 days, with flexible latency requirements (for example, long-term backups) | 180 days | No (offline) | No |

- **Account level vs blob level:** hot, cool, and cold can be set as the account's default tier; archive cannot. All four tiers can be set on an individual blob, during or after upload. A blob without its own setting takes the account default (hot unless you change it).
- **Cost direction:** hot has the highest storage cost and the lowest access cost; cool and cold have lower storage costs, higher access costs, and a slightly lower availability SLA; archive has the lowest storage cost and the highest access cost and retrieval latency.
- **Rehydration:** a blob in the archive tier is offline and cannot be read or modified. It must first be **rehydrated** to an online tier (hot, cool, or cold), which can take hours (Microsoft's documentation says up to 15 hours).
- **Early deletion:** removing or re-tiering a blob before its tier's minimum period has passed incurs a prorated early-deletion charge.

> **Exam tip:** Remember 30 / 90 / 180 for cool / cold / archive. "Rarely accessed, kept for years, a retrieval delay of several hours is acceptable" is archive. "Rarely accessed but must be readable immediately" is cool or cold, never archive.

> **Exam tip:** Access tiers apply to blob data. They are not a feature of queues, tables, or disks, and archive can only be set per blob, not as an account default.

#### Redundancy options

Azure Storage always keeps at least three copies of your data. The redundancy option decides where the copies are, and that determines what failure you survive and what you pay.

| Option | Copies and location | Protects against | Durability (per year) |
|---|---|---|---|
| LRS, locally redundant storage | 3 copies in a single datacenter in the primary region | Drive and server-rack failure | At least 11 nines |
| ZRS, zone-redundant storage | 3 copies, written synchronously across 3 availability zones in the primary region | Loss of a datacenter or a whole zone | At least 12 nines |
| GRS, geo-redundant storage | 3 copies in one datacenter in the primary region (LRS), plus 3 copies in the paired secondary region (LRS), copied asynchronously | Loss of the whole primary region | At least 16 nines |
| GZRS, geo-zone-redundant storage | 3 copies across 3 zones in the primary region (ZRS), plus 3 copies in the paired secondary region (LRS), copied asynchronously | Zone failure and regional disaster | At least 16 nines |

- **LRS** is the lowest-cost option and the least durable: a disaster in that one datacenter can lose the data.
- **ZRS** keeps data readable and writable if one zone is down, and keeps every copy inside one region, which suits data-residency requirements. It needs a region that has availability zones (see 2.1).
- **Secondary region:** you choose the primary region; Azure assigns the secondary from the region pair (see 2.1). Replication to the secondary is asynchronous, so the newest writes can be lost in a regional disaster. Microsoft describes the typical recovery point objective (RPO) as under 15 minutes, with no SLA on it.
- **Read-access variants (RA-GRS, RA-GZRS):** with plain GRS or GZRS, the secondary copy cannot be read until a failover to the secondary region happens. RA-GRS and RA-GZRS add read access to the secondary region at all times. The copy count and durability are the same as GRS and GZRS; only the ability to read changes.

> **Exam tip:** Count and place the copies. LRS = 3 in one datacenter. ZRS = 3 across zones in one region. GRS = 6 (3 + 3) across two regions, LRS on both sides. GZRS = 6 (3 across zones + 3 in the secondary region).

> **Exam tip:** "Survive a datacenter failure but keep the data in one region" is ZRS. "Survive a regional outage" is GRS or GZRS. "Read the data from the secondary region while the primary is still up" requires an RA- option. "Highest availability and regional protection together" is GZRS (RA-GZRS if reads from the secondary are needed).

#### Storage account options and storage types

The account type decides which services and redundancy options are available.

| Account type | Supported services | Redundancy options | Use for |
|---|---|---|---|
| Standard general-purpose v2 | Blob Storage (including Data Lake Storage), Queue Storage, Table Storage, Azure Files | LRS, GRS, RA-GRS, ZRS, GZRS, RA-GZRS | The default choice; recommended for most scenarios |
| Premium block blobs | Blob Storage (block blobs and append blobs, including Data Lake Storage) | LRS, ZRS | High transaction rates, smaller objects, or consistently low storage latency |
| Premium file shares | Azure Files only | LRS, ZRS | High-performance file shares; the type to use when you need both SMB and NFS shares |
| Premium page blobs | Page blobs only | LRS | Page blob workloads |

- Standard accounts are the only ones that offer the geo-redundant options. Premium accounts are limited to LRS and ZRS (premium page blobs to LRS only).
- Only standard general-purpose v2 supports queues and tables.
- NFS file shares in Azure Files require the premium file shares account type.

**Storage account names and endpoints**

- A storage account name must be **3 to 24 characters**, **lowercase letters and numbers only**, and **unique across all of Azure**, because the name becomes part of the public endpoint.
- Each service has its own endpoint built from the account name:

| Service | Endpoint |
|---|---|
| Blob Storage | `https://<storage-account-name>.blob.core.windows.net` |
| Data Lake Storage Gen2 | `https://<storage-account-name>.dfs.core.windows.net` |
| Azure Files | `https://<storage-account-name>.file.core.windows.net` |
| Queue Storage | `https://<storage-account-name>.queue.core.windows.net` |
| Table Storage | `https://<storage-account-name>.table.core.windows.net` |

> **Exam tip:** Storage account names are globally unique and cannot contain uppercase letters, hyphens, or underscores. Resource groups, by contrast, only need a name that is unique within the subscription.

#### Moving files (AzCopy, Azure Storage Explorer, Azure File Sync)

These tools move or manage individual files and small sets of files, as opposed to migrating a whole datacenter.

| Tool | What it is | Direction | Pick it when |
|---|---|---|---|
| AzCopy | Command-line utility that copies blobs and files to, from, and between storage accounts; can also copy to and from other cloud providers | Upload, download, copy, and **one-direction** sync from a source to a destination | The task must be scripted or automated |
| Azure Storage Explorer | Standalone app with a graphical interface for managing blobs and files; runs on Windows, macOS, and Linux and uses AzCopy on the back end | Upload, download, and move between accounts | An administrator wants a GUI |
| Azure File Sync | Service that centralizes file shares in Azure Files while a local Windows file server keeps a fast local cache | **Bi-directional** sync between Windows Server and an Azure file share | Branch offices need local file-server performance with the data centralized in Azure |

With Azure File Sync you can keep using any protocol Windows Server offers to reach the data locally (SMB, NFS, FTPS), have as many caches as you need around the world, replace a failed local server by installing Azure File Sync on a new one, and turn on **cloud tiering** so that frequently used files stay local and rarely used files stay in the cloud until someone asks for them.

> **Exam tip:** AzCopy = command line, one-way sync. Storage Explorer = graphical, any desktop OS. Azure File Sync = installed on Windows Server, two-way sync, cloud tiering. Azure File Sync is not a general copy tool and works with Azure Files, not Blob storage.

#### Migration (Azure Migrate, Azure Data Box)

| Option | Type | What it does |
|---|---|---|
| Azure Migrate | Online, over the network | A hub (one portal) to discover, assess, and migrate on-premises servers, databases, and web apps to Azure, and to track the migration |
| Azure Data Box | Offline, physical device | Microsoft ships you an encrypted storage device; you copy data to it and ship it back (or the reverse for an export) |

**Azure Migrate** provides:

- **A unified migration platform:** one portal to start, run, and track the migration.
- **A range of tools:** *Azure Migrate: Discovery and assessment* (find on-premises servers running on VMware, Hyper-V, or physical hardware and assess readiness, sizing, and cost) and *Azure Migrate: Server Migration* (move those servers to Azure; these are the names in the AZ-900 training, and current product documentation calls the migration tool Azure Migrate and Modernize). The hub also has integrated options for database migration and web app migration, integrates with independent software vendor (ISV) tools, and uses Azure Data Box for large offline data moves.
- **Assessment and migration** of on-premises infrastructure from the same place.

**Azure Data Box** is the physical option for very large data sets (tens of terabytes or more) when the network is too slow, too expensive, or unavailable:

- You order the device in the Azure portal, set it up through its local web UI, copy the data, and return it by carrier. For an import, the data is uploaded to your storage account automatically when Microsoft receives the device. The whole order is tracked in the portal.
- It works in both directions: **import** to Azure and **export** from Azure.
- Typical import uses: a one-time bulk migration, an initial bulk transfer followed by incremental transfers over the network, and periodic uploads of large amounts of data. Typical export uses: disaster recovery, regulatory or security requirements, and moving data back on-premises or to another provider.
- The device has a rugged case, the data is encrypted, and the disks are wiped to NIST 800-88r1 standards after the upload.
- Device lineup: Microsoft Learn's AZ-900 module describes a Data Box with 80 TB of usable capacity. Current product documentation lists next-generation Data Box devices of 120 TB and 525 TB that are replacing the 80 TB model region by region, still offers the smaller Data Box Disk (a set of encrypted solid-state disks for smaller transfers), and states that the larger Data Box Heavy has been retired. Do not memorize capacities; know that Data Box is the offline, ship-a-device option.

> **Exam tip:** "Limited bandwidth" or "would take months over the network" plus "tens or hundreds of terabytes" is Azure Data Box. "Discover, assess, and migrate servers" is Azure Migrate. "Copy a folder from a script" is AzCopy.

---

### 2.4 Describe Azure identity, access, and security

#### Directory services (Microsoft Entra ID, Microsoft Entra Domain Services)

**Microsoft Entra ID** (formerly Azure Active Directory) is Microsoft's cloud-based identity and access management service. Users sign in with it to Microsoft cloud services (Azure, Microsoft 365) and to applications your organization develops or subscribes to. You control the identity accounts; Microsoft keeps the service available globally.

Microsoft Entra ID provides:

- **Authentication:** verifying identity, including self-service password reset, multifactor authentication, a banned password list, and smart lockout.
- **Single sign-on (SSO):** one identity for many applications.
- **Application management:** cloud and on-premises apps, through features such as Application Proxy, SaaS app integration, and the My Apps portal.
- **Device management:** device registration, integration with Microsoft Intune, and device-based Conditional Access.

| | Active Directory Domain Services (AD DS) | Microsoft Entra ID | Microsoft Entra Domain Services |
|---|---|---|---|
| What it is | The directory role on Windows Server | Cloud identity service | Managed domain services in Azure |
| Who runs the domain controllers | You do | Not applicable (no domain controllers) | Microsoft does |
| Protocols | Kerberos, NTLM, LDAP, Group Policy | Modern web-based sign-in for cloud apps | Kerberos, NTLM, LDAP, Group Policy, domain join |
| Typical use | On-premises domain | Sign-in to Azure, Microsoft 365, and SaaS apps | Legacy apps moved to Azure that cannot use modern authentication |

- **Microsoft Entra Connect** synchronizes user identities between on-premises Active Directory and Microsoft Entra ID, so users have one identity and get SSO, MFA, and self-service password reset whether the resource is on-premises or in the cloud. Without it you maintain two separate sets of identities.
- **Microsoft Entra Domain Services** gives you domain join, group policy, LDAP, and Kerberos/NTLM authentication without deploying, patching, or managing domain controllers. It integrates with your existing Microsoft Entra tenant, so users sign in to the managed domain with their existing credentials.
- When you create a managed domain you pick a unique domain name, and Azure deploys two Windows Server domain controllers (a **replica set**) into your chosen region. Azure handles backups, patching, and encryption at rest for them.
- Synchronization is **one-way, from Microsoft Entra ID to the managed domain**. Objects you create directly in the managed domain are not written back to Microsoft Entra ID. In a hybrid setup the flow is on-premises AD DS → Microsoft Entra Connect → Microsoft Entra ID → Microsoft Entra Domain Services.

> **Exam tip:** Microsoft Entra ID is not "Active Directory in the cloud": it has no domain join, group policy, or LDAP. If a lifted-and-shifted application needs those and the company does not want to manage domain controllers, the answer is Microsoft Entra Domain Services. If the stem says "synchronize on-premises accounts to the cloud", the answer is Microsoft Entra Connect.

#### Authentication methods (SSO, MFA, passwordless)

**Authentication** establishes who a person, service, or device is. **Authorization** decides what an authenticated identity is allowed to do. Authentication comes first.

| Method | Definition | Point to remember |
|---|---|---|
| Single sign-on (SSO) | Sign in once and use that one identity to reach multiple applications | Fewer passwords to remember and reset; access is tied to one identity, so removing access is simple; SSO is only as secure as the initial authenticator |
| Multifactor authentication (MFA) | Requires an additional factor during sign-in | A stolen password alone is not enough |
| Passwordless | Removes the password and replaces it with something you have plus something you are or know | High security and high convenience |

**MFA factor categories** (MFA needs two or more elements from different categories):

- **Something you know:** a password or the answer to a challenge question.
- **Something you have:** a mobile phone that receives a code or app notification, or a hardware key.
- **Something you are:** a biometric such as a fingerprint or face scan.

**Microsoft Entra multifactor authentication** is the Microsoft service that provides MFA, with additional verification such as a phone call or a mobile app notification.

**Passwordless options in Microsoft Entra ID:**

| Option | How it works | Best fit |
|---|---|---|
| Windows Hello for Business | Biometric or PIN tied to one specific Windows PC | Information workers with their own designated Windows PC |
| Microsoft Authenticator app | Phone notification; the user matches a number shown on the screen and confirms with a biometric or PIN | Anyone with an iOS or Android phone |
| FIDO2 security keys | Hardware key (USB, Bluetooth, or NFC) based on the open FIDO2/WebAuthn standard; resistant to phishing. Current Microsoft Entra documentation lists this method as passkeys (FIDO2) | Shared workstations and users who cannot or will not use a phone |

> **Exam tip:** A password plus a PIN is not MFA; both are "something you know". A password plus a code from a phone is MFA. A PIN in Windows Hello for Business is acceptable for passwordless because it is bound to the device (something you have).

> **Exam tip:** SSO reduces the number of credentials; MFA increases the strength of a sign-in; passwordless removes the password. They are complementary, not alternatives.

#### External identities

An **external identity** is a person, device, or service outside your organization's tenant. **Microsoft Entra External ID** is the set of capabilities for working with them securely. External users "bring their own identity" (a work account from another organization, or a social identity such as Google or Facebook): the external identity provider authenticates them, and you control authorization to your apps and resources.

| Capability | Who it is for | How the user appears |
|---|---|---|
| B2B collaboration | Partners, suppliers, vendors, and contractors who need your Microsoft apps or other enterprise apps | In your directory, typically as a **guest user** |
| B2B direct connect | Another Microsoft Entra organization, through a mutual two-way trust; currently used for Teams shared channels | Not represented in your directory |
| Customer-facing identity: Microsoft Entra External ID for customers (the replacement for Azure AD B2C) | Consumers and customers of the apps you publish | In a separate tenant used for customer identities |

- Naming: the AZ-900 training labels External ID for customers "formerly Azure AD B2C". Microsoft's product documentation is more precise: External ID is the next-generation customer identity platform, not a rename, and Azure AD B2C is the older service that new customers can no longer buy. For the exam, treat both names as the customer-facing option.
- Guests can be invited by administrators or by authorized users.
- **Access reviews** let you ask guests or a decision maker to confirm (recertify) that each guest still needs access, and remove access for those who do not.

> **Exam tip:** Partner employee signing in with their own company account to reach your resources = B2B collaboration (guest user). Members of the public signing up for your app with a social account = customer-facing External ID (the replacement for Azure AD B2C, which older material still names).

#### Microsoft Entra Conditional Access

**Conditional Access** is the Microsoft Entra ID tool that allows or denies access to resources based on identity **signals**. At sign-in it collects the signals, makes a **decision**, and **enforces** it.

| Stage | Examples |
|---|---|
| Signals | Who the user is (user or group, role), where the user is (location or network), the device being used, the application being accessed |
| Decision | Allow access, block access, or allow only after a further requirement is met |
| Enforcement | Access granted, access blocked, or the user is challenged for multifactor authentication |

Use Conditional Access to:

- Require MFA depending on the requester's role, location, or network (for example, MFA for administrators, or for anyone outside trusted locations).
- Allow access only through approved client applications.
- Allow access only from managed devices (devices that meet your security and compliance standards).
- Block access from untrusted sources such as unknown or unexpected locations.

> **Exam tip:** Conditional Access is "if this signal, then this access control". It gives a more granular MFA experience: no extra prompt at a known location, a prompt (or a block) when the sign-in looks unusual. It evaluates sign-ins; it does not define what a user may do to Azure resources (that is Azure RBAC).

#### Azure RBAC

**Azure role-based access control (Azure RBAC)** is the authorization system for Azure resources. It implements the **principle of least privilege**: grant only the access needed to do the job. Instead of granting permissions person by person, you assign **roles**.

A **role assignment** has three parts:

| Part | Meaning |
|---|---|
| Security principal (who) | A user, a group, or an application or service identity |
| Role definition (what) | A named collection of permissions; Azure supplies built-in roles and you can define custom roles |
| Scope (where) | The set of resources the access applies to: a management group, a subscription, a resource group, or a single resource |

**Built-in roles to know:**

| Role | Can do |
|---|---|
| Owner | Full access to manage all resources, including assigning roles to others |
| Contributor | Create and manage all types of resources, but cannot grant access to others |
| Reader | View resources; cannot make changes |
| User Access Administrator | Manage user access to Azure resources (assign roles), without managing the resources themselves |

- **Inheritance:** Azure RBAC is hierarchical. A role assigned at a parent scope is inherited by every child scope (see 2.1 for the hierarchy). Owner at a management group can manage everything in every subscription under it; Reader at a subscription can view every resource group and resource in it.
- **Allow model:** role assignments are additive. If one assignment grants read on a resource group and another grants write on the same resource group, you have both.
- **Enforcement:** Azure RBAC is enforced on every action against an Azure resource that passes through Azure Resource Manager (3.3), whether it comes from the Azure portal, Azure Cloud Shell, Azure PowerShell, or the Azure CLI. It does not enforce permissions at the application or data level inside your own application.
- Assigning a role to a group means new members receive the access automatically, and new resources created inside the scope are covered automatically.

> **Exam tip:** Owner vs Contributor: both can manage resources, only Owner can assign roles. "Can manage access but must not change resources" is User Access Administrator. "View only" is Reader.

> **Exam tip:** Scope order, broadest to narrowest: management group, subscription, resource group, resource. Assign at the narrowest scope that does the job. Azure RBAC authorizes people; Azure Policy (3.2) restricts what may be deployed; resource locks (3.2) block deletion or modification even for an Owner.

#### Zero Trust

**Zero Trust** is a security model that assumes the worst case and protects resources accordingly. It assumes breach at the outset and verifies every request as though it came from an uncontrolled network. It replaces the perimeter idea that anything inside the corporate network is safe: access is granted on the strength of authentication and context, not network location.

| Principle | Meaning |
|---|---|
| Verify explicitly | Always authenticate and authorize based on all available data points (identity, location, device, and so on) |
| Use least privilege access | Limit access with just-in-time and just-enough-access (JIT/JEA), risk-based adaptive policies, and data protection |
| Assume breach | Limit the potential impact and segment access, verify end-to-end encryption, and use analytics for visibility and threat detection |

> **Exam tip:** "Trusted because it is on the internal network" is the opposite of Zero Trust. Conditional Access is the practical way "verify explicitly" is applied at sign-in; Azure RBAC and JIT access apply "least privilege".

#### Defense-in-depth

**Defense-in-depth** is a strategy that places several layers of protection around data, so that if one layer is breached the next is already in place. Its objective is to protect information and prevent it from being stolen; it slows an attack and removes reliance on any single layer.

Layers from the outside in, with data at the center:

| # | Layer | Role | Examples |
|---|---|---|---|
| 1 | Physical security | First line of defense; protects computing hardware in the datacenter | Building access controls (Microsoft's responsibility in its datacenters) |
| 2 | Identity and access | Controls access to infrastructure and change control | SSO, MFA, auditing of sign-ins and changes |
| 3 | Perimeter | Protects against large-scale network-based attacks | DDoS protection, perimeter firewalls |
| 4 | Network | Limits communication between resources | Segmentation, deny by default, restricted inbound and outbound access, secure connectivity to on-premises |
| 5 | Compute | Secures access to virtual machines | Endpoint protection, patching |
| 6 | Application | Keeps applications secure and free of vulnerabilities | Secure development practices, secrets stored in Azure Key Vault rather than in code |
| 7 | Data | Controls access to business and customer data | Encryption at rest and in transit, access control to the data |

Azure Key Vault, which Microsoft Learn introduces alongside these layers, is the Azure service for securely storing and controlling access to secrets, encryption keys, and certificates.

> **Exam tip:** Memorize the order: physical, identity and access, perimeter, network, compute, application, data. DDoS protection belongs to the perimeter layer; limiting traffic between resources belongs to the network layer; patching VMs belongs to the compute layer.

> **Exam tip:** Defense-in-depth is about layers; Zero Trust is about never trusting by default. A question that lists "multiple layers of protection" is defense-in-depth even if it mentions identity.

#### Microsoft Defender for Cloud

**Microsoft Defender for Cloud** is a security posture management and threat protection service. It monitors cloud, on-premises, hybrid, and multicloud resources and gives you recommendations and alerts.

- **Azure-native:** it is built into Azure, so many Azure services are monitored and protected without any deployment.
- **Hybrid:** on-premises and other non-Azure machines are brought in through **Azure Arc** (3.3), which extends Defender plans to them.
- **Multicloud:** it can also protect resources in other clouds, including Amazon Web Services (AWS) and Google Cloud Platform (GCP), for example by extending posture recommendations, container protection, and server protection to them.

It meets three needs:

| Need | What Defender for Cloud does |
|---|---|
| Continuously assess | Shows your security posture and tracks vulnerabilities, including vulnerability assessment for virtual machines, container registries, and SQL servers |
| Secure | Hardens resources using policies built on Azure Policy and aligned to the **Microsoft cloud security benchmark**; produces prioritized **recommendations**, groups them into security controls, and calculates a **secure score** |
| Defend | Detects threats and raises **security alerts** that describe the affected resources and suggest remediation steps; provides workload protection for VMs, SQL databases, containers, web applications, and networks, with features such as just-in-time VM access and adaptive application controls |

- **Secure score** is a single measure of your security posture. A higher score means a lower identified risk; you raise it by remediating recommendations.
- **Recommendations** are the specific actions to take (for example, enable MFA or close a management port), produced as new resources are evaluated against best practices.

> **Exam tip:** "One place to see the security posture of Azure, on-premises, and other clouds, with a score and recommendations" is Microsoft Defender for Cloud. Azure Advisor (3.4) also gives security recommendations, but it is a general best-practice advisor that covers cost, reliability, performance, and operations as well; it does not detect threats or raise security alerts.

---

### Most-tested distinctions

- Region = a geographic area containing one or more datacenters. Availability zone = physically separate datacenters within one region (protects against a datacenter failure). Region pair = two regions in the same geography used for replication and disaster recovery (protects against a regional outage). Sovereign regions are isolated instances of Azure for government or legal compliance.
- Availability set = VMs spread across fault domains (shared power source and network switch; unplanned hardware failure) and update domains (rebooted together; planned maintenance) inside one datacenter. Virtual Machine Scale Set = a group of identical, load-balanced VMs that scales out and in automatically. Availability zone = placing VMs in different datacenters of a region.
- Virtual machine = IaaS, full control of the operating system. Container = lightweight, packages the app and its dependencies, no guest operating system to manage per app. Azure Functions = serverless, event-driven code that runs on demand and is billed while it runs. Azure App Service = PaaS hosting for web apps and APIs without managing servers.
- Azure Virtual Desktop = cloud-hosted Windows desktops and apps; not the same as a single Azure VM you connect to with remote desktop.
- VPN Gateway = encrypted tunnel over the public internet (site-to-site, point-to-site). ExpressRoute = private dedicated connection through a connectivity provider that does not travel over the public internet.
- Virtual network peering connects two virtual networks over the Microsoft backbone; VPN Gateway and ExpressRoute connect a virtual network to on-premises. Azure DNS hosts DNS domains; you cannot buy a domain name through it.
- Public endpoint = public IP address, reachable from the internet. Private endpoint = a network interface with a private IP address from your virtual network that connects to the service through Azure Private Link. Service endpoint = the service keeps its public endpoint but can be restricted to your subnet, with traffic on the Microsoft backbone.
- Resource = one manageable item. Resource group = logical container; each resource is in exactly one, and deleting the group deletes its resources. Subscription = billing and access boundary. Management group = container for subscriptions used to apply governance to many of them. Order: management groups, subscriptions, resource groups, resources.
- Blob = unstructured objects; Files = SMB/NFS shares; Queues = messages up to 64 KB; Tables = NoSQL; Disks = block volumes for VMs.
- Access tiers: hot (frequent access), cool (30 days), cold (90 days), archive (180 days, offline, must be rehydrated, takes hours). Archive is set per blob only; hot, cool, and cold can be the account default.
- LRS = 3 copies in one datacenter. ZRS = 3 copies across zones in one region. GRS = LRS plus 3 copies in the paired region. GZRS = ZRS plus 3 copies in the paired region. RA- prefix = the secondary can be read without a failover.
- Standard general-purpose v2 supports blobs, files, queues, and tables with every redundancy option; premium account types support one kind of data each and only LRS/ZRS (page blobs LRS only).
- Storage account name: 3 to 24 characters, lowercase letters and numbers, globally unique.
- AzCopy = command line, one-way sync. Storage Explorer = GUI on Windows, macOS, Linux. Azure File Sync = two-way sync between Windows Server and Azure Files, with cloud tiering.
- Azure Migrate = hub to discover, assess, and migrate servers, databases, and web apps online. Azure Data Box = physical device for offline bulk transfer, import or export.
- Microsoft Entra ID = cloud identity for sign-in to cloud apps. Microsoft Entra Domain Services = managed domain (domain join, group policy, LDAP, Kerberos/NTLM) with no domain controllers to manage. Microsoft Entra Connect = synchronization between on-premises AD and Microsoft Entra ID.
- Authentication = proving who you are; authorization = what you may do. SSO = one sign-in for many apps; MFA = two or more factor categories; passwordless = Windows Hello for Business, the Microsoft Authenticator app, FIDO2 security keys.
- B2B collaboration = partners as guest users in your directory; customer-facing External ID (the replacement for Azure AD B2C) = consumers of your apps.
- Conditional Access = signals (user, location, device, application) → decision → enforcement (allow, block, require MFA). Azure RBAC = who can do what to which Azure resources.
- Azure RBAC: role definition + security principal + scope; inherited downward; additive (allow model). Owner = everything including access; Contributor = everything except access; Reader = view; User Access Administrator = access only.
- Zero Trust: verify explicitly, use least privilege access, assume breach. Defense-in-depth layers: physical, identity and access, perimeter, network, compute, application, data.
- Microsoft Defender for Cloud = secure score, recommendations, security alerts, and workload protection across Azure, on-premises (through Azure Arc), and other clouds.

---

## Domain 3 — Azure Management and Governance (30–35%)

Objectives 3.1–3.4. This domain is mostly "which tool does this job": cost tools, governance tools, deployment tools, and monitoring tools. Nearly every question is a pick-the-right-service question, so learn the one-line purpose of each tool and the neighbor it gets confused with.

---

### 3.1 Describe cost management in Azure

#### Factors that affect costs

Azure bills on consumption (see 1.1): you rent resources and pay for what you use. Microsoft's training names six cost factors.

| Factor | What it means for the bill |
|---|---|
| **Resource type** | The kind of resource and its settings drive the price. Storage account: type of data, performance and access tier, redundancy, region. VM: operating system licensing, processor and core count, attached storage, network interface. |
| **Consumption** | Pay-as-you-go: use more in a billing cycle, pay more; use less, pay less. Commitment discounts (below) lower the rate for predictable usage. |
| **Maintenance** | Resources you forget still cost money. Deleting a VM can leave its disks, public IP address, and network interface behind. Organize with resource groups and remove what is no longer needed. |
| **Geography** | The same resource can cost a different amount in a different region, because power, labor, taxes, and fees vary by location. Geography also affects network traffic cost. |
| **Subscription type** | Some subscription types include usage allowances. An Azure free account includes a set of products free for 12 months, a credit to spend in the first 30 days, and a set of always-free products (the offer details change; the exam point is that the subscription type affects cost). |
| **Azure Marketplace** | Third-party solutions (preconfigured VMs, managed services, software). You pay for the underlying Azure services and may also pay the vendor; the vendor sets the billing structure. Marketplace offers are certified against Azure policies and standards. |

**Network traffic (part of geography).** Bandwidth is data moving into and out of Azure datacenters.

- Inbound data (ingress) is generally free.
- Outbound data (egress) is charged, priced by **billing zone**.
- A billing zone is a geographical grouping of Azure regions used only for data-transfer pricing. It has nothing to do with availability zones (2.1).
- Moving data within one geography is cheaper than moving it between continents.

> **Exam tip:** "Which factor affects cost?" answers are things like region, resource type and size, usage, outbound data, and Marketplace licensing. Distractors are things that are free or irrelevant: resource groups, tags, management groups, the number of users in Microsoft Entra ID, and inbound data transfer.

> **Exam tip:** Stopping (deallocating) a VM stops the compute charge but not the charge for its disks. Deleting the VM without its disks leaves the storage charge in place. That is the "maintenance" factor.

#### Pricing options that reduce cost

| Option | Commitment | Best for | Catch |
|---|---|---|---|
| **Pay-as-you-go** | None | Unpredictable or short-lived workloads | Highest rate |
| **Azure Reservations** | Specific resources (for example a VM size in a region, database capacity, storage capacity) for a one-year or three-year term | Stable, predictable, always-on workloads | Discount applies only to usage that matches what you reserved |
| **Azure savings plan for compute** | A fixed hourly spend on eligible compute services for one or three years | Steady compute spend that shifts between VM sizes, regions, or compute services | Compute only; usage above the commitment is billed pay-as-you-go |
| **Azure Spot Virtual Machines** | None | Interruptible work: batch jobs, rendering, dev/test that can restart | Azure can evict the VM when it needs the capacity back; no availability guarantee |
| **Azure Hybrid Benefit** | Existing on-premises licenses | Organizations that already own Windows Server or SQL Server licenses with Software Assurance (or qualifying subscriptions) | A licensing benefit, not a commitment discount. Microsoft's AZ-900 training module covers the other four options and not this one, so know only its one-line purpose |

> **Exam tip:** Reservation = commit to a specific resource. Savings plan = commit to an hourly dollar amount, flexible across compute. "Workload runs 24/7 on the same VM size for three years" is a reservation. "Compute usage is steady but moves between services and regions" is a savings plan.

> **Exam tip:** "Reuse the licenses we already bought for the on-premises datacenter" is Azure Hybrid Benefit. "Cheapest compute for a job that can be interrupted" is Spot.

#### The pricing calculator

A public web tool that estimates the cost of Azure resources **before** you deploy them.

- Add products, then configure region, tier or size, quantity, hours of use, redundancy, and pricing option; it returns an estimated monthly cost.
- Estimates individual resources, a whole solution, or a provided example scenario. Covers compute, storage, and associated network costs.
- For information only: the figures are estimates, **nothing is provisioned**, and you are not charged for anything you add.
- Typical use: compare regions, tiers, and redundancy options, then use the estimate as a baseline for budget approval.

The Total Cost of Ownership (TCO) calculator, which compared on-premises cost with Azure cost, has been retired and is no longer part of the exam outline.

> **Exam tip:** Pricing calculator = estimate what something *will* cost, before deployment, with no Azure subscription needed. Cost Management = see and control what you *are* spending, on resources that already exist.

#### Cost management capabilities

**Microsoft Cost Management** is the set of tools in the Azure portal for analyzing, monitoring, and controlling Azure spend.

| Capability | What it does |
|---|---|
| **Cost analysis** | Visual breakdown of actual cost. View by billing cycle, subscription, resource group, service, region, resource, or tag; see accumulated cost over time and forecast against a budget; spot trends and sudden increases. |
| **Budgets** | A spending limit you define for a scope (subscription, resource group, service type, and so on). Reaching a threshold triggers a budget alert and can trigger automation, for example shutting down nonproduction resources. |
| **Cost alerts** | One place that lists every alert Cost Management has raised. Three types, below. |

| Cost alert type | Triggered when | Applies to |
|---|---|---|
| **Budget alert** | Spending (or, through the API, usage) reaches a threshold of a budget you created | Any customer with a budget |
| **Credit alert** | Azure Prepayment (formerly monetary commitment) is consumed; generated automatically at 90% and 100% of the balance | Enterprise Agreement customers |
| **Department spending quota alert** | Department spending reaches a fixed threshold of its quota (for example 50% or 75%) | Enterprise Agreement customers |

> **Exam tip:** A budget does not stop spending by itself. It notifies, and it can run automation that you configure. If a question says "prevent the deployment of expensive VM sizes," that is Azure Policy (3.2), not a budget.

> **Exam tip:** Azure Advisor (3.4) *recommends* cost savings (idle or oversized resources, reservation purchases). Cost Management *reports and alerts* on spend. Both live in the portal and both mention cost; pick by verb.

#### Tags

A tag is a **name–value pair** of metadata attached to a resource, resource group, or subscription, for example `Environment = Prod` or `CostCenter = 4410`. Tags organize resources across resource group and subscription boundaries.

| Use | Example |
|---|---|
| Resource management | Find every resource belonging to a workload, environment, team, or owner |
| Cost management and optimization | Group cost by cost center or department in cost analysis; track budgets; forecast |
| Operations management | Mark business criticality to drive SLAs and response priority |
| Security | Classify data, such as public or confidential |
| Governance and regulatory compliance | Identify resources subject to a standard; require an owner or department tag |
| Workload optimization and automation | Let automation select the resources that belong to an application |

- Manage tags through the Azure portal, Azure PowerShell, the Azure CLI, ARM templates, or the REST API.
- **Tags are not inherited.** A resource does not pick up the tags of its resource group or subscription.
- Use **Azure Policy** (3.2) to require a tag on new resources, to add a missing tag, or to copy a tag down from the resource group.
- Not every resource needs every tag; a tagging scheme can differ by level.

> **Exam tip:** "Report cost by department when departments share subscriptions and resource groups" is tags plus cost analysis. "Make sure every resource has a CostCenter tag" is Azure Policy. Resource groups organize by life cycle; tags organize by any attribute you choose.

---

### 3.2 Describe features and tools in Azure for governance and compliance

#### Microsoft Purview

A family of **data governance, risk, and compliance** solutions that gives a single, unified view of an organization's data. It governs *data*, not Azure resources.

- Brings together insight about data held **on-premises, in multiple clouds, and in software as a service (SaaS)** applications.
- Core capabilities: **automated data discovery**, **sensitive data classification**, and **end-to-end data lineage** (where data came from and how it moved and changed).

| Solution area | What it covers |
|---|---|
| **Risk and compliance** | Built around Microsoft 365 services such as Teams, OneDrive, and Exchange. Protect sensitive data across clouds, apps, and devices; identify data risks; manage regulatory compliance. |
| **Unified data governance** | Data in Azure, SQL and Hive databases, on-premises stores, and other clouds such as Amazon S3. Build an up-to-date **map** of the data estate with classification and lineage; identify where sensitive data lives; give data consumers a secure **catalog** in which to find data; generate insight into how data is stored and used; manage access to data at scale. |

> **Exam tip:** Keywords for Purview: data estate, data map, data catalog, classification, lineage, sensitive data, multicloud data. If the question is about rules for *resources* (allowed regions, required tags), it is Azure Policy. If it is about security posture of workloads, it is Microsoft Defender for Cloud (2.4).

#### Azure Policy

A service for creating, assigning, and managing policies that **control or audit resource configuration** so that resources stay compliant with organizational standards.

| Term | Meaning |
|---|---|
| **Policy definition** | One rule: a condition and the effect to apply when it is met. Example: allowed locations, allowed VM sizes, require a tag. Azure supplies many built-in definitions; you can write custom ones. |
| **Initiative** | A group of related policy definitions managed and tracked as a single unit toward one larger goal. An initiative can hold a hundred or more definitions. |
| **Assignment** | Applying a definition or initiative to a **scope**: management group, subscription, resource group, or individual resource. |
| **Inheritance** | An assignment applies to everything under its scope. Assign at a management group and every subscription, resource group, and resource beneath it is covered. |
| **Exclusion** | A child scope or resource can be marked as an exception to an assignment. |

How it behaves:

- Evaluated when a resource is **created or changed** (creating a VM, resizing a VM) and can **prevent** a noncompliant resource from being created.
- Also evaluates **existing resources**, including ones created before the policy was assigned, and reports them as noncompliant. Existing resources are flagged, not deleted.
- The compliance view highlights which resources and which policies are out of compliance.
- **Remediation:** in some cases Azure Policy can fix noncompliant resources automatically, for example adding a required tag that is missing.
- Integrates with Azure DevOps to apply policy in deployment pipelines.
- Applies no matter how the change is made: portal, CLI, template, or an AI-assisted tool.

| Common effect | Result |
|---|---|
| **Deny** | The noncompliant create or update request is blocked |
| **Audit** | The request is allowed; the resource is reported as noncompliant |
| **Append / Modify** | Adds or changes properties, such as tags, on the resource |
| **DeployIfNotExists** | Deploys a related resource or setting when it is missing (used for remediation) |

**Azure Policy vs Azure RBAC**

| | Azure Policy | Azure RBAC (2.4) |
|---|---|---|
| Question it answers | What state must resources be in? | Who can do what? |
| Focus | Resource properties, at deployment and for existing resources | User, group, and application actions at a scope |
| Example | Only allow resources in two regions | Allow the help desk to restart VMs but not delete them |
| Default | Explicit deny: a request is allowed unless an assigned policy denies it | Explicit allow: an action is refused unless a role assignment grants it |

> **Exam tip:** A user with the Owner role can still be blocked by a Deny policy. RBAC lets the user attempt the action; Policy decides whether the resulting resource is acceptable. The two work together.

> **Exam tip:** "Group several policies and assign them together" is an initiative. Do not answer management group (a container for subscriptions) or resource group.

#### Resource locks

A lock prevents a resource from being **accidentally deleted or changed**, regardless of who is making the request.

| Lock (portal name) | Read | Modify | Delete |
|---|---|---|---|
| **Delete** (CanNotDelete) | Yes | Yes | No |
| **ReadOnly** | Yes | No | No |

- Apply at the **subscription, resource group, or individual resource** level. A lock cannot be placed on a management group.
- **Inherited:** a lock on a resource group applies to every resource in it, including resources added later.
- ReadOnly is similar to limiting every user to the Reader role for that scope.
- Locks **apply regardless of RBAC permissions**. Even an Owner must **remove the lock first**, then perform the action: a deliberate two-step process.
- Manage locks from the Azure portal (Settings > Locks), Azure PowerShell, the Azure CLI, or an ARM template.

> **Exam tip:** "An administrator with Owner rights cannot delete a resource group" points to a lock. "Protect against accidental deletion but still allow configuration changes" is a Delete lock. "Nobody may change it at all" is ReadOnly.

> **Exam tip:** Three governance tools, three jobs. RBAC: who may act. Policy: what configurations are allowed. Locks: protect a specific resource from change or deletion by anyone.

---

### 3.3 Describe features and tools for managing and deploying Azure resources

#### Azure portal

A **web-based, unified console** with a graphical user interface, the alternative to command-line tools.

- Build, manage, and monitor everything from a single web app to complex deployments.
- Create **custom dashboards** for an organized view of resources; configure accessibility options.
- Designed for continuous availability: it has a presence in every Azure datacenter, is resilient to an individual datacenter failure, updates continuously, and needs no maintenance downtime.
- Best for one-off tasks, exploring services, and viewing reports. Not well suited to repeating the same deployment many times, because every step is manual.

#### Azure Cloud Shell, Azure CLI, and Azure PowerShell

**Azure Cloud Shell** is a **browser-based shell**, opened from the Cloud Shell icon in the portal.

- No local installation or configuration required.
- Already authenticated with your Azure credentials, so it knows who you are and what you may do.
- You choose the shell: **Bash** (with the Azure CLI) or **PowerShell** (with Azure PowerShell).

| | Azure CLI | Azure PowerShell |
|---|---|---|
| Command style | Bash-style commands that start with `az`, for example `az vm create` | Cmdlets in Verb-Noun form, for example `New-AzVM` |
| Natural fit | Administrators who know Bash and Linux | Administrators who know PowerShell and Windows |
| Runs on | Windows, Linux, macOS, and Cloud Shell | Windows, Linux, macOS, and Cloud Shell |
| Capability | Functionally equivalent: both call the Azure REST API through Azure Resource Manager | |

- Both can run single commands for one-off changes or be combined into **scripts** that set up, tear down, and maintain many resources. A script makes the process repeatable and automatable.
- The choice between them is mainly which syntax the team already knows.

> **Exam tip:** Cloud Shell is where you run commands; the CLI and PowerShell are what you run. "Manage Azure from a tablet or a locked-down PC with nothing installed" is Cloud Shell (or the portal). "Bash" in the stem leans Azure CLI; "cmdlets" leans Azure PowerShell.

> **Exam tip:** Both tools run on all three desktop operating systems. "Azure PowerShell only runs on Windows" and "the Azure CLI only runs on Linux" are false statements.

#### Azure Arc

Azure Arc **extends Azure management and governance to resources outside Azure**: on-premises datacenters, the edge, and other public clouds. It works with Azure Resource Manager by **projecting non-Azure resources into ARM**, so they appear and are managed like Azure resources.

- One consistent management platform for hybrid and multicloud environments.
- Apply familiar Azure capabilities to those resources: Azure Policy, tags, RBAC, inventory, and monitoring.
- Keep traditional IT operations while introducing DevOps practices.

Resource types Azure Arc can manage outside Azure: **servers**, **Kubernetes clusters**, **Azure data services**, **SQL Server**, and **virtual machines** (listed as preview in Microsoft's training).

> **Exam tip:** Arc manages; it does not move or connect. Migrating servers into Azure is Azure Migrate (2.3). A private network link is VPN Gateway or ExpressRoute (2.2). "Apply Azure Policy to servers running in another cloud" is Azure Arc.

#### Infrastructure as code (IaC)

Managing infrastructure through **code and templates instead of manual configuration**. The definition lives in files that can be version-controlled, reviewed, and reused.

- Benefits: consistent environments (dev, test, and production built from the same definition), repeatable deployments, less human error, faster provisioning, and a change history.
- It can start with Azure CLI or Azure PowerShell scripts and grow into ARM templates and Bicep.

| Approach | You write | Examples |
|---|---|---|
| **Imperative** | The steps to run, in order | Azure CLI and Azure PowerShell scripts |
| **Declarative** | The desired end state; the platform works out the steps | ARM templates, Bicep |

#### Azure Resource Manager (ARM) and ARM templates

**Azure Resource Manager** is the **deployment and management service** for Azure: the management layer through which resources are created, updated, and deleted.

- Every request, from the portal, the CLI, PowerShell, SDKs, or the REST API, goes to ARM. ARM **authenticates and authorizes** it, then passes it to the Azure service. Because all tools use the same API, results are consistent across tools.
- ARM lets you: deploy, manage, and monitor a solution's resources **as a group**; redeploy throughout the life cycle with a consistent result; define **dependencies** so resources deploy in the right order; apply **RBAC** (natively integrated); apply **tags** and **locks**.

**ARM templates** are **JSON files** that declare the resources you want.

| Benefit | Meaning |
|---|---|
| **Declarative syntax** | State what to deploy, not the commands to deploy it |
| **Repeatable results** | Templates are **idempotent**: deploying the same template again yields the same resources in the same state, without duplicates |
| **Orchestration** | ARM works out dependency order and deploys resources in parallel where it can |
| **Modularity** | Break a deployment into smaller reusable templates and nest them |
| **Extensibility** | Run PowerShell or Bash deployment scripts for steps before or after resource creation |

ARM validates a template before it deploys anything.

**Bicep** is a declarative language for the same job, deployed through ARM. Its syntax is simpler and more concise than JSON. Benefits: support for current resource types and API versions, simple syntax, repeatable (idempotent) deployments, built-in orchestration, and modularity through Bicep modules.

> **Exam tip:** ARM is the service; an ARM template is a file. "Which component handles a request made in the portal?" is Azure Resource Manager. "Deploy the same 30 resources identically to three environments" is an ARM template or Bicep file.

> **Exam tip:** ARM template = JSON. Bicep = its own, shorter language. Both are declarative. Scripts in the CLI or PowerShell are imperative.

---

### 3.4 Describe monitoring tools in Azure

#### Azure Advisor

Evaluates your deployed resources and gives **personalized recommendations** based on best practices. Each recommendation comes with a suggested action that you can take immediately, postpone, or dismiss.

| Category | What it recommends |
|---|---|
| **Reliability** | Configuration risks to fix so that business-critical applications keep running (the Advisor API and CLI still label this category HighAvailability) |
| **Security** | Fixes for threats and vulnerabilities that could lead to a breach |
| **Performance** | Changes that speed up applications |
| **Operational Excellence** | Process, workflow, and deployment best practices |
| **Cost** | Ways to reduce spend, such as resizing or shutting down underused resources |

- The dashboard covers all your subscriptions and filters by subscription, resource group, or service.
- Available in the portal and through an API; you can set up notifications for new recommendations.
- Advisor recommends. It does not make the change for you and does not report outages.

> **Exam tip:** The five categories are a recall item. "Scalability," "compliance," and "availability zones" are not Advisor categories.

#### Azure Service Health

Tracks the health of the Azure platform itself, in three views that narrow from global to a single resource.

| View | Scope | Use it when |
|---|---|---|
| **Azure Status** | All Azure services in all regions; a public status page, not personalized | You hear about a widespread outage and want the global picture |
| **Service Health** | Only the services and regions **you use**, because you are signed in. Shows service issues (outages), **planned maintenance**, and **health advisories** | You want to know whether an incident or upcoming maintenance affects your environment; you want an alert when it does |
| **Resource Health** | An **individual resource** of yours, such as one VM. Shows whether it is available and whether the problem is on Azure's side or yours | One specific resource is misbehaving |

- You can create **Service Health alerts** to be notified automatically.
- Historical events are retained so you can spot recurring trends, and events link to support.

> **Exam tip:** Service Health tells you about problems with *Azure*. Azure Monitor tells you about the behavior of *your* resources and applications. "Be notified of planned maintenance in the regions we use" is Service Health.

> **Exam tip:** Personalized or not is the split between Azure Status (everyone sees the same page) and Service Health (filtered to your subscriptions).

#### Azure Monitor

The platform for **collecting, analyzing, and acting on** telemetry from Azure, on-premises, and multicloud resources and applications. It gathers data from applications, operating systems, and network layers, stores it centrally, and exposes it through dashboards, queries, and alerts.

| Data type | What it is | Good for |
|---|---|---|
| **Metrics** | Numeric values sampled at regular intervals (CPU percentage, request count) | Near-real-time charts and fast alerting |
| **Logs** | Records of events and traces with varied structure, stored in a Log Analytics workspace | Detailed analysis, correlation, troubleshooting |

| Feature | Purpose |
|---|---|
| **Log Analytics** | The tool in the portal for writing and running **queries** against collected log data, using the **Kusto Query Language (KQL)**. From a simple filter ("all errors in the last hour") to trend analysis and visualization. |
| **Azure Monitor alerts** | Notify you, and optionally act, when a condition you defined is met. An **alert rule** holds the condition; an **action group** holds who is notified and what happens (email, SMS, automation). Alerts can be **metric-based** (a VM's CPU stays above 80%) or **log-based** (a specific error pattern across many resources). Action groups are reusable across Azure Monitor, Service Health, and Azure Advisor. |
| **Application Insights** | Monitors the **performance and usage of web applications**, whether they run in Azure, on-premises, or in another cloud. Enable it by adding an SDK to the code or by using the agent with no code change. |

Application Insights can monitor:

- Request rates, response times, and failure rates
- Dependency calls and their performance
- Page load times, user counts, and session trends
- Server performance counters such as CPU, memory, and network usage
- **Availability tests:** synthetic requests sent on a schedule to confirm that the application responds, even when no real users are active

> **Exam tip:** Advisor = recommendations. Service Health = Azure platform incidents and maintenance. Monitor = your telemetry. Application Insights = inside your application. Log Analytics = query the logs.

> **Exam tip:** An alert rule decides *when*; an action group decides *who and what*. "Notify the on-call team by SMS" is configured in the action group.

---

### Most-tested distinctions

- Pricing calculator estimates cost before deployment and provisions nothing; Cost Management analyzes and controls actual spend. The TCO calculator is retired.
- Cost factors: resource type, consumption, maintenance, geography (including network traffic), subscription type, Azure Marketplace. Resource groups, tags, and management groups are free.
- Inbound data is generally free; outbound data is charged by billing zone. Billing zones are not availability zones.
- Reservation = commit to specific resources for one or three years; savings plan for compute = commit to an hourly spend, flexible across compute; Spot = unused capacity, can be evicted; Hybrid Benefit = reuse existing licenses.
- Cost analysis shows where money goes; a budget sets a threshold; cost alerts are budget, credit, and department spending quota (the last two are Enterprise Agreement only).
- A budget notifies and can trigger automation; it does not block deployments. Azure Policy blocks deployments.
- Tags are name–value metadata, not inherited from the resource group or subscription; Azure Policy enforces or inherits them.
- Microsoft Purview governs data (map, catalog, classification, lineage) across on-premises, multicloud, and SaaS; Azure Policy governs resource configuration.
- Policy definition = one rule; initiative = a group of definitions; assignment = applying either to a scope; assignments are inherited by child scopes.
- Azure Policy evaluates new and existing resources; existing noncompliant resources are flagged, not deleted; some can be remediated automatically.
- RBAC = who can do what; Azure Policy = what resources may look like; resource lock = nobody changes or deletes this until the lock is removed.
- Delete lock allows read and modify; ReadOnly allows read only. Locks are inherited and apply even to Owners.
- Azure portal = web GUI; Cloud Shell = browser-based shell with Bash or PowerShell, nothing to install; Azure CLI = `az` commands; Azure PowerShell = cmdlets. CLI and PowerShell are functionally equivalent and cross-platform.
- Azure Arc projects servers, Kubernetes clusters, Azure data services, SQL Server, and VMs outside Azure into Azure Resource Manager; it manages, it does not migrate.
- Azure Resource Manager is the single management layer every tool goes through; it authenticates and authorizes each request.
- ARM templates are declarative JSON, idempotent, orchestrated, and modular; Bicep is a simpler declarative language for the same deployments. CLI and PowerShell scripts are imperative.
- Azure Advisor categories: Reliability, Security, Performance, Operational Excellence, Cost.
- Azure Status = global public page; Service Health = your services and regions, including planned maintenance; Resource Health = one of your resources.
- Azure Monitor collects metrics (numeric, time-based) and logs (event records); Log Analytics queries logs with KQL; an alert rule plus an action group makes an alert; Application Insights monitors web applications.

---

## Service Picker

"The requirement says X, the answer is Y." Find the deciding words in the stem, then look them up here. Objective numbers point to the chapter section.

> **Exam tip:** Most AZ-900 service questions turn on one phrase. Underline it before reading the options.

### Compute (2.2)

| The requirement says | The answer is |
|---|---|
| Full control of the operating system; lift and shift an existing server; custom software | Azure Virtual Machines |
| Many identical, load-balanced VMs that scale out and in automatically | Virtual Machine Scale Sets |
| Keep a group of VMs from sharing one hardware failure or one maintenance reboot (fault and update domains) | Availability set |
| Windows desktops and apps delivered from Azure to any device; multi-session Windows | Azure Virtual Desktop |
| Run a single container quickly without managing VMs or an orchestrator | Azure Container Instances |
| Run containers with scale to zero and no cluster management | Azure Container Apps |
| Orchestrate many containers with Kubernetes | Azure Kubernetes Service |
| Run a small piece of code in response to an event or timer; pay only while it runs | Azure Functions |

### Application hosting (2.2)

| The requirement says | The answer is |
|---|---|
| Host a website or REST API without managing servers; built-in scaling and deployment | Azure App Service (web apps, API apps) |
| Package the app with its dependencies so it runs the same everywhere | Containers |
| The app needs settings or software only possible with OS-level access | Virtual machines |
| No infrastructure to manage and no charge while idle | Serverless (Azure Functions) |

### Networking and connectivity (2.2)

| The requirement says | The answer is |
|---|---|
| Private, isolated network in Azure for resources to communicate | Azure Virtual Network |
| Segment a virtual network into address ranges | Subnets |
| Connect two virtual networks so traffic stays on the Microsoft backbone | Virtual network peering |
| Encrypted tunnel over the public internet from a datacenter to Azure | Azure VPN Gateway, site-to-site |
| Encrypted connection from one laptop to Azure | Azure VPN Gateway, point-to-site |
| Private, dedicated connection to Azure that does not use the public internet | Azure ExpressRoute |
| Host DNS domains and manage records with Azure tools and credentials | Azure DNS |
| Reach a service at an address reachable from the internet | Public endpoint |
| Reach an Azure service through a private IP address inside your virtual network | Private endpoint |

### Storage (2.3)

| The requirement says | The answer is |
|---|---|
| Massive amounts of unstructured data: images, video, backups, logs | Azure Blob Storage |
| Managed file share over SMB or NFS that can be mounted from cloud and on-premises | Azure Files |
| Store messages so application components can process them asynchronously | Azure Queue Storage |
| Simple key/attribute store for structured, non-relational data | Azure Table Storage |
| Block-level volumes for virtual machines | Azure managed disks |
| Data accessed frequently | Hot tier |
| Data accessed infrequently, kept at least 30 days, still available immediately | Cool tier |
| Data rarely accessed, kept at least 90 days, still available immediately | Cold tier |
| Data rarely accessed, kept at least 180 days, retrieval in hours is acceptable; lowest storage cost | Archive tier |
| Lowest-cost redundancy; protection against drive and rack failure only | LRS |
| Survive the loss of a datacenter in the region, data stays in the region | ZRS |
| Survive the loss of the whole region | GRS |
| Survive the loss of a zone and of the region | GZRS |
| Read from the secondary region while the primary is still healthy or during an outage | RA-GRS or RA-GZRS |
| One account for blobs, files, queues, and tables | Standard general-purpose v2 storage account |

### Data transfer and migration (2.3)

| The requirement says | The answer is |
|---|---|
| Command-line or scripted copy of blobs or files to, from, or between storage accounts | AzCopy |
| Graphical desktop app to browse and manage storage on Windows, macOS, or Linux | Azure Storage Explorer |
| Keep an on-premises Windows file server in sync with Azure Files; cache hot files locally | Azure File Sync |
| Discover, assess, and migrate on-premises servers, databases, and web apps | Azure Migrate |
| Move a very large amount of data offline because the network is slow or costly | Azure Data Box |

### Identity and access (2.4)

| The requirement says | The answer is |
|---|---|
| Cloud identity and access management for Azure, Microsoft 365, and SaaS apps | Microsoft Entra ID |
| Domain join, group policy, LDAP, Kerberos or NTLM in Azure without deploying domain controllers | Microsoft Entra Domain Services |
| Sign in once and reach many applications | Single sign-on |
| Require a second proof of identity at sign-in | Multifactor authentication |
| Sign in with a biometric, a FIDO2 key, or the Authenticator app instead of a password | Passwordless authentication |
| Let partners, vendors, or customers sign in with their own identities | Microsoft Entra External ID |
| Allow or block sign-in, or require MFA, based on user, location, device, or risk | Microsoft Entra Conditional Access |
| Grant a user only the permissions needed on a resource, resource group, or subscription | Azure RBAC |

### Security (2.4)

| The requirement says | The answer is |
|---|---|
| "Never trust, always verify"; verify explicitly, least privilege, assume breach | Zero Trust |
| Several layers of protection so one failed control does not expose data | Defense in depth |
| Secure score, security recommendations, and threat protection across Azure, on-premises, and other clouds | Microsoft Defender for Cloud |

### Governance and compliance (3.2)

| The requirement says | The answer is |
|---|---|
| Enforce or audit rules on resources: allowed regions, allowed VM sizes, required tags | Azure Policy |
| Group related policies toward one goal | Policy initiative |
| Prevent accidental deletion of a resource | Resource lock: Delete (CanNotDelete) |
| Prevent any change to a resource | Resource lock: ReadOnly |
| Discover, classify, and govern data across on-premises, multicloud, and SaaS | Microsoft Purview |
| Apply policy or access to many subscriptions at once | Management group |

### Cost (3.1)

| The requirement says | The answer is |
|---|---|
| Estimate the cost of resources before deploying them | Pricing calculator |
| Analyze actual spending, set budgets, and get cost alerts | Microsoft Cost Management |
| Be notified when spending reaches a threshold | Budget with a cost alert |
| Attribute cost to a department, project, or environment | Tags |
| Discount for committing to a specific resource type in a region for one or three years | Azure Reservations |
| Discount for committing to a fixed hourly spend on compute across services and regions | Azure savings plan for compute |
| Find idle or underused resources to cut cost | Azure Advisor, cost recommendations |

### Deployment and management (3.3)

| The requirement says | The answer is |
|---|---|
| Web-based graphical console for managing resources | Azure portal |
| Browser-based shell with nothing to install; Bash or PowerShell | Azure Cloud Shell |
| Cross-platform command line using `az` commands | Azure CLI |
| Command line using cmdlets such as `New-AzVM` | Azure PowerShell |
| Manage servers and Kubernetes clusters that run on-premises or in other clouds with Azure tools | Azure Arc |
| Deployment and management layer that every tool and request goes through | Azure Resource Manager |
| Declarative JSON file that deploys the same resources repeatedly | ARM template |
| Declarative deployment with a simpler syntax than JSON | Bicep |
| Define infrastructure in versioned files instead of manual steps | Infrastructure as code |

### Monitoring (3.4)

| The requirement says | The answer is |
|---|---|
| Personalized best-practice recommendations for your resources | Azure Advisor |
| Status of all Azure services in all regions | Azure Status page |
| Outages and planned maintenance for the services and regions you use | Azure Service Health |
| Health of one specific resource, such as a single VM | Resource Health |
| Collect and analyze metrics and logs from Azure and on-premises resources | Azure Monitor |
| Query collected log data with KQL | Log Analytics |
| Be notified or trigger an action when a metric or log crosses a threshold | Azure Monitor alerts |
| Monitor a web application's performance, failures, and usage | Application Insights |

### Sounds alike, is not

| Pair | The difference |
|---|---|
| Azure Policy vs. Azure RBAC | Policy controls what resources may be or do; RBAC controls what a person or app may do |
| Azure RBAC vs. resource lock | RBAC grants permissions per identity; a lock blocks delete or change for everyone, including owners, until it is removed |
| Tags vs. resource groups | Tags are metadata for reporting; a resource group is a container a resource must belong to. Tags are not inherited by default |
| Microsoft Entra ID vs. Microsoft Entra Domain Services | Entra ID is cloud identity using modern protocols; Domain Services provides managed traditional domain services |
| Microsoft Entra ID vs. Active Directory Domain Services | Entra ID is not a domain controller in the cloud; it has no group policy and uses a flat structure |
| Conditional Access vs. MFA | MFA is one authentication requirement; Conditional Access is the if-then policy that decides when to require it |
| Availability set vs. availability zone | A set spreads VMs across racks in one datacenter; zones are separate datacenters in one region |
| Availability zone vs. region pair | Zones protect against a datacenter failure; a region pair protects against a regional disaster |
| Scale set vs. availability set | A scale set creates and scales identical VMs; an availability set only places VMs you create |
| VPN Gateway vs. ExpressRoute | VPN is encrypted over the internet; ExpressRoute is a private circuit that bypasses the internet |
| Peering vs. VPN Gateway | Peering joins Azure virtual networks; a VPN gateway joins a virtual network to an outside network |
| Azure Files vs. Blob Storage | Files is a mountable share with a directory tree; Blob is object storage reached over HTTP |
| Azure File Sync vs. AzCopy | File Sync keeps a server and a share continuously in sync; AzCopy is a one-time or scripted copy |
| Azure Migrate vs. Azure Data Box | Migrate assesses and moves workloads; Data Box ships data on a physical device |
| Cool vs. cold vs. archive | Cool and cold are online; archive is offline and must be rehydrated before reading |
| GRS vs. RA-GRS | Both copy to a secondary region; only RA-GRS lets you read the secondary without a failover |
| Pricing calculator vs. Cost Management | The calculator estimates before you deploy; Cost Management reports and controls what you already spend |
| Reservation vs. savings plan | A reservation commits to a specific resource; a savings plan commits to an hourly amount and is more flexible |
| Advisor vs. Service Health | Advisor recommends improvements; Service Health reports Azure incidents and maintenance |
| Service Health vs. Azure Monitor | Service Health is about the Azure platform; Monitor is about your own resources' metrics and logs |
| Azure Monitor vs. Defender for Cloud | Monitor covers performance and availability telemetry; Defender for Cloud covers security posture and threats |
| Azure CLI vs. Azure PowerShell | Same capabilities; `az` commands versus `Az` cmdlets. Both run in Cloud Shell |
| Azure Resource Manager vs. ARM template | The service versus a file submitted to it |
| Azure Arc vs. Azure Migrate | Arc manages resources where they are; Migrate moves them to Azure |
| Scalability vs. elasticity | Scalability is the ability to add resources; elasticity is doing so automatically, up and down, with demand |
| High availability vs. reliability | Availability is uptime, backed by an SLA; reliability is the ability to recover from failure and keep working |

---

## Acronyms

AZ-900 acronym list: acronym, expansion, one-line meaning. Where an acronym has two meanings, both are noted.

Jump: [A](#a) [B](#b) [C](#c) [D](#d) [E](#e) [F](#f) [G](#g) [H](#h) [I](#i) [J](#j) [K](#k) [L](#l) [M](#m) [N](#n) [O](#o) [P](#p) [R](#r) [S](#s) [T](#t) [U](#u) [V](#v) [W](#w) [Z](#z)

### A

| Acronym | Expansion | Meaning |
|---|---|---|
| ACI | Azure Container Instances | Runs a container on demand without managing VMs or an orchestrator |
| ACR | Azure Container Registry | Private registry for storing container images |
| AD | Active Directory | Microsoft's on-premises directory service; usually means AD DS |
| AD DS | Active Directory Domain Services | Traditional Windows domain services: domain join, group policy, LDAP, Kerberos/NTLM |
| AI | Artificial Intelligence | Software that performs tasks associated with human intelligence |
| AKS | Azure Kubernetes Service | Managed Kubernetes for orchestrating containers |
| API | Application Programming Interface | Defined way for software components to communicate |
| ARM | Azure Resource Manager | Deployment and management layer for all Azure resources; every tool sends requests through it |
| AVD | Azure Virtual Desktop | Desktop and app virtualization service that runs in Azure |
| Azure AD | Azure Active Directory | Former name of Microsoft Entra ID |

### B

| Acronym | Expansion | Meaning |
|---|---|---|
| B2B | Business-to-Business | External collaboration: partners sign in with their own identities as guests |
| B2C | Business-to-Consumer | Customer-facing identity for apps you publish to the public |
| BCDR | Business Continuity and Disaster Recovery | Keeping the business running through, and recovering after, a major outage |
| BGP | Border Gateway Protocol | Routing protocol used to exchange routes, for example over ExpressRoute |

### C

| Acronym | Expansion | Meaning |
|---|---|---|
| CapEx | Capital Expenditure | Up-front spending on physical assets such as servers and buildings |
| CDN | Content Delivery Network | Distributed servers that cache content close to users |
| CI/CD | Continuous Integration and Continuous Delivery | Automated build, test, and release pipeline; often deploys infrastructure as code |
| CIDR | Classless Inter-Domain Routing | Address notation such as 10.0.0.0/16 used for virtual network and subnet ranges |
| CLI | Command-Line Interface | Text-based tool; the Azure CLI uses `az` commands |
| CPU | Central Processing Unit | The processor; VM sizes are defined partly by vCPU count |
| CSP | Cloud Service Provider | Company that offers cloud services, such as Microsoft; also the Cloud Solution Provider partner program |
| CSPM | Cloud Security Posture Management | Assessing configuration against security best practices; a pillar of Defender for Cloud (secure score) |
| CWPP | Cloud Workload Protection Platform | Threat protection for workloads such as servers, containers, storage, and databases; a pillar of Defender for Cloud |

### D

| Acronym | Expansion | Meaning |
|---|---|---|
| DDoS | Distributed Denial of Service | Attack that floods a service with traffic from many sources; addressed at the perimeter layer |
| DLP | Data Loss Prevention | Policies that detect and stop sensitive data from leaving; part of Microsoft Purview |
| DNS | Domain Name System | Resolves names to IP addresses; Azure DNS hosts DNS domains |
| DR | Disaster Recovery | Restoring service after a major failure, often in another region |

### E

| Acronym | Expansion | Meaning |
|---|---|---|
| EA | Enterprise Agreement | Volume purchasing agreement for large organizations |

### F

| Acronym | Expansion | Meaning |
|---|---|---|
| FaaS | Function as a Service | Serverless model that runs code in response to events, such as Azure Functions |
| FIDO2 | Fast Identity Online 2 | Open standard for passwordless sign-in with security keys or platform authenticators |
| FQDN | Fully Qualified Domain Name | Complete DNS name of a host, such as app.contoso.com |

### G

| Acronym | Expansion | Meaning |
|---|---|---|
| GDPR | General Data Protection Regulation | European Union privacy regulation; an example of a compliance requirement |
| GPO | Group Policy Object | Windows domain settings object; supported by AD DS and Microsoft Entra Domain Services, not by Microsoft Entra ID |
| GPU | Graphics Processing Unit | Processor for graphics and parallel compute; available in certain VM sizes |
| GPv2 | General-Purpose v2 | Standard storage account type that supports blobs, files, queues, and tables |
| GRS | Geo-Redundant Storage | LRS in the primary region plus an asynchronous copy to the paired secondary region |
| GUI | Graphical User Interface | Visual interface such as the Azure portal |
| GZRS | Geo-Zone-Redundant Storage | ZRS in the primary region plus an asynchronous copy to the secondary region |

### H

| Acronym | Expansion | Meaning |
|---|---|---|
| HA | High Availability | Keeping a service running with minimal downtime despite failures |
| HDD | Hard Disk Drive | Spinning disk; the lowest-cost managed disk type |
| HPC | High-Performance Computing | Large parallel compute workloads |
| HTTP | Hypertext Transfer Protocol | Web protocol, unencrypted |
| HTTPS | Hypertext Transfer Protocol Secure | HTTP over TLS |

### I

| Acronym | Expansion | Meaning |
|---|---|---|
| IaaS | Infrastructure as a Service | Rented compute, storage, and networking; you manage the OS and everything above it |
| IaC | Infrastructure as Code | Defining infrastructure in files (ARM templates, Bicep) so deployments are repeatable |
| IAM | Identity and Access Management | Managing who can sign in and what they can do; the portal's "Access control (IAM)" page assigns Azure RBAC roles |
| IdP | Identity Provider | Service that authenticates users and issues tokens, such as Microsoft Entra ID |
| IOPS | Input/Output Operations Per Second | Disk performance measure |
| IoT | Internet of Things | Network-connected devices and sensors |
| IP | Internet Protocol | Network addressing; public and private IP addresses |
| IPsec | Internet Protocol Security | Protocol suite that encrypts VPN tunnels |
| ISO | International Organization for Standardization | Publisher of standards such as ISO/IEC 27001 |

### J

| Acronym | Expansion | Meaning |
|---|---|---|
| JIT | Just-in-Time | Access granted only when needed and for a limited time, such as JIT VM access in Defender for Cloud |
| JSON | JavaScript Object Notation | Text data format used by ARM templates and policy definitions |

### K

| Acronym | Expansion | Meaning |
|---|---|---|
| KQL | Kusto Query Language | Query language used in Log Analytics |

### L

| Acronym | Expansion | Meaning |
|---|---|---|
| LAN | Local Area Network | Network that covers one site |
| LDAP | Lightweight Directory Access Protocol | Directory query protocol; supported by Microsoft Entra Domain Services |
| LRS | Locally Redundant Storage | Three copies in a single datacenter; lowest cost and lowest durability |

### M

| Acronym | Expansion | Meaning |
|---|---|---|
| MFA | Multifactor Authentication | Sign-in that requires two or more of: something you know, have, or are |
| ML | Machine Learning | Training models from data to make predictions |
| MSA | Microsoft Account | Personal Microsoft sign-in; recommended for registering for certification exams |

### N

| Acronym | Expansion | Meaning |
|---|---|---|
| NFS | Network File System | File-sharing protocol common on Linux; supported by premium Azure file shares |
| NIC | Network Interface Card | A VM's network interface; one of the resources created with a VM |
| NIST | National Institute of Standards and Technology | US standards body; source of the cloud computing definition and security frameworks |
| NoSQL | Not Only SQL | Non-relational data stores such as key/value and document databases; Azure Table Storage is one |
| NSG | Network Security Group | Allow and deny rules that filter traffic to and from subnets and network interfaces |
| NTLM | New Technology LAN Manager | Legacy Windows authentication protocol; supported by Microsoft Entra Domain Services |

### O

| Acronym | Expansion | Meaning |
|---|---|---|
| OATH | Initiative for Open Authentication | Standards for one-time password tokens used as an MFA method |
| OAuth | Open Authorization | Token-based authorization standard used by Microsoft Entra ID |
| OIDC | OpenID Connect | Authentication layer on top of OAuth 2.0 used for sign-in |
| OpEx | Operational Expenditure | Ongoing spending on services as they are consumed; cloud computing is OpEx |
| OS | Operating System | Windows or Linux on a VM; customer-managed in IaaS |
| OTP | One-Time Password | Single-use code from an app, hardware token, or text message |

### P

| Acronym | Expansion | Meaning |
|---|---|---|
| P2S | Point-to-Site | VPN from one client computer to a virtual network |
| PaaS | Platform as a Service | Managed platform for running apps; the provider manages the OS and runtime |
| PAYG | Pay-As-You-Go | Paying only for what is used, with no up-front commitment |
| PII | Personally Identifiable Information | Data that identifies a person; a type of sensitive data Microsoft Purview classifies |
| PIN | Personal Identification Number | Short numeric secret tied to a device, as used by Windows Hello |

### R

| Acronym | Expansion | Meaning |
|---|---|---|
| RA-GRS | Read-Access Geo-Redundant Storage | GRS with read access to the secondary region at all times |
| RA-GZRS | Read-Access Geo-Zone-Redundant Storage | GZRS with read access to the secondary region at all times |
| RBAC | Role-Based Access Control | Granting permissions by assigning a role to an identity at a scope |
| RDP | Remote Desktop Protocol | Remote access to a Windows desktop |
| REST | Representational State Transfer | Web API style; Azure Resource Manager exposes a REST API |
| RPO | Recovery Point Objective | Maximum acceptable data loss, measured in time |
| RTO | Recovery Time Objective | Maximum acceptable time to restore service |

### S

| Acronym | Expansion | Meaning |
|---|---|---|
| S2S | Site-to-Site | VPN from an on-premises network device to a virtual network |
| SaaS | Software as a Service | Finished application delivered over the internet, such as Microsoft 365 |
| SAML | Security Assertion Markup Language | Federation standard used for single sign-on |
| SAS | Shared Access Signature | Token that grants limited, time-bound access to storage resources |
| SDK | Software Development Kit | Libraries for calling a service from code |
| SFTP | SSH File Transfer Protocol | Secure file transfer over SSH |
| SKU | Stock Keeping Unit | A purchasable variant or tier of a service |
| SLA | Service-Level Agreement | Microsoft's formal commitment for uptime and connectivity, expressed as a percentage |
| SMB | Server Message Block | Windows file-sharing protocol; used by Azure Files |
| SMS | Short Message Service | Text message; a verification method |
| SQL | Structured Query Language | Language for relational databases |
| SSD | Solid-State Drive | Flash disk; standard and premium managed disk types |
| SSH | Secure Shell | Encrypted remote access to a Linux system |
| SSL | Secure Sockets Layer | Obsolete predecessor of TLS; the name is still used loosely for TLS |
| SSO | Single Sign-On | One sign-in gives access to multiple applications |

### T

| Acronym | Expansion | Meaning |
|---|---|---|
| TCO | Total Cost of Ownership | All costs of owning and running a system over its life; Azure's TCO calculator has been retired and is no longer in the exam outline |
| TCP | Transmission Control Protocol | Connection-oriented transport protocol |
| TLS | Transport Layer Security | Encryption for data in transit |

### U

| Acronym | Expansion | Meaning |
|---|---|---|
| UDP | User Datagram Protocol | Connectionless transport protocol |
| UI | User Interface | What the user interacts with |
| URL | Uniform Resource Locator | Web address |

### V

| Acronym | Expansion | Meaning |
|---|---|---|
| vCPU | Virtual Central Processing Unit | Virtual processor core assigned to a VM |
| VDI | Virtual Desktop Infrastructure | Desktops hosted centrally and delivered remotely; Azure Virtual Desktop is the Azure offering |
| VHD | Virtual Hard Disk | Disk file format used by VM disks |
| VM | Virtual Machine | Software emulation of a computer; Azure's IaaS compute |
| VMSS | Virtual Machine Scale Sets | Group of identical, load-balanced VMs that scales automatically |
| VNet | Virtual Network | Private, isolated network in Azure |
| VPN | Virtual Private Network | Encrypted tunnel over a public network |

### W

| Acronym | Expansion | Meaning |
|---|---|---|
| WAF | Web Application Firewall | Protects web apps from common attacks; the letters also stand for the Azure Well-Architected Framework, whose pillars Azure Advisor follows |
| WAN | Wide Area Network | Network that spans large distances |
| WVD | Windows Virtual Desktop | Former name of Azure Virtual Desktop |

### Z

| Acronym | Expansion | Meaning |
|---|---|---|
| ZRS | Zone-Redundant Storage | Synchronous copies across three availability zones in one region |

---

## Numbers and Comparisons

The countable facts and the side-by-side tables. AZ-900 asks for few exact numbers; the ones worth knowing are in bold.

### SLA percentages and downtime

Service-level agreements are no longer a named outline bullet, but the "nines" still appear under high availability (1.2).

| Availability | Downtime per 30-day month | Downtime per year |
|---|---|---|
| 99% | 7.2 hours | 3.65 days |
| 99.9% | 43.2 minutes | 8.76 hours |
| 99.95% | 21.6 minutes | 4.38 hours |
| 99.99% | 4.32 minutes | 52.6 minutes |
| 99.999% | 26 seconds | 5.26 minutes |

- **Composite SLA:** when an application needs every service in a chain, multiply the SLAs. Two services at 99.95% and 99.99% give 0.9995 x 0.9999 = about 99.94%, lower than either one.
- Adding redundancy (more instances, zones, or regions) raises availability; adding dependencies lowers it.
- An SLA is a financial commitment. Missing it earns a service credit; it does not guarantee that no outage occurs.

### Regions, availability zones, and region pairs (2.1)

| Fact | Value |
|---|---|
| Region | A geographical area with at least one datacenter, usually several, networked together with low latency |
| Availability zone | One or more datacenters with independent power, cooling, and networking |
| Zones in a zone-enabled region | **Minimum of three**; not every region supports zones |
| Region pair distance | **At least 300 miles** apart where possible, in the same geography |
| Planned updates in a pair | Rolled out to one region of the pair at a time |
| Large outage affecting a pair | One region of each pair is prioritized for recovery |
| Data residency | Paired regions stay in one geography, except Brazil South, which pairs with South Central US |
| One-direction pairs | Brazil South's secondary is South Central US, but not the reverse |
| Regions without a pair | Some newer regions have no pair and rely on availability zones |
| Sovereign regions | Isolated instances of Azure: Azure Government (US) and Azure operated by 21Vianet (China) |
| Global (non-regional) services | No region to choose, for example Microsoft Entra ID and Azure DNS |

| Protects against | Use |
|---|---|
| Failure of one server or rack | Availability set (fault domains) |
| Planned maintenance reboots | Availability set (update domains) |
| Failure of a datacenter | Availability zones |
| Failure of a region | A second region, normally the paired one |

Availability set limits: up to **3 fault domains** and up to **20 update domains** (5 by default). The availability set itself is free; you pay for the VMs.

### Storage redundancy (2.3)

| Option | Copies and where | Durability over a year | Survives datacenter loss | Survives region loss | Read from secondary |
|---|---|---|---|---|---|
| LRS | 3 copies in one datacenter | At least **11 nines** | No | No | No |
| ZRS | 3 copies across 3 availability zones in one region | At least **12 nines** | Yes | No | No |
| GRS | 3 copies in the primary region (LRS) + 3 in the secondary region (LRS) | At least **16 nines** | Yes | Yes, after failover | No |
| RA-GRS | Same as GRS | At least 16 nines | Yes | Yes | **Yes** |
| GZRS | 3 zones in the primary region (ZRS) + 3 copies in the secondary region (LRS) | At least 16 nines | Yes | Yes, after failover | No |
| RA-GZRS | Same as GZRS | At least 16 nines | Yes | Yes | **Yes** |

- Copies inside the primary region are written synchronously; the copy to the secondary region is asynchronous, so the newest writes can be lost in a regional disaster.
- The secondary region is the primary's paired region and cannot be chosen.
- Cost and durability rise in this order: LRS, ZRS, GRS, GZRS. The read-access variants cost more than their base option.

### Blob access tiers (2.3)

| Tier | Online | Intended for | Minimum retention | Storage cost | Access cost | Can be the account default |
|---|---|---|---|---|---|---|
| Hot | Yes | Frequently accessed data | None | Highest | Lowest | Yes |
| Cool | Yes | Infrequently accessed data | **30 days** | Lower | Higher | Yes |
| Cold | Yes | Rarely accessed data that still needs fast retrieval | **90 days** | Lower still | Higher still | Yes |
| Archive | **No (offline)** | Rarely accessed data that can wait hours | **180 days** | Lowest | Highest | No; set per blob |

- Deleting or moving a blob before its tier's minimum period incurs a prorated early deletion charge.
- An archived blob must be **rehydrated** to an online tier before it can be read; this can take up to 15 hours.
- The archive tier is supported only on LRS, GRS, and RA-GRS accounts, not on ZRS, GZRS, or RA-GZRS.
- Tiers apply to block blobs. Cool and cold offer slightly lower availability than hot but the same durability and latency.

### Storage account types and services (2.3)

| Account type | Supports | Redundancy | Use |
|---|---|---|---|
| Standard general-purpose v2 | Blob Storage (including Data Lake Storage), Queue Storage, Table Storage, Azure Files | LRS, ZRS, GRS, RA-GRS, GZRS, RA-GZRS | Recommended for most scenarios |
| Premium block blobs | Block blobs and append blobs | LRS, ZRS | High transaction rates, small objects, consistently low latency |
| Premium file shares | Azure Files only | LRS, ZRS | High-performance file shares; supports both SMB and NFS |
| Premium page blobs | Page blobs only | LRS, ZRS | Page blob workloads |

Premium accounts use SSDs. A standard account cannot be converted to a premium account, or the reverse, after creation. A storage account name is **3–24 characters**, lowercase letters and numbers only, and unique across Azure.

| Blob type | Use |
|---|---|
| Block blob | Text and binary files; the default |
| Append blob | Data that is added to, such as logs |
| Page blob | Random-access files such as virtual hard disks |

### Management hierarchy (2.1)

Top to bottom: **management groups, subscriptions, resource groups, resources**. Policy and role assignments made at one level are inherited by everything below it.

| Level | Facts |
|---|---|
| Management group | One root management group per directory (tenant); up to **10,000** management groups per directory; tree depth up to **six levels**, not counting the root or the subscription level; each management group and subscription has exactly **one parent** |
| Subscription | A billing and access boundary; trusts one Microsoft Entra tenant; an account can have several subscriptions |
| Resource group | A resource belongs to exactly **one** resource group; resource groups cannot be nested; deleting the group deletes its resources; resources in a group can be in different regions |
| Resource | A single manageable item such as a VM, a storage account, or a virtual network |

Tags: up to **50** name/value pairs per resource, resource group, or subscription. Tags are not inherited unless Azure Policy applies them.

### Shared responsibility (1.1)

| Responsibility | On-premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Information and data | Customer | Customer | Customer | Customer |
| Devices (mobile and PCs) | Customer | Customer | Customer | Customer |
| Accounts and identities | Customer | Customer | Customer | Customer |
| Identity and directory infrastructure | Customer | Customer | Shared | Shared |
| Applications | Customer | Customer | Shared | Microsoft |
| Network controls | Customer | Customer | Shared | Microsoft |
| Operating system | Customer | Customer | Microsoft | Microsoft |
| Physical hosts | Customer | Microsoft | Microsoft | Microsoft |
| Physical network | Customer | Microsoft | Microsoft | Microsoft |
| Physical datacenter | Customer | Microsoft | Microsoft | Microsoft |

Always the customer: data, devices, accounts and identities. Always Microsoft in the cloud: physical hosts, network, and datacenter.

This matrix follows the diagram in Microsoft's AZ-900 training. The current Azure security article on shared responsibility renames some rows and marks applications (and client devices) as shared in SaaS, because the customer still configures the application and protects its endpoints. The rows the exam leans on are the same in both: data and identities are always yours, the physical layers are always Microsoft's, the operating system is yours only in IaaS, and network controls are shared in PaaS.

### Reservations and savings plans (3.1)

| | Azure Reservations | Azure savings plan for compute |
|---|---|---|
| Commitment | A specific resource type and region | A fixed hourly amount of spend |
| Term | **1 or 3 years** | **1 or 3 years** |
| Flexibility | Lower | Higher; applies across eligible compute services and regions |
| Best for | Stable, predictable workloads that will not change | Workloads that change size, service, or region |

Factors that affect cost: resource type, consumption, maintenance, geography (region), network traffic, subscription type, and Azure Marketplace purchases. Inbound data transfer is generally free; outbound data transfer is billed.

### Azure RBAC built-in roles (2.4)

| Role | Manage resources | Grant access to others |
|---|---|---|
| Owner | Yes | Yes |
| Contributor | Yes | No |
| Reader | View only | No |
| User Access Administrator | No | Yes |

A role assignment has three parts: a security principal (who), a role definition (what), and a scope (where). Scopes: management group, subscription, resource group, resource. Assignments are inherited downward and are additive.

### Resource locks (3.2)

| Lock | Portal name | Read | Modify | Delete |
|---|---|---|---|---|
| CanNotDelete | Delete | Yes | Yes | **No** |
| ReadOnly | Read-only | Yes | **No** | **No** |

Locks can be set on a subscription, resource group, or resource and are inherited by child resources. They apply to every user regardless of role; the lock must be removed before the blocked action can be taken.

### Defense in depth (2.4)

Seven layers, outermost to innermost:

| # | Layer | Example control |
|---|---|---|
| 1 | Physical security | Datacenter access controls |
| 2 | Identity and access | SSO, MFA, Conditional Access |
| 3 | Perimeter | DDoS protection, perimeter firewalls |
| 4 | Network | Segmentation, deny by default, network security groups |
| 5 | Compute | Patching, endpoint protection, secured VM access |
| 6 | Application | Secure development, no secrets in code |
| 7 | Data | Encryption and access control on the data itself |

### Zero Trust (2.4)

| Principle | Meaning |
|---|---|
| Verify explicitly | Authenticate and authorize every request using all available signals |
| Use least privilege access | Just-in-time and just-enough access |
| Assume breach | Segment access, encrypt end to end, and monitor to limit damage |

Authentication factors: something you know, something you have, something you are. MFA needs two or more different factors. Passwordless options in Microsoft Entra ID: Windows Hello for Business, the Microsoft Authenticator app, and FIDO2 security keys (passkeys).

### Azure Advisor categories (3.4)

| # | Category | Recommends |
|---|---|---|
| 1 | Reliability | Improving continuity of business-critical applications |
| 2 | Security | Fixing threats and vulnerabilities (from Defender for Cloud) |
| 3 | Performance | Improving speed and responsiveness |
| 4 | Cost | Reducing spending, such as resizing or shutting down idle resources |
| 5 | Operational excellence | Process, workflow, and manageability best practices |

### Azure Service Health components (3.4)

| Component | Scope |
|---|---|
| Azure Status | All Azure services in all regions; a public page |
| Service Health | Only the services and regions you use: service issues, planned maintenance, health advisories |
| Resource Health | Your individual resources, such as one VM |

Azure Monitor parts named in the outline: **Log Analytics** (query logs with KQL), **Azure Monitor alerts** (notify or act on a condition), **Application Insights** (monitor web applications).

---
