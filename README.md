# Hybrid Cloud Infrastructure Deployment (Hyper-V + Microsoft Azure)

## Overview

Designed and implemented a hybrid infrastructure environment that combines on-premises virtualized services with cloud-hosted web content. The project demonstrates how core internal services can remain locally hosted while public-facing content is migrated to Microsoft Azure for improved scalability, availability, and operational flexibility.

The solution includes:

* Hyper-V virtualized infrastructure
* DHCP and DNS services
* IIS web hosting
* Internal network segmentation
* Azure Storage Static Website hosting
* Basic governance and resource protection controls

---

## Architecture

### On-Premises Infrastructure

The local environment was deployed using Microsoft Hyper-V and consisted of:

* Internal Virtual Switch
* DHCP Server
* DNS Server
* IIS Web Server
* Database Server VM

All virtual machines communicated through an isolated internal network using dynamically assigned IP addresses provided by the DHCP service.

### Cloud Infrastructure

Public-facing web content was migrated to Microsoft Azure using:

* Azure Resource Group
* Azure Storage Account
* Static Website Hosting
* Resource Locks for governance

The cloud-hosted website was made publicly accessible through the Azure-generated endpoint.

---

## Objectives

* Build an isolated on-premises virtual network
* Deploy and validate DHCP, DNS, and IIS services
* Enable communication between virtual machines
* Host internal web content locally
* Migrate public-facing content to Azure
* Validate accessibility and functionality
* Implement basic governance controls

---

## Technologies Used

### Virtualization

* Microsoft Hyper-V
* Windows Server

### Networking

* DHCP
* DNS
* IPv4 Addressing
* Virtual Switching
* ICMP Connectivity Testing

### Web Services

* IIS Web Server

### Cloud

* Microsoft Azure
* Azure Storage Accounts
* Static Website Hosting

### Security & Governance

* Windows Firewall
* Azure Resource Locks

---

## Implementation

### Phase 1 – Local Infrastructure Deployment

Created an isolated virtual network using a Hyper-V Internal Virtual Switch.

Configured:

* Static IPv4 addressing on the host adapter
* DHCP scope and address allocation
* DNS services
* IIS web hosting

Deployed two virtual machines:

* Web Server
* Database Server

Validated:

* Dynamic IP allocation
* Name resolution
* VM-to-VM communication
* IIS website accessibility

---

### Phase 2 – Azure Migration

Provisioned Azure resources including:

* Resource Group
* Storage Account
* Static Website Hosting

Uploaded web content from the local environment to Azure and validated public accessibility using the generated endpoint.

---

### Bonus Implementation

Additional services were implemented to strengthen the environment:

#### DNS Server

* Forward Lookup Zone configuration
* Internal name resolution

#### Firewall Configuration

* Basic traffic filtering
* Service access validation

#### Resource Lock

* Protection against accidental deletion of Azure resources

---

## Validation and Testing

The following tests were successfully completed:

* DHCP address assignment verification
* DNS name resolution testing
* VM connectivity validation using ICMP
* IIS web service validation
* Azure static website deployment verification
* Public URL accessibility testing

---

## Key Learning Outcomes

### Networking

* DHCP scope creation and management
* DNS deployment and troubleshooting
* Internal network segmentation

### Virtualization

* Hyper-V virtual switch design
* VM provisioning and management
* Service deployment within isolated networks

### Cloud

* Azure Storage configuration
* Static website hosting
* Hybrid infrastructure concepts

### Security

* Firewall management
* Governance controls through resource locks
* Network isolation principles

---

## Challenges and Solutions

| Challenge                                            | Solution                                                                        |
| ---------------------------------------------------- | ------------------------------------------------------------------------------- |
| DHCP bindings not appearing                          | Assigned a static IP to the Hyper-V virtual adapter and restarted DHCP services |
| Azure resource restrictions in student subscription  | Utilized Microsoft Learn Sandbox and existing resource groups                   |
| Internal network isolation preventing direct uploads | Simulated migration using host-based file transfer                              |

---

## Future Improvements

Potential enhancements include:

* Site-to-Site VPN connectivity
* Azure Virtual Network integration
* Infrastructure as Code using Terraform
* Azure Monitor implementation
* Automated deployment pipelines
* Advanced firewall and security controls

---

## Outcome

Successfully deployed a functional hybrid environment that combines locally hosted infrastructure services with cloud-hosted web content. The project demonstrates practical experience with virtualization, networking, cloud migration, service validation, and hybrid architecture design principles.
