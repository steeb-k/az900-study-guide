# Domain 2 — Azure Architecture and Services (35–40%)

> **Note:** AI-generated content, not yet vetted for accuracy. See the README for details.

Objectives 2.1–2.4. The largest domain: the physical and logical building blocks of Azure (2.1), compute and networking (2.2), storage (2.3), and identity, access, and security (2.4). Most questions are "which service fits this scenario", so learn each service by the one thing that sets it apart from its neighbors.

---

## 2.1 Describe the core architectural components of Azure

Two layers. **Physical infrastructure**: datacenters, grouped into availability zones, regions, and region pairs. **Management infrastructure**: resources, resource groups, subscriptions, and management groups, which organize what you deploy and control billing and access.

### Azure regions, region pairs, and sovereign regions

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

### Availability zones

**Availability zone**: a physically separate location inside one Azure region. Each zone is made up of one or more datacenters with independent power, cooling, and networking, and the zones are connected through high-speed private fiber. If one zone goes down, the others keep working. Regions that support availability zones have a minimum of three; not every region supports them.

Zones protect against a datacenter-level failure inside a region. They do not protect against the loss of the whole region; that is what a second region (usually the paired one) is for.

| Service category | How it uses zones | Examples |
|---|---|---|
| Zonal services | You pin the resource to a specific zone that you choose | VMs, managed disks, IP addresses |
| Zone-redundant services | The platform replicates automatically across zones | Zone-redundant storage, SQL Database |
| Non-regional services | Always available from Azure geographies; resilient to zone-wide and region-wide outages | Global services that do not ask you to pick a region, such as Microsoft Entra ID, Azure Traffic Manager, and Azure DNS |

> **Exam tip:** Scope of each protection. Availability set: hardware failure or maintenance inside one datacenter (see 2.2). Availability zones: failure of an entire datacenter, inside one region. Region pairs: failure of an entire region. Match the size of the outage in the stem to the feature.

> **Exam tip:** "Zonal" = you place the resource in zone 1, 2, or 3 and must deploy copies to other zones yourself. "Zone-redundant" = Azure spreads the copies across zones for you.

### Azure datacenters

**Datacenter**: a physical facility that houses racks of servers with dedicated power, cooling, and networking. Microsoft operates them around the world, but customers never deploy to an individual datacenter directly. Datacenters are grouped into regions and availability zones, and those are what you select. Physical security of the datacenter is always Microsoft's part of the shared responsibility model (see 1.1).

### Resources and resource groups

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

### Subscriptions

**Subscription**: a unit of management, billing, and scale. It links to an Azure account, which is an identity in Microsoft Entra ID (see 2.4), and it is required before you can create any resource. An account can have more than one subscription.

| Boundary | Meaning |
|---|---|
| Billing boundary | Each subscription gets its own billing reports and invoice, so costs can be separated per subscription |
| Access control boundary | Access management policies are applied at the subscription level, so different teams or departments can be governed separately |

Common reasons to create additional subscriptions: to separate environments (development, test, production), to match organizational structure (one per department), or to separate billing. A subscription also has resource limits (quotas), so very large deployments may need more than one.

> **Exam tip:** "Each department needs its own invoice" = separate subscriptions. "Track cost by project inside one subscription" = tags (3.1) or resource groups.

### Management groups

**Management group**: a container for subscriptions (and other management groups). Governance settings such as Azure Policy assignments (3.2) and Azure RBAC role assignments (see 2.4) applied to a management group are inherited by every subscription beneath it. Use management groups when an organization has many subscriptions and wants to manage access, policy, and compliance for them together.

Facts Microsoft Learn states:

- 10,000 management groups can be supported in a single directory.
- A management group tree can be up to six levels deep, not counting the root level or the subscription level.
- Each management group and each subscription has exactly one parent.
- Every directory (Microsoft Entra tenant) has one top-level **root management group**, shown as the Tenant Root Group; all other management groups and subscriptions fold up to it.
- Unlike resource groups, management groups can be nested.

### Hierarchy of resource groups, subscriptions, and management groups

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

## 2.2 Describe Azure compute and networking services

### Compare compute types: virtual machines, containers, and functions

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

### Virtual machine options

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

### Resources required for virtual machines

When you create a VM, you choose or create the resources it depends on:

- **Size**: purpose, number of processor cores, and amount of RAM.
- **Storage disks**: hard disk drives or solid-state drives (an OS disk at minimum).
- **Networking**: a virtual network, a network interface, optionally a public IP address, and port configuration.
- A **resource group** to hold all of it.

These are separate resources that are billed separately. Stopping (deallocating) a VM stops the compute charge, but its disks and any reserved public IP address continue to cost money (3.1).

### Application hosting options

| Option | Model | You get | Choose it when |
|---|---|---|---|
| Azure App Service | PaaS | A managed, HTTP-based platform with built-in scaling, load balancing, and high availability, on Windows or Linux | You want to host a web app or API and focus on the code, not the servers |
| Containers (ACI, Container Apps, AKS) | PaaS | A portable package of the app and its dependencies | The app is already containerized, or is built as microservices |
| Virtual machines | IaaS | The whole operating system | You need full control of the hosting environment, or the app cannot be changed |

**Azure App Service** hosts web apps, API apps (REST-based web APIs), WebJobs (background tasks), and back ends for mobile apps. It supports many languages, including .NET, Java, Node.js, PHP, and Python, and supports automated deployments from GitHub, Azure DevOps, or any Git repository.

> **Exam tip:** "Host a website without managing the underlying servers" = App Service. If the stem adds "must install custom software on the operating system", it becomes a virtual machine.

### Virtual networking

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

### Public and private endpoints

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

## 2.3 Describe Azure storage services

A **storage account** is the container for Azure Storage data: it gives you a globally unique namespace reachable over HTTP/HTTPS, and its type and redundancy setting decide which services you get and how many copies are kept. All data written to a storage account is encrypted by the service.

### Compare Azure Storage services

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

### Storage tiers

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

### Redundancy options

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

### Storage account options and storage types

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

### Moving files (AzCopy, Azure Storage Explorer, Azure File Sync)

These tools move or manage individual files and small sets of files, as opposed to migrating a whole datacenter.

| Tool | What it is | Direction | Pick it when |
|---|---|---|---|
| AzCopy | Command-line utility that copies blobs and files to, from, and between storage accounts; can also copy to and from other cloud providers | Upload, download, copy, and **one-direction** sync from a source to a destination | The task must be scripted or automated |
| Azure Storage Explorer | Standalone app with a graphical interface for managing blobs and files; runs on Windows, macOS, and Linux and uses AzCopy on the back end | Upload, download, and move between accounts | An administrator wants a GUI |
| Azure File Sync | Service that centralizes file shares in Azure Files while a local Windows file server keeps a fast local cache | **Bi-directional** sync between Windows Server and an Azure file share | Branch offices need local file-server performance with the data centralized in Azure |

With Azure File Sync you can keep using any protocol Windows Server offers to reach the data locally (SMB, NFS, FTPS), have as many caches as you need around the world, replace a failed local server by installing Azure File Sync on a new one, and turn on **cloud tiering** so that frequently used files stay local and rarely used files stay in the cloud until someone asks for them.

> **Exam tip:** AzCopy = command line, one-way sync. Storage Explorer = graphical, any desktop OS. Azure File Sync = installed on Windows Server, two-way sync, cloud tiering. Azure File Sync is not a general copy tool and works with Azure Files, not Blob storage.

### Migration (Azure Migrate, Azure Data Box)

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

## 2.4 Describe Azure identity, access, and security

### Directory services (Microsoft Entra ID, Microsoft Entra Domain Services)

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

### Authentication methods (SSO, MFA, passwordless)

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

### External identities

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

### Microsoft Entra Conditional Access

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

### Azure RBAC

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

### Zero Trust

**Zero Trust** is a security model that assumes the worst case and protects resources accordingly. It assumes breach at the outset and verifies every request as though it came from an uncontrolled network. It replaces the perimeter idea that anything inside the corporate network is safe: access is granted on the strength of authentication and context, not network location.

| Principle | Meaning |
|---|---|
| Verify explicitly | Always authenticate and authorize based on all available data points (identity, location, device, and so on) |
| Use least privilege access | Limit access with just-in-time and just-enough-access (JIT/JEA), risk-based adaptive policies, and data protection |
| Assume breach | Limit the potential impact and segment access, verify end-to-end encryption, and use analytics for visibility and threat detection |

> **Exam tip:** "Trusted because it is on the internal network" is the opposite of Zero Trust. Conditional Access is the practical way "verify explicitly" is applied at sign-in; Azure RBAC and JIT access apply "least privilege".

### Defense-in-depth

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

### Microsoft Defender for Cloud

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

## Most-tested distinctions

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
