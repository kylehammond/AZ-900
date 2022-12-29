# Describe cloud concepts (25-30%)

## 1. Describe cloud computing

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

Consumption based model info
- Cloud computing is OpEx due to consumption-based model
- 
- not paying for physical infrastructure, electricity, security, or any other datacenter costs

- you are paying for IT resources used

consumption based model benefits
- no upfront costs
- no need to purchase and manage costly infra 
- the ability to pay for more resources 
- ability to stop paying for resources





## 2. Describe the benefits of using cloud services
### Describe the benefits of high availability and scalability in the cloud
- High availability
  - Azure SLA's - includes up time, down time, credit if sla not met
  - 100% up time would be very expensive because it'd have to duplicate everything
  - 99% - unavailable for up to 1.68 hrs per week or 7.2hrs per month - is cumulative
  - 99.9% - 10 min per week or 43.2 per month

- Scalability
  - the ability to adjust resources to meet demand

- Vertical scaling
  - add more CPUs or RAM to the virtual machine (or drop)

- Horizontal scaling
  - add additional virtual machines or containers, scaling out (or drop)

### Describe the benefits of reliability and predictability in the cloud
- Reliability
  - ability of a system to recover from failures and continue to function.
  - pillar of Microsoft Azure Well-Architected Framwork
  - the cloud enables you to have resources deployed in regions around the world
  - even if one region has a catastrophic event other regions are still up and running (if you take advantage of this in your design it can switch)
- Predictability
  - Performance
    - Autoscaling, load balancing, and high availability are just some of the cloud concepts that support performance predictability
      - autoscaling can deploy additional resources to meet the demand, and then scale back when the demand drops
      - load balancing can help redirect some overload to less stressed areas
  - Cost
    - you can track your resource use in real time
    - monitor resources for effiency
    - see trends and patterns
    - estimate using TCO or pricing calculators

### Describe the benefits of security and governance in the cloud
- can use set templates to enforce corporate standards and regulations
- can update all deployed resources as standards change
- can apply patches automatically
- ability to switch cloud model based on responsibility if you want more control to patch yourself or less to have it done for you
- cloud providers are typically well suited to handle things like distributed denial of service (DDoS) attacks

### Describe the benefits of manageability in the cloud
- Management of the cloud
    - Automatically scale resource deployment based on need.
    - Deploy resources based on a preconfigured template, removing the need for manual configuration.
    - Monitor the health of resources and automatically replace failing resources.
    - Receive automatic alerts based on configured metrics, so you’re aware of performance in real time.
- Management in the cloud
    - Through a web portal.
    - Using a command line interface.
    - Using APIs.
    - Using PowerShell.

## 3. Describe cloud service types

### Describe Infrastructure as as Service (IaaS)
- With IaaS, you’re essentially renting the hardware in a cloud datacenter, but what you do with that hardware is up to you.

- IaaS places the largest share of responsibility with you. The cloud provider is responsible for maintaining the physical infrastructure and its access to the internet. You’re responsible for installation and configuration, patching and updates, and security.

Common Scenarios:

- Lift-and-shift migration: You’re standing up cloud resources similar to your on-prem datacenter, and then simply moving the things running on-prem to running on the IaaS infrastructure.

- Testing and development: You have established configurations for development and test environments that you need to rapidly replicate. You can stand up or shut down the different environments rapidly with an IaaS structure, while maintaining complete control.

### Describe Platform as a Service (PaaS)
- Middle ground

- don't have to worry about the licensing or patching for operating systems and databases

- well suited to provide a complete development environment without the headache of maintaining all the development infrastructure

- Depending on the configuration, you or the cloud provider may be responsible for networking settings and connectivity within your cloud environment, network and application security, and the directory infrastructure

Common secnarios:

Some common scenarios where PaaS might make sense include:

- Development framework: PaaS provides a framework that developers can build upon to develop or customize cloud-based applications. Similar to the way you create an Excel macro, PaaS lets developers create applications using built-in software components. Cloud features such as scalability, high-availability, and multi-tenant capability are included, reducing the amount of coding that developers must do.

- Analytics or business intelligence: Tools provided as a service with PaaS allow organizations to analyze and mine their data, finding insights and patterns and predicting outcomes to improve forecasting, product design decisions, investment returns, and other business decisions.
  
### Describe Software as a Service (SaaS)
- With SaaS, you’re essentially renting or using a fully developed application

- In a SaaS environment you’re responsible for the data that you put into the system, the devices that you allow to connect to the system, and the users that have access. Nearly everything else falls to the cloud provider.
  
Common scenarios:

- Email and messaging.

- Business productivity applications.

- Finance and expense tracking.

