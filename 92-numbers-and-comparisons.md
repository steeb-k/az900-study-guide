# Numbers and Comparisons

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

The countable facts and the side-by-side tables. AZ-900 asks for few exact numbers; the ones worth knowing are in bold.

## SLA percentages and downtime

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

## Regions, availability zones, and region pairs (2.1)

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

## Storage redundancy (2.3)

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

## Blob access tiers (2.3)

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

## Storage account types and services (2.3)

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

## Management hierarchy (2.1)

Top to bottom: **management groups, subscriptions, resource groups, resources**. Policy and role assignments made at one level are inherited by everything below it.

| Level | Facts |
|---|---|
| Management group | One root management group per directory (tenant); up to **10,000** management groups per directory; tree depth up to **six levels**, not counting the root or the subscription level; each management group and subscription has exactly **one parent** |
| Subscription | A billing and access boundary; trusts one Microsoft Entra tenant; an account can have several subscriptions |
| Resource group | A resource belongs to exactly **one** resource group; resource groups cannot be nested; deleting the group deletes its resources; resources in a group can be in different regions |
| Resource | A single manageable item such as a VM, a storage account, or a virtual network |

Tags: up to **50** name/value pairs per resource, resource group, or subscription. Tags are not inherited unless Azure Policy applies them.

## Shared responsibility (1.1)

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

## Reservations and savings plans (3.1)

| | Azure Reservations | Azure savings plan for compute |
|---|---|---|
| Commitment | A specific resource type and region | A fixed hourly amount of spend |
| Term | **1 or 3 years** | **1 or 3 years** |
| Flexibility | Lower | Higher; applies across eligible compute services and regions |
| Best for | Stable, predictable workloads that will not change | Workloads that change size, service, or region |

Factors that affect cost: resource type, consumption, maintenance, geography (region), network traffic, subscription type, and Azure Marketplace purchases. Inbound data transfer is generally free; outbound data transfer is billed.

## Azure RBAC built-in roles (2.4)

| Role | Manage resources | Grant access to others |
|---|---|---|
| Owner | Yes | Yes |
| Contributor | Yes | No |
| Reader | View only | No |
| User Access Administrator | No | Yes |

A role assignment has three parts: a security principal (who), a role definition (what), and a scope (where). Scopes: management group, subscription, resource group, resource. Assignments are inherited downward and are additive.

## Resource locks (3.2)

| Lock | Portal name | Read | Modify | Delete |
|---|---|---|---|---|
| CanNotDelete | Delete | Yes | Yes | **No** |
| ReadOnly | Read-only | Yes | **No** | **No** |

Locks can be set on a subscription, resource group, or resource and are inherited by child resources. They apply to every user regardless of role; the lock must be removed before the blocked action can be taken.

## Defense in depth (2.4)

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

## Zero Trust (2.4)

| Principle | Meaning |
|---|---|
| Verify explicitly | Authenticate and authorize every request using all available signals |
| Use least privilege access | Just-in-time and just-enough access |
| Assume breach | Segment access, encrypt end to end, and monitor to limit damage |

Authentication factors: something you know, something you have, something you are. MFA needs two or more different factors. Passwordless options in Microsoft Entra ID: Windows Hello for Business, the Microsoft Authenticator app, and FIDO2 security keys (passkeys).

## Azure Advisor categories (3.4)

| # | Category | Recommends |
|---|---|---|
| 1 | Reliability | Improving continuity of business-critical applications |
| 2 | Security | Fixing threats and vulnerabilities (from Defender for Cloud) |
| 3 | Performance | Improving speed and responsiveness |
| 4 | Cost | Reducing spending, such as resizing or shutting down idle resources |
| 5 | Operational excellence | Process, workflow, and manageability best practices |

## Azure Service Health components (3.4)

| Component | Scope |
|---|---|
| Azure Status | All Azure services in all regions; a public page |
| Service Health | Only the services and regions you use: service issues, planned maintenance, health advisories |
| Resource Health | Your individual resources, such as one VM |

Azure Monitor parts named in the outline: **Log Analytics** (query logs with KQL), **Azure Monitor alerts** (notify or act on a condition), **Application Insights** (monitor web applications).
