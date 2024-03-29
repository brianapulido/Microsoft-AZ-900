These are my notes taken during the self-paced study I did for the AZ-900 Microsoft Azure Fundamentals Exam.   
The link below brings you to the Microsoft website for the AZ-900 Exam which contains the 3 learning paths I followed to prepare.  
[Exam AZ-900: Microsoft Azure Fundamentals](https://learn.microsoft.com/en-us/credentials/certifications/exams/az-900/)

# Describe cloud concepts (25–30%)
* Microsoft Azure is a cloud computing platform.  
* Azure services:  
	- Remote storage  
	- Database hosting  
	- Centralized account management  
	- AI & IoT services  
* Exam Domain areas:  
	- Describe cloud concepts  
	- Describe Azure architecture and services  
	- Describe Azure management and governance  
* **Cloud computing** is the delivery of computing services over the internet.  
* Services include virtual machines, storage, databases, networking, AI, IoT, ML.  
* Main services: Compute power and storage.  
* **Shared responsibility model**: responsibility for infrastructure and software is shared between the cloud provider and the consumer.  
* Cloud provider has responsibility over things in their datacenter.  
* **IaaS** places the most responsibility on the consumer, with the cloud provider being responsible for the basics of physical security, power, and connectivity.  
* **SaaS** places most of the responsibility with the cloud provider.   
* **PaaS**, being a middle ground of shared responsibility.  
* You’ll always be responsible for:  
	- The information and data stored in the cloud  
	- Devices that are allowed to connect to your cloud (cell phones, computers, and so on)  
	- The accounts and identities of the people, services, and devices within your organization  
* The cloud provider is always responsible for:  
	- The physical datacenter  
	- The physical network  
	- The physical hosts  
* Your service model will determine responsibility for things like:  
	- Operating systems  
	- Network controls  
	- Applications  
	- Identity and infrastructure  
* 3 main cloud models: private, public and hybrid  
* Private cloud: used by a single entity  
* Public cloud: available for public use, purchase cloud services and use. It is built, controlled and maintained by a third-party cloud provider.  
* Hybrid cloud: can run both private and public cloud together and decide where you want certain services to go. Flexibility.  
* Azure Arc helps manage cloud environments  
* Azure VMware Solution provides seamless integration between private and public or hybrid clouds.  
* Consumption-based model: Cloud computing falls under operational expenditure (OpEx) which is spending money on services or products over time.   
* Consumer pays only for resources used.  
* Pay-as-you-go pricing model.  
* Availability: need high availability to make sure resources are available when needed. Minimize downtime. Get it with redundancy, load balancing, failover solutions, set data synchronization to meet RPO. Availability guarantee is in the Service Level Agreement (SLA).  
* Scalability: the ability to adjust resources to meet demand. Vertical and horizontal scaling. Vertical scaling is focused on increasing or decreasing the capabilities of resources (CPU, RAM). Horizontal scaling is adding or subtracting the number of resources (VMs, containers).  
* Reliability: the ability of a system to recover from failures and continue to function. Cloud has decentralized design.  
* Predictability: performance predictability is predicting the resources needed to deliver a positive experience for your customers (Autoscaling, load balancing, and high availability). Cost predictability is predicting or forecasting the cost of the cloud spend. With the cloud, you can track your resource use in real time, monitor resources to ensure that you’re using them in the most efficient way, and apply data analytics to find patterns and trends that help better plan resource deployments.  
* Cloud features support governance and compliance.  
* Management of the cloud  
* Management in the cloud  
* IaaS: flexible, max control over resources. The cloud provider is responsible for maintaining the hardware, network connectivity (to the internet), and physical security. You’re responsible for everything else: operating system installation, configuration, and maintenance; network configuration; database and storage configuration, etc.  
* PaaS: the cloud provider maintains the physical infrastructure, physical security, connection to the internet, the operating systems, middleware, development tools, and business intelligence services that make up a cloud solution. No burden of maintenance of dev infrastructure on the consumer.  
* SaaS: renting or suing a fully developed software application. Most of the responsibility is on the cloud provider.  

# Describe Azure architecture and services (35–40%)
* Datacenters: facilities with resources arranged in racks, with dedicated power, cooling, and networking infrastructure.  
* Datacenters are grouped into Azure Regions or Azure Availability Zones.  
* A region is a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.  
* Availability zones are physically separate datacenters within an Azure region. They are made up of one or more datacenters.  
* Availability zones are primarily for VMs, managed disks, load balancers, and SQL databases.  
* Azure services that support availability zones:  
	- Zonal services  
	- Sone-redundant services  
	- Non-regional services  
* Region pairs: regions are paired with another region within the same geographical area to help with failover.  
* Sovereign regions: instances of Azure that are isolated from the main instance of Azure… used for compliance or legal purposes.  
* Virtual Machines (VMs), virtual networks, databases, cognitive services, etc. are all considered resources within Azure.  
* Resources must be placed in a resource group… no nesting.  
* Azure subscriptions  
* Management groups  
	- Resources are gathered into resource groups, and resource groups are gathered into subscriptions which are then gathered into management groups.  
* Azure Virtual Machines (VMs) give you the flexibility of virtualization without having to buy and maintain the physical hardware that runs the VM. You choose OS, tools, packages, isolation or together. Can only run one OS at a time. IAAS. parts of a VM include:
	- virtual network
 	- NIC
  	- IP address
  	- network security group (NSG)
  	- OS disk  
* Availability sets are designed to ensure that VMs stagger updates and have varied power and network connectivity, preventing you from losing all your VMs with a single network or power failure.  
* Availability sets group VMs in two ways: update domain and fault domain.  
* VMs are good for lift and shift scenarios.  
* Azure virtual desktop: desktop and application virtualization service that runs on the cloud. It enables you to use a cloud-hosted version of Windows from any location. provides centralized security management with Entra ID.  
* Containers are a virtualization environment. You can run multiple containers on a single physical or virtual host. Single app + dependencies. Can spin up quickly.  
* Docker is a popular container engine and is supported by Azure  
* VMs virtualize the hardware while containers virtualize the OS  
* Container is more efficient than VM  
* Containers can have container cluster orchestration. Exp. Azure Kubernetes service which manages lifecycle of containers  
* For complete control of env use VM  
* For portability or performance, use containers  
* Azure container instances are PaaS  
* Azure container apps are Paas… removes container management.. Can incorporate load balancing and scaling = elasticity  
* Containers use microservice architecture  
* Azure Functions is an event-driven, serverless compute option that doesn’t require maintaining virtual machines or containers. Event wake the function so resources not always running.  
* Functions scale automatically… good when demand is variable  
* Durable functions = stateful  
* Azure virtual network allows you to create multiple isolated virtual networks.  
* When you set up a virtual network, you define a private IP address and you can divide that IP address space into subnets and allocate part of the defined address space to each named subnet.  
* You can enable incoming connections from the internet by assigning a public IP address to an Azure resource.  
* You can use virtual networks or service endpoints to enable Azure resources to communicate securely with each other.  
* Azure virtual networks enable you to link resources together in your on-premises environment and within your Azure subscription.  
	- Point-to-site virtual private network connections are from a computer outside your organization back into your corporate network.  
	- Site-to-site virtual private networks link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network.  
	- Azure ExpressRoute provides a dedicated private connectivity to Azure that doesn't travel over the internet. Greater bandwidth + high security.  
* Control routing via:  
	- Route tables allow you to define rules about how traffic should be directed.  
	- Border Gateway Protocol (BGP) works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual networks.  
* Azure virtual networks enable you to filter traffic between subnets by using  
	- Network security groups (NSGs) that can contain multiple inbound and outbound security rules you define.  
	- Network virtual appliances that specialized VMs that can be compared to a hardened network appliance.  
* You can link virtual networks together by using virtual network peering which allows two virtual networks to connect directly to each other.  
	- Network traffic is private  
	- Resources in each virtual network can communicate with each other  
	- User-defined routes (UDR) allow you to control the routing tables between subnets within a virtual network or between virtual networks.  
* Virtual private networks (VPNs) are typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public internet) using an encrypted tunnel.  
* A VPN gateway is a type of virtual network gateway. Azure VPN Gateway instances are deployed in a dedicated subnet of the virtual network.  
* VPN gateways  
	- Connect on-premises datacenters to virtual networks through a site-to-site connection.  
	- Connect individual devices to virtual networks through a point-to-site connection.  
	- Connect virtual networks to other virtual networks through a network-to-network connection.  
* You can deploy only one VPN gateway in each virtual network.  
* When setting up a VPN gateway, you must specify the type of VPN - either policy-based or route-based.   
* In Azure, regardless of the VPN type, the method of authentication employed is a pre-shared key. 
* Policy-based VPN gateways specify statically the IP address of packets that should be encrypted through each tunnel.  
* In Route-based gateways, IPSec tunnels are modeled as a network interface or virtual tunnel interface. IP routing (either static routes or dynamic routing protocols) decides which one of these tunnel interfaces to use when sending each packet. Route-based VPNs are the preferred connection method for on-premises devices.  
* By default, VPN gateways are deployed as two instances in an active/standby configuration.  
* With the introduction of support for the BGP routing protocol, you can also deploy VPN gateways in an active/active configuration.  
* Another high-availability option is to configure a VPN gateway as a secure failover path for ExpressRoute connections.  
* In regions that support availability zones, VPN gateways and ExpressRoute gateways can be deployed in a zone-redundant configuration.  
* Deploying gateways in Azure availability zones physically and logically separates gateways within a region while protecting your on-premises network connectivity to Azure from zone-level failures.  
* ExpressRoute Circuit is a means of connecting on-premises networks to the cloud.  
	- Redundancy  
	- Dynamic routing via BGP  
	- Connectivity across regions  
* ExpressRoute Connectivity Models  
	- CloudExchange colocation  
	- Point-to-point Ethernet connection  
	- Any-to-any connection  
	- Directly from ExpressRoute sites  
* Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure infrastructure.  
* DNS domains in Azure DNS are hosted on Azure's global network of DNS name servers, providing resiliency and high availability.  
* Azure DNS uses anycast networking = fast performance and HA  
* Azure security features include RBAC, activity logs, resource locking  
* Azure DNS is integrated in the Azure portal = ease of use  
* Azure DNS also supports private DNS domains and alias record sets.  
* Azure storage is an account that stores data  
	- Locally redundant storage (LRS)  
	- Geo-redundant storage (GRS)  
	- Read-access geo-redundant storage (RA-GRS)  
	- Zone-redundant storage (ZRS)  
	- Geo-zone-redundant storage (GZRS)  
	- Read-access geo-zone-redundant storage (RA-GZRS)  
* Storage service  
	- Blob storage  
	- Data lake storage Gen2  
	- Azure files  
	- Queue storage  
	- Table storage  
* Azure storage redundancy in the primary region  
	- Data in an Azure Storage account is always replicated three times in the primary region. Either LRS or ZRS.  
* Locally redundant storage (LRS) replicates your data three times within a single data center in the primary region.  
	- LRS is the lowest-cost redundancy option and offers the least durability  
* Zone-redundant storage (ZRS) replicates your Azure Storage data synchronously across three Azure availability zones in the primary region  
	- High availability  
* Azure Storage offers two options for copying your data to a secondary region: geo-redundant storage (GRS) and geo-zone-redundant storage (GZRS).  
	- Data is replicated asynchronously  
* GRS copies your data synchronously three times within a single physical location in the primary region using LRS. It then copies your data asynchronously to a single physical location in the secondary region (the region pair) using LRS  
* Data in a GZRS storage account is copied across three Azure availability zones in the primary region (similar to ZRS) and is also replicated to a secondary geographic region, using LRS, for protection from regional disasters. 16 nines of durability.  
	- For cases requiring maximum consistency, durability, and availability, excellent performance, and resilience for disaster recovery.  
* Azure Storage platform services:  
	- Azure Blobs: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake   Storage Gen2.  
	- Azure Files: Managed file shares for cloud or on-premises deployments.  
	- Azure Queues: A messaging store for reliable messaging between application components.  
	- Azure Disks: Block-level storage volumes for Azure VMs.  
	- Azure Tables: NoSQL table option for structured, non-relational data.  
* Azure storage benefits  
	- Durable and highly available --> redundancy/data replication  
	- Secure --> encrypted  
	- Scalable --> resource management to meet demands  
	- Managed --> maintenance, updates, patches, critical issues  
	- Accessible --> access anywhere, libraries in many languages, Azure portal  
* Azure Blobs  
	- Object storage solution for the cloud that can store massive amounts of unstructured data.  
	- Objects can be accessed from anywhere via HTTP or HTTPS.  
	- Objects can be accessed via URLs. Azure Storage REST API, Azure Powershell, Azure CLI, or Azure Storage client library.  
* Blob Storage Tiers  
	- Hot access tier: Optimized for storing data that is accessed frequently (for example, images for your website).  
	- Cool access tier: Optimized for data that is infrequently accessed and stored for at least 30 days (for example, invoices for your customers).  
	- Cold access tier: Optimized for storing data that is infrequently accessed and stored for at least 90 days.  
	- Archive access tier: Appropriate for data that is rarely accessed and stored for at least 180 days, with flexible latency requirements (for example, long-term backups).  
* Azure File storage offers managed file shares in cloud via Server Message Block (SMB) or Network File System (NFS) protocols.  
* Azure Migrate helps migrate data from on-premises to the cloud (Azure).  
* Azure Data Box: a physical migration service that helps transfer large amounts of data (> 40 TBs).  
* AzCopy: command-line utility that can upload, download, copy and synchronize blobs or files to or from the storage account.  
* Azure Storage Explorer: app that provides a graphical interface to manage files and blobs in your Azure Storage Account.  
* Azure File Sync: software tool that lets you centralize file shares in Azure Files… bi-directional syncing between local server and Azure.  
* Microsoft Entra ID: a directory service enables sign-in to Microsoft cloud applications and self-developed cloud applications. It is a cloud-based identity and access management service.   
	- Authentication  
	- Single Sign on (SSO)  
	- Application management  
	- Device management  
* Use Microsoft Entra Connect to connect Microsoft Entra ID with on-premises AD.  
* Microsoft Entra Domain Services provides managed domain services such as domain join, group policy, lightweight directory access protocol (LDAP), and Kerberos/NTLM authentication.  
* You create a Microsoft Entra Domain Services managed domain, two Windows Server domain controllers are deployed as a replica set.  
* A managed domain performs one-way synchronization from Microsoft Entra ID to Microsoft Entra Domain Services.  
* Azure supports multiple authentication methods, including standard passwords, single sign-on (SSO), multifactor authentication (MFA), and passwordless.  
* Single sign-on (SSO) enables a user to sign in one time (via initial authenticator) and use that credential to access multiple resources and applications from different providers.  
* Multifactor authentication is the process of prompting a user for an extra form (or factor) of identification during the sign-in process.  
* Multifactor authentication provides additional security for your identities by requiring two or more elements to fully authenticate.  
	- Something the user knows – this might be a challenge question.  
	- Something the user has – this might be a code that's sent to the user's mobile phone.  
	- Something the user is – this is typically some sort of biometric property, such as a fingerprint or face scan.  
* 3 passwordless authentication methods:  
	- Windows Hello for Business: biometric and PIN credentials  
	- Microsoft Authenticator app: notification to phone to type in the number provided and then provide biometric or PIN to confirm  
	- FIDO2 (Fast Identity Online) security keys: typically USB devices. Hardware device that handles authentication.  
* Microsoft Entra External ID refers to all the ways you can securely interact with users outside of your organization.  
	- Business to business  
	- Business to customer  
* Azure Conditional Access: a tool that Microsoft Entra ID uses to allow (or deny) access to resources based on identity signals such as who the user is, where the user is and what device the user is requesting access from. Good when:  
	- Require MFA  
	- Require use of managed devices  
	- Require use of approved client apps  
	- Block access from certain locations  
* Principle of least privilege says you should only grant access up to the level needed to complete a task.  
* Azure role-based access control (Azure RBAC): Azure built-in roles and each role has an associated set of access permissions that relate to that role. So you assign access in groups instead of individually.  
* Role-based access control is applied to a scope  
* Scopes include:  
	- A management group (a collection of multiple subscriptions).  
	- A single subscription.  
	- A resource group.  
	- A single resource.  
* Azure RBAC is enforced on any action that's initiated against an Azure resource that passes through Azure Resource Manager from the Azure portal  
* Zero trust is a security model that assumes breach at the outset, and then verifies each request as though it originated from an uncontrolled network.  
	- Verify explicitly - Always authenticate and authorize based on all available data points.  
	- Use least privilege access - Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.  
	- Assume breach - Minimize blast radius and segment access. Verify end-to-end encryption. Use analytics to get visibility, drive threat detection, and improve defenses.  
* Defense in depth is a layered approach that protects information and prevents it from being stolen by those who are not authorized to access it.  
	- The physical security layer is the first line of defense to protect computing hardware in the datacenter.  
	- The identity and access layer controls access to infrastructure and change control, uses SSO and MFA, and involves auditing events and changes.  
	- The perimeter layer uses distributed denial of service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for users. Firewalls.  
	- The network layer limits communication between resources through segmentation and access controls. Deny by default.  
	- The compute layer secures access to virtual machines. Implement endpoint protection.  
	- The application layer helps ensure that applications are secure and free of security vulnerabilities. Security is a design requirement.  
	- The data layer controls access to business and customer data that you need to protect.  
* Defender for Cloud is a monitoring tool for security posture management and threat protection. Has security alerts.  
* For Azure machines, deployment is handled directly. For hybrid and multi-cloud environments, Microsoft Defender plans are extended to non-Azure * machines with the help of Azure Arc  
		
# Describe Azure management and governance (30–35%)
* Azure operational expenses depend on:  
	- Resource type  
	- Consumption: pay for what you use or commit to a certain usage  
	- Maintenance  
	- Geography  
	- Subscription type  
	- Azure Marketplace  
* Performance tier, access tier, redundancy settings, licensing for the OS, processors, # of cores for the VM, network traffic bandwidth pricing for inbound vs outbound  
* Cost Management provides the ability to quickly check Azure resource costs, create alerts based on resource spend, and create budgets that can be used to automate management of resources.  
	- Cost analysis is a subset of Cost Management that provides a quick visual for your Azure costs.  
	- Cost alerts provide a single location to quickly check on all of the different alert types that may show up in the Cost Management service.  
	  	- Budget alerts  
		- Credit alerts  
		- Department spending quota alerts  
* Resource tags provide metadata about your resources.  
	- You can add, modify, or delete resource tags through Windows PowerShell, the Azure CLI, Azure Resource Manager templates, the REST API, or the Azure portal.  
* Describe Features and Tools in Azure for Governance and Compliance  
* Microsoft Purview is a family of data governance, risk, and compliance solutions that helps you get a single, unified view into your data.  
	- Automated data discovery  
	- Sensitive data classification  
	- End-to-end data lineage  
* 2 solution areas:  
	- Risk and compliance  
		- Protect sensitive data across clouds, apps, and devices.  
		- Identify data risks and manage regulatory compliance requirements.  
		- Get started with regulatory compliance.  
	- Unified data governance  
		- Create an up-to-date map of your entire data estate that includes data classification and end-to-end lineage.  
		- Identify where sensitive data is stored in your estate.  
		- Create a secure environment for data consumers to find valuable data.  
		- Generate insights about how your data is stored and used.  
		- Manage access to the data in your estate securely and at scale.  
* Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit your resources. The policies enforce different rules across your resource configurations so that those configurations stay compliant with corporate standards.  
	- An Azure Policy initiative is a way of grouping related policies together.  
* Resource locks prevent resources from being accidentally deleted or changed. They are inherited. 2 types:  
	- Delete means authorized users can still read and modify a resource, but they can't delete the resource.  
	- ReadOnly means authorized users can read a resource, but they can't delete or update the resource. Applying this lock is similar to restricting all authorized users to the permissions granted by the Reader role.  
* Service Trust portal is a portal that provides access to various content, tools, and other resources about Microsoft security, privacy, and compliance practices.  
* Describe features and tools for managing and deploying Azure resources  
* Azure portal is a web-based, unified console that provides an alternative to command-line tools.  
	- Build, manage, and monitor everything from simple web apps to complex cloud deployments  
	- Create custom dashboards for an organized view of resources  
	- Configure accessibility options for an optimal experience  
* Azure Cloud Shell is a browser-based shell tool that allows you to create, configure, and manage Azure resources using a shell.  
	- Supports both Azure PowerShell and the Azure Command Line Interface (CLI), which is a Bash shell.  
	- Azure PowerShell is a shell with which you can run commands.. command-lets (cmdlets) which call the Azure REST API to perform management tasks in Azure.  
	- Azure CLI is a shell with which you can run commands but it uses Bash commands.  
* Azure Arc lets you extend your Azure compliance and monitoring to your hybrid and multi-cloud configurations. It simplifies governance and management by delivering a consistent multi-cloud and on-premises management platform.  
	- Can modify servers, kubernetes clusters, Azure data services, SQL Server, Virtual machines (preview)  
* Azure Resource Manager (ARM) is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in your Azure account.  
	- Azure ARM template is a JSON file that defines what resources you want to deploy to Azure. Infrastructure as code.  
		- Declarative syntax  
		- Repeatable results  
		- Orchestration  
		- Modular files  
		- Extensibility  
	- Bicep is a language that uses declarative syntax to deploy Azure resources. A Bicep file defines the infrastructure and configuration.  
		- Support for all resource types and API versions  
		- Simple syntax  
		- Repeatable results  
		- Orchestration  
		- Modularity  
* Describe monitoring tools in Azure  
* Azure Advisor evaluates your Azure resources and makes recommendations to help improve reliability, security, and performance, achieve operational excellence, and reduce costs. Recommendations:  
	- Reliability  
	- Security  
	- Performance  
	- Operational excellence  
	- Cost  
* Azure Service Health helps you keep track of Azure resource, both your specifically deployed resources and the overall status of Azure.  
	- Azure Status informs you of service outages in Azure on the Azure Status page  
	- Service Health tells of service impacting communications about outages, planned maintenance activities, and other health advisories  
	- Resource Health provides information about the health of your individual cloud resources, such as a specific virtual machine instance   
* Azure Monitor is a platform for collecting data on your resources, analyzing that data, visualizing the information, and even acting on the results.   Azure Monitor can monitor Azure resources, your on-premises resources, and even multi-cloud resources. you can use the data to help you react to critical events in real time, through alerts delivered to teams.  
* Azure Log Analytics is the tool in the Azure portal where you’ll write and run log queries on the data gathered by Azure Monitor and sort, filter, and analyze the records. You can write an advanced query to perform statistical analysis and visualize the results in a chart to identify a particular trend.  
* Azure Monitor Alerts are an automated way to stay informed when Azure Monitor detects a threshold being crossed and can also attempt corrective action.  
	- Alerts can be set up to monitor the logs and trigger on certain log events, or they can be set to monitor metrics and trigger when certain metrics are crossed.  
* Application Insights monitors your web applications running in Azure, on-premises, or in a different cloud environment. Configure by installing an SDK in your application, or you can use the Application Insights agent. Monitor:  
	- Request rates, response times, and failure rates  
	- Dependency rates, response times, and failure rates, to show whether external services are slowing down performance  
	- Page views and load performance reported by users' browsers  
	- AJAX calls from web pages, including rates, response times, and failure rates  
	- User and session counts  
	- Performance counters from Windows or Linux server machines, such as CPU, memory, and network usage  
END
