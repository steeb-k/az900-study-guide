# Domain 1 — Cloud Concepts (25–30%)

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

Objectives 1.1–1.3. Almost no Azure product knowledge is needed here; the questions test vocabulary. Most of them describe a situation and ask which cloud model, service type, or benefit it illustrates.

---

## 1.1 Describe cloud computing

### Define cloud computing

**Cloud computing** is the delivery of computing services over the internet: virtual machines, storage, databases, and networking, plus newer services such as Internet of Things (IoT), machine learning, and AI. You rent capacity from a provider's datacenters instead of buying and running hardware, you can add or remove capacity in minutes, and you are billed for what you use.

Compared with a traditional datacenter, the cloud removes the need to buy hardware, provide power and cooling, secure a building, or guess capacity years ahead.

### Shared responsibility model

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

### Cloud models (public, private, hybrid)

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

### Use cases for each cloud model

| Requirement in the stem | Model |
|---|---|
| New company with no datacenter; wants no upfront hardware cost; wants to deploy fast | Public |
| Unpredictable or rapidly growing demand; pay only for what is used | Public |
| Must keep complete control of hardware and security; data must not share infrastructure with other organizations | Private |
| Legacy system that cannot move, or data that regulation requires to stay on-premises, combined with new cloud workloads | Hybrid |
| Keep the existing datacenter investment and use the public cloud for peak demand ("cloud bursting") or for disaster recovery | Hybrid |
| Migrate gradually, running some systems on-premises and some in Azure during the move | Hybrid |

> **Exam tip:** Any stem that mentions keeping something on-premises *and* using public cloud services is hybrid. "Most flexibility" also points to hybrid; "complete control" points to private; "no capital expenditure" points to public.

### Consumption-based model

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

### Compare cloud pricing models

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

### Describe serverless

**Serverless** computing means the provider provisions, scales, and maintains the servers that run your code. Servers still exist; you just never manage them. Characteristics:

- No infrastructure management. You deploy code, not servers.
- Automatic scaling with demand, typically down to zero when nothing is running.
- Billing based on actual consumption, such as the number of executions and the resources each one uses. In a consumption-based plan you do not pay for idle time.
- Often event-driven: code runs in response to a trigger such as an HTTP request, a timer, or a new message.

Azure Functions is Azure's serverless compute service; the outline lists it as "functions" (see 2.2).

> **Exam tip:** Serverless vs a virtual machine: a VM bills for every hour it is allocated, even when idle, and you manage its operating system. Serverless code bills only when it runs, and there is no operating system for you to manage.

---

## 1.2 Describe the benefits of using cloud services

### High availability and scalability

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

### Reliability and predictability

**Reliability** is the ability of a system to recover from failures and continue to function. The cloud supports it through decentralized design: resources can be deployed in regions around the world, so if one region has a catastrophic event, others keep running.

**Predictability** lets you move forward with confidence. It has two parts:

| | Performance predictability | Cost predictability |
|---|---|---|
| Meaning | Predicting the resources needed to give customers a positive experience | Predicting or forecasting what cloud spending will be |
| Supported by | Autoscaling, load balancing, high availability | Tracking resource use in real time, monitoring for efficient use, analyzing data to find patterns, estimating with the pricing calculator (3.1) |

Both tie back to the **Microsoft Azure Well-Architected Framework**, Microsoft's design guidance for cloud workloads: reliability is one of its pillars, and a solution built around the framework has predictable cost and performance.

> **Exam tip:** Reliability = recovers from failure. High availability = stays accessible with minimal downtime. They are close; choose reliability when the stem stresses recovery or deploying to multiple regions, and high availability when it stresses uptime or an SLA.

> **Exam tip:** Forecasting a bill is cost predictability. Autoscaling and load balancing delivering a consistent user experience is performance predictability.

### Security and governance

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

### Manageability

Two halves, and the exam asks you to tell them apart.

| | Management **of** the cloud | Management **in** the cloud |
|---|---|---|
| Question it answers | How are cloud resources managed? | How do you interact with and manage your cloud environment? |
| Examples | Automatically scale deployments to meet need; deploy resources from a preconfigured template, removing manual configuration; monitor resource health and automatically replace failing resources; receive automatic alerts based on configured metrics | Through a web portal; using a command-line interface; using APIs; using PowerShell |

The Azure tools for the second column (portal, CLI, PowerShell) are in 3.3.

> **Exam tip:** "Of" = what the platform can do to resources (autoscale, templates, self-healing, alerts). "In" = the interface you use (portal, CLI, APIs, PowerShell).

---

## 1.3 Describe cloud service types

The service type decides how much the provider manages and how much you manage. Flexibility and responsibility move together: the most control comes with the most work.

### Infrastructure as a service (IaaS)

The provider maintains the hardware, network connectivity to the internet, and physical security. You rent compute, storage, and networking and manage everything above them: operating system installation, configuration, patching, network configuration, and applications.

- Most flexible service type; gives the customer the maximum amount of control.
- Places the largest share of responsibility on the customer.
- Example: Azure Virtual Machines.

### Platform as a service (PaaS)

The provider maintains the physical infrastructure, physical security, and internet connection, and also the operating systems, middleware, development tools, and analytics services. You do not handle licensing or patching for operating systems and databases. You deploy and manage your applications and data.

- Middle ground between IaaS and SaaS.
- A complete development and deployment environment without the infrastructure work.
- Examples: Azure App Service, Azure SQL Database.

### Software as a service (SaaS)

You use a fully developed application that the provider hosts and manages. You are responsible only for the data you put into it, the devices you allow to connect, and the users who have access.

- Least flexible; you take the application as offered and configure it.
- Easiest to get running; least technical knowledge needed.
- Commonly paid for by subscription, per user, monthly or annually.
- Examples: Microsoft 365 (email, Teams, Office apps), Dynamics 365. Email, messaging, and financial software are the typical SaaS categories.

### Use cases for each

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

## Most-tested distinctions

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
