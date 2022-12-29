# Describe Azure architecture and services (35-40%)

## 1. Describe the core architectural components of Azure

### What is Microsoft Azure
... basic overview / marketing


### Get started with Azure accounts
- Azure subscription is primary requirement to use Azure
- see account-scope.png
- Account > Subscription > Resource Groups > Resources

Free account
- Free access to popular Azure products for 12 months.
- A credit to use for the first 30 days.
- Access to more than 25 products that are always free.

Free student account 
- Free access to certain Azure services for 12 months.
- A credit to use in the first 12 months.
- Free access to certain software developer tools.

### Exercise - Explore the Learn sandbox
Just played around in azure sandbox CLI

- type 'bash' to get to bash
- type 'pwsh' to switch to powershell
- az version
- az interactive - interactive mode  (exit to end)

### Describe Azure physical infrastructure 

- Physical infrastructure
    - Made up of datacenters, much like corporate ones, conceptually
    - Not directly accessible
  
  - Regions
    - 1 to many datacenters
    - networked together with low latency network
    - Azure balances automatically
  
  - Availability Zones
    - sub groupings of regions that are isolated from eachother 
    - connected by fiber
    - not all regions support Availability zones
    - in supported regions, at least 3 avail. zones

    - see availability-zones.png

  - Use availability zones in your apps
    - can run mission critical things inside these with a cost
    - primarily for VMs, managed disks, load balancers, SQL dbs
    - Az services categories
      - zonal services - pin resource to specific zone - VMs, managed disks, IP addresses
      - zone-redundant services - platform replicates automatically across zones - zone-redundant storage, SQL db
      - Non-regional services - always available from Az geographies and are resilient to zone-wide outages as well as region-wide outages

- Region pairs
  - For times when outage impact is bigger than one or more zone
  - Most regions paried with another at least 300 miles away in same geography (US, Europe, Asia, etc)
  - In case of natural disaster, civil unrest, power outages, physical network outages
  - not all svcs automatically replicate data or automatically fall back to cross replicate - must be configured

  - see region-pairs.png

  - Additional advantages
    - if extensive outage, one region of every pair prioritized to make sure at least one working ASAP
    - planned azure updates rolled out to pairs one region at a time
    - data continues to reside within same geography (except for Brazil South) as its pair for tax- and law-enforcement jurisdiction purposes

    - most paired in both directions to be backup for each (with exception of West India, Brazil South)
      - South India does not rely on West india (one-direction)
      - Brazil South paired with region outside its geography (South Central US) - However, SCUS not paired to Brazil South as its secondary region
  
- Sovereign Regions
  - Special isolated regions for compliance/legal reasons
  - US DoD Central, US Gov Virginia, US Gov Iowa, etc
  - China East, China North, etc - special partnership between MS and 21Vianet (maintains datacenters)

### Describe Azure management infrastructure 
- Resources, resource groups, subscriptions, accounts
  - see resource-group.png
  - Resource Groups are groupings of resources and is required
  - single resource can belong to ONLY one RG
  - groups can NOT be nested
  - applying an action or deleting a group applies to all resources in group

- Azure subscriptions
  - see subscriptions.png
  - unit of management, billing, and scale
  - links to an azure account
  - account required to have one sub, but can have multiple
  - types of subscription boundries
    - billing - separate billing reports and invoices
    - access countrol - access management policies 
  - Create additional Azure subscriptions
    - for environments/compliance
    - org structure
    - billing

- Azure management groups
  - provide a level of scope above subscriptions
  - allows you to apply governance - "all VMs must be in US West Region"
  - you can apply Azure role-based access control (Azure RBAC) - is applied to all subgroups
  - Management groups > Subscriptions > Resource groups > resources
  - see management-groups-subscriptions.png
  
  - 10,000 mgmt groups can be supported in a single directory
  - mgmt group tree can support up to six levels of depth (not including root or subscription level)
  - each mgmt group and subscription can only have one parent
  

### Exercise - Create an Azure resource


## 2. Describe Azure copute and networking services

### Describe Azure Virtual Machines
- Provides IaaS
- Control everything
- Maintain everything
- Can deploy templated VM's

- Scale VMs in Azure
  - Virtual machine scale sets
    - Azure helps automate work of creating and managing sets of identical load balanced VMs
    - handles the utilization monitoring for scaling for you
  
  - Virtual machine availability sets
    - tool that ensures VMs stagger updates and have varied power and network connectivity 
    - prevents loss of all VMs with a single network or power failure
    - groupings
      - Update domain 
        - groups VMs that can be rebooted at the same time
        - all of machines in group will be updated at same time 
        - will be given 30 min to recover before next update domain starts
      - Fault domain
        - gruops VMs by common power source and network switch  
        - by default, split by up to three fault domains
        - no additional cost for configuring - only pay for VMs
- Examples of when to use VMs
  - testing and development
  - when running apps in the cloud
  - when extending datacenter to the cloud
  - during disaster recovery

- Move to the cloud with VMs
  - lift and shift

- VM Resources
  - Things you can choose
    - size (purpose, number of cores, amt of RAM)
    - storage disks (HDD, SSD, etc)
    - networking (Vnet, pub IP address, port config)


### Exercise - Create an Azure Virtual Machine
az vm create \
  --resource-group learn-b7014ac3-9ddd-4676-a0d3-2f00b4a4c01a \
  --name my-vm \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys

az vm extension set \
  --resource-group learn-b7014ac3-9ddd-4676-a0d3-2f00b4a4c01a \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'


### Describe Azure Virtual Desktop
- Azure's VDI solution
- Enhance security
  - provides centralized security management with AAD, MFA, Role-based access controls (RBACs)
  - data and apps are separated from local hardware (confidential info risk low)
- Multi-session Windows 10 or Windows 11 deployment
  - allows multiple concurrent users on a single VM 

### Describe Azure Containers
### Describe Azure Functions
### Describe application hosting options
### Describe Azure Virtual Networking
### Exercise - Configure network access
### Describe Azure Virtual Private Networks
### Describe Azure ExpressRoute
### Describe Azure DNS


## 3. Describe Azure storage services

### Describe Azure storage accounts
### Describe Azure storage redundancy
### Describe Azure storage services
### Exercise - Create a storage blob
### Identify Azure data migration options
### Identify Azure file movement options


## 4. Describe Azure identity, access, and security

### Describe Azure directory services
### Describe Azure authentication methods
### Describe Azure external identities
### Describe Azure conditional access
### Describe Azure role-based access control
### Describe zero trust model
### Describe defense-in-depth
### Describe Microsoft Defender for Cloud