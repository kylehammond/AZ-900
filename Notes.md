# Describe cloud concepts (25-30%)

## Describe cloud computing

### What is cloud computing
Basic offerings are compute power and storage
computer power - how much processing can be done
storage - volume of data you can store

### Describe the shared responsibility model
(Cloud) Shared responsibility model - 
cloud provider - responsible for physical security, power, cooling, and network connectivity
- because customer is not colo with provider

customer - responsible for the data and information stored in cloud
- cloud provider should not see data

shared/depends on situ 
ex:
- cloud SQL - cloud provider resp. for maintaining actual DB - but customer resp. for data
- vm with SQL on it - customer responsible for all including patching, updates, data/info


See shared-responsibiilty.png

You’ll always be responsible for:
The information and data stored in the cloud
Devices that are allowed to connect to your cloud (cell phones, computers, and so on)
The accounts and identities of the people, services, and devices within your organization

The cloud provider is always responsible for:
The physical datacenter
The physical network
The physical hosts

Your service model will determine responsibility for things like:
Operating systems
Network controls
Applications
Identity and infrastructure


Type of model (Saas, PaaS, IaaS) will indicate how much resp is shared


On Premise model
- customer responsible for everything

### Define cloud models
Private cloud
- cloud used by a single entity
- may be hosted from own datacenter
- may be hosted third party at dedicated datacenter offsite
- key features:
    Organizations have complete control over resources and security
    Data is not collocated with other organizations’ data
    Hardware must be purchased for startup and maintenance
    Organizations are responsible for hardware maintenance and updates

Public cloud
- cloud built, controlled, maintained by third party cloud provider
- has general public availability
- key features:
    No capital expenditures to scale up
    Applications can be quickly provisioned and deprovisioned
    Organizations pay only for what they use
    Organizations don’t have complete control over resources and security

Hybrid cloud
- can allow for private to surge into public
- allows customer to choose which services are private or public (enhanced security options)
- key features:
  Provides the most flexibility
  Organizations determine where to run their applications
  Organizations control security, compliance, or legal requirements

Multi-cloud
- increasingly likely
- using multiple public clouds
- could be due to mid-migration
- could be to use features of diff clouds

Azure Arc
- set of tools to help you manage public, private, hybrid, or multi-cloud

Azure VMware Solution
- Azure's VMware solution

### Describe the consumption-based model
CapEx - capital expenditure 
- usually one-time, up front expenditure for tangible resource

OpEx - operational expenditure
- spend on svcs or products over time

Cloud computing is OpEx due to consumption-based model

not paying for physical infrastructure, electricity, security, or any other datacenter costs

you are paying for IT resources used

consumption based model benefits
- no upfront costs
- no need to purchase and manage costly infra 
- the ability to pay for more resources 
- ability to stop paying for resources





## Describe the benefits of using cloud services


## Describe cloud service types


# Describe Azure architecture and services (35-40%)

## Describe the core architectural components of Azure
## Describe Azure copute and networking services
## Describe Azure storage services
## Describe Azure identity, access, and security


# Describe Azure management and governance (30-35%)

## Describe cost management in Azure
## Describe features and tools in Azure for governance and compliance
## Describe features and tools for managing and deploying Azure resources
## Describe monitoring tools in Azure



### Practice tests
http://www.examtopics.com
https://www.whizlabs.com/learn/course/microsoft-azure-az-900
