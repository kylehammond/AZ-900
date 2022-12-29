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


### Exercise - Create an Azure resource


## 2. Describe Azure copute and networking services

### Describe Azure Virtual Machines
### Exercise - Create an Azure Virtual Machine
### Describe Azure Virtual Desktop
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