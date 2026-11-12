# Domain 3 — Azure Management and Governance (30–35%)

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

Objectives 3.1–3.4. This domain is mostly "which tool does this job": cost tools, governance tools, deployment tools, and monitoring tools. Nearly every question is a pick-the-right-service question, so learn the one-line purpose of each tool and the neighbor it gets confused with.

---

## 3.1 Describe cost management in Azure

### Factors that affect costs

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

### Pricing options that reduce cost

| Option | Commitment | Best for | Catch |
|---|---|---|---|
| **Pay-as-you-go** | None | Unpredictable or short-lived workloads | Highest rate |
| **Azure Reservations** | Specific resources (for example a VM size in a region, database capacity, storage capacity) for a one-year or three-year term | Stable, predictable, always-on workloads | Discount applies only to usage that matches what you reserved |
| **Azure savings plan for compute** | A fixed hourly spend on eligible compute services for one or three years | Steady compute spend that shifts between VM sizes, regions, or compute services | Compute only; usage above the commitment is billed pay-as-you-go |
| **Azure Spot Virtual Machines** | None | Interruptible work: batch jobs, rendering, dev/test that can restart | Azure can evict the VM when it needs the capacity back; no availability guarantee |
| **Azure Hybrid Benefit** | Existing on-premises licenses | Organizations that already own Windows Server or SQL Server licenses with Software Assurance (or qualifying subscriptions) | A licensing benefit, not a commitment discount. Microsoft's AZ-900 training module covers the other four options and not this one, so know only its one-line purpose |

> **Exam tip:** Reservation = commit to a specific resource. Savings plan = commit to an hourly dollar amount, flexible across compute. "Workload runs 24/7 on the same VM size for three years" is a reservation. "Compute usage is steady but moves between services and regions" is a savings plan.

> **Exam tip:** "Reuse the licenses we already bought for the on-premises datacenter" is Azure Hybrid Benefit. "Cheapest compute for a job that can be interrupted" is Spot.

### The pricing calculator

A public web tool that estimates the cost of Azure resources **before** you deploy them.

- Add products, then configure region, tier or size, quantity, hours of use, redundancy, and pricing option; it returns an estimated monthly cost.
- Estimates individual resources, a whole solution, or a provided example scenario. Covers compute, storage, and associated network costs.
- For information only: the figures are estimates, **nothing is provisioned**, and you are not charged for anything you add.
- Typical use: compare regions, tiers, and redundancy options, then use the estimate as a baseline for budget approval.

The Total Cost of Ownership (TCO) calculator, which compared on-premises cost with Azure cost, has been retired and is no longer part of the exam outline.

> **Exam tip:** Pricing calculator = estimate what something *will* cost, before deployment, with no Azure subscription needed. Cost Management = see and control what you *are* spending, on resources that already exist.

### Cost management capabilities

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

### Tags

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

## 3.2 Describe features and tools in Azure for governance and compliance

### Microsoft Purview

A family of **data governance, risk, and compliance** solutions that gives a single, unified view of an organization's data. It governs *data*, not Azure resources.

- Brings together insight about data held **on-premises, in multiple clouds, and in software as a service (SaaS)** applications.
- Core capabilities: **automated data discovery**, **sensitive data classification**, and **end-to-end data lineage** (where data came from and how it moved and changed).

| Solution area | What it covers |
|---|---|
| **Risk and compliance** | Built around Microsoft 365 services such as Teams, OneDrive, and Exchange. Protect sensitive data across clouds, apps, and devices; identify data risks; manage regulatory compliance. |
| **Unified data governance** | Data in Azure, SQL and Hive databases, on-premises stores, and other clouds such as Amazon S3. Build an up-to-date **map** of the data estate with classification and lineage; identify where sensitive data lives; give data consumers a secure **catalog** in which to find data; generate insight into how data is stored and used; manage access to data at scale. |

> **Exam tip:** Keywords for Purview: data estate, data map, data catalog, classification, lineage, sensitive data, multicloud data. If the question is about rules for *resources* (allowed regions, required tags), it is Azure Policy. If it is about security posture of workloads, it is Microsoft Defender for Cloud (2.4).

### Azure Policy

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

### Resource locks

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

## 3.3 Describe features and tools for managing and deploying Azure resources

### Azure portal

A **web-based, unified console** with a graphical user interface, the alternative to command-line tools.

- Build, manage, and monitor everything from a single web app to complex deployments.
- Create **custom dashboards** for an organized view of resources; configure accessibility options.
- Designed for continuous availability: it has a presence in every Azure datacenter, is resilient to an individual datacenter failure, updates continuously, and needs no maintenance downtime.
- Best for one-off tasks, exploring services, and viewing reports. Not well suited to repeating the same deployment many times, because every step is manual.

### Azure Cloud Shell, Azure CLI, and Azure PowerShell

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

### Azure Arc

Azure Arc **extends Azure management and governance to resources outside Azure**: on-premises datacenters, the edge, and other public clouds. It works with Azure Resource Manager by **projecting non-Azure resources into ARM**, so they appear and are managed like Azure resources.

- One consistent management platform for hybrid and multicloud environments.
- Apply familiar Azure capabilities to those resources: Azure Policy, tags, RBAC, inventory, and monitoring.
- Keep traditional IT operations while introducing DevOps practices.

Resource types Azure Arc can manage outside Azure: **servers**, **Kubernetes clusters**, **Azure data services**, **SQL Server**, and **virtual machines** (listed as preview in Microsoft's training).

> **Exam tip:** Arc manages; it does not move or connect. Migrating servers into Azure is Azure Migrate (2.3). A private network link is VPN Gateway or ExpressRoute (2.2). "Apply Azure Policy to servers running in another cloud" is Azure Arc.

### Infrastructure as code (IaC)

Managing infrastructure through **code and templates instead of manual configuration**. The definition lives in files that can be version-controlled, reviewed, and reused.

- Benefits: consistent environments (dev, test, and production built from the same definition), repeatable deployments, less human error, faster provisioning, and a change history.
- It can start with Azure CLI or Azure PowerShell scripts and grow into ARM templates and Bicep.

| Approach | You write | Examples |
|---|---|---|
| **Imperative** | The steps to run, in order | Azure CLI and Azure PowerShell scripts |
| **Declarative** | The desired end state; the platform works out the steps | ARM templates, Bicep |

### Azure Resource Manager (ARM) and ARM templates

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

## 3.4 Describe monitoring tools in Azure

### Azure Advisor

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

### Azure Service Health

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

### Azure Monitor

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

## Most-tested distinctions

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
