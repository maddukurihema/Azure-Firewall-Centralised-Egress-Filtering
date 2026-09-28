# TASK 4 :



1.Create and Configure a virtual network

2.Deploy virtual machines into the virtual Network

3.Configure Private and public IP addresses of Azure VMs

4.Configure Network security groups

5.Configure azure DNS for internal name resolution

6.configure azure DNS for external name resolution

                    Internet

&#x20;                      │

&#x20;                Public IP

&#x20;                      │

&#x20;               ┌──────┴──────┐

&#x20;               │   NSG       │

&#x20;               │ Allow SSH   │

&#x20;               └──────┬──────┘

&#x20;                      │

&#x20;             ┌────────┴────────┐

&#x20;             │  VNet           │	 |

&#x20;             │  az104-vnet     │	 |

&#x20;             │ 10.0.0.0/16     │	 |

&#x20;             │                 │

&#x20;             │  ┌───────────┐  │

&#x20;             │  │ Subnet    │  │

&#x20;             │  │ 10.0.1.0/24│ │

&#x20;             │  └─────┬─────┘  │

&#x20;             │        │        │

&#x20;             │   ┌────┴────┐   │

&#x20;             │   │ VM1     │   │

&#x20;             │   │ VM2     │   │

&#x20;             │   └─────────┘   │

&#x20;             └─────────────────┘

**VM1 and VM2** 
Username:azureuser
Password : klu@123456


Perfect! Your internal Azure DNS configuration is complete. ✅



Your output confirms:



Private DNS Zone: internal.az104.local exists.

VNet Link: az104-vnet-link

RegistrationEnabled: True

VirtualNetworkLinkState: Completed

ProvisioningState: Succeeded

DNS A records: both VMs have records:

az104-vm1 → A record

az104-vm2 → A record

You also have vm1 and vm2 records that we created manually.



The az104-vm1 and az104-vm2 records with TTL 10 are especially useful because automatic DNS registration is working.



**Task 4 — Internal DNS: DONE**



You can use this as your lab evidence:



Private DNS Zone: internal.az104.local

VNet: az104-vnet

VNet Link: az104-vnet-link

Registration: Enabled

Link State: Completed

DNS Records: az104-vm1, az104-vm2

Provisioning State: Succeeded




Yes — everything looks good now for Task 4. ✅



Based on the outputs you've shown, the important Azure resources are successfully configured:



VNet: az104-vnet — ✅

Subnet: default (10.0.1.0/24) — ✅

NSG: az104-nsg — ✅

SSH rule: port 22 allowed — ✅

VM1: az104-vm1 — Succeeded — ✅

VM2: az104-vm2 — Succeeded — ✅

Public IPs: static IPs configured — ✅

Private DNS: internal.az104.local — ✅

VNet DNS link: az104-vnet-link — Succeeded, registration enabled — ✅

Internal DNS records: az104-vm1 and az104-vm2 — ✅

Public DNS zone: az104labdemo.com — ✅

Public DNS A record: vm1 → 20.212.208.71 — Succeeded — ✅

