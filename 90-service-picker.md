# Service Picker

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

"The requirement says X, the answer is Y." Find the deciding words in the stem, then look them up here. Objective numbers point to the chapter section.

> **Exam tip:** Most AZ-900 service questions turn on one phrase. Underline it before reading the options.

## Compute (2.2)

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

## Application hosting (2.2)

| The requirement says | The answer is |
|---|---|
| Host a website or REST API without managing servers; built-in scaling and deployment | Azure App Service (web apps, API apps) |
| Package the app with its dependencies so it runs the same everywhere | Containers |
| The app needs settings or software only possible with OS-level access | Virtual machines |
| No infrastructure to manage and no charge while idle | Serverless (Azure Functions) |

## Networking and connectivity (2.2)

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

## Storage (2.3)

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

## Data transfer and migration (2.3)

| The requirement says | The answer is |
|---|---|
| Command-line or scripted copy of blobs or files to, from, or between storage accounts | AzCopy |
| Graphical desktop app to browse and manage storage on Windows, macOS, or Linux | Azure Storage Explorer |
| Keep an on-premises Windows file server in sync with Azure Files; cache hot files locally | Azure File Sync |
| Discover, assess, and migrate on-premises servers, databases, and web apps | Azure Migrate |
| Move a very large amount of data offline because the network is slow or costly | Azure Data Box |

## Identity and access (2.4)

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

## Security (2.4)

| The requirement says | The answer is |
|---|---|
| "Never trust, always verify"; verify explicitly, least privilege, assume breach | Zero Trust |
| Several layers of protection so one failed control does not expose data | Defense in depth |
| Secure score, security recommendations, and threat protection across Azure, on-premises, and other clouds | Microsoft Defender for Cloud |

## Governance and compliance (3.2)

| The requirement says | The answer is |
|---|---|
| Enforce or audit rules on resources: allowed regions, allowed VM sizes, required tags | Azure Policy |
| Group related policies toward one goal | Policy initiative |
| Prevent accidental deletion of a resource | Resource lock: Delete (CanNotDelete) |
| Prevent any change to a resource | Resource lock: ReadOnly |
| Discover, classify, and govern data across on-premises, multicloud, and SaaS | Microsoft Purview |
| Apply policy or access to many subscriptions at once | Management group |

## Cost (3.1)

| The requirement says | The answer is |
|---|---|
| Estimate the cost of resources before deploying them | Pricing calculator |
| Analyze actual spending, set budgets, and get cost alerts | Microsoft Cost Management |
| Be notified when spending reaches a threshold | Budget with a cost alert |
| Attribute cost to a department, project, or environment | Tags |
| Discount for committing to a specific resource type in a region for one or three years | Azure Reservations |
| Discount for committing to a fixed hourly spend on compute across services and regions | Azure savings plan for compute |
| Find idle or underused resources to cut cost | Azure Advisor, cost recommendations |

## Deployment and management (3.3)

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

## Monitoring (3.4)

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

## Sounds alike, is not

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
