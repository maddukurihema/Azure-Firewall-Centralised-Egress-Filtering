# Azure Firewall Centralised Egress Filtering

## Project ID
24CC3046-P021

## Team
T225

## Guide
Dr P. Lakshmi

## Department / Section
CSE & S55

## Team Members

1. Maddukuri Hema - 2400033171
2. Yanamadala Aditya Swaroop -- 2400032999
3. Rachapudi Akhilesh -- 2400032599

---

## 1. Problem Statement

Multiple teams may require Internet access from Azure workloads.
Direct outbound access can make security policies difficult to manage
and may allow access to unauthorized websites and services.

This project introduces a centralized Azure Firewall to control
outbound traffic from Azure workloads.

---

## 2. Project Objective

The project has two main use cases:

1. Route all outbound traffic through one centralized Azure Firewall.
2. Enforce an FQDN allowlist for approved external destinations.

Additional objectives include configuring User Defined Routes,
creating FQDN application rules, and testing allowed and unapproved
outbound requests.

---

## 3. Key Concepts

### Egress
Egress means outbound traffic leaving an Azure workload and going
towards an external network or the Internet.

### FQDN
FQDN stands for Fully Qualified Domain Name.

Examples:
- www.google.com
- newerp.kluniversity.in

### FQDN Allowlist
An FQDN allowlist contains the approved domain names that workloads
are permitted to access.

### UDR
UDR stands for User Defined Route. It allows us to manually define
where network traffic should be sent.

---

## 4. Architecture

```text
                    INTERNET
                        |
                        v
              +-------------------+
              |   AZURE FIREWALL  |
              |   FQDN FILTERING  |
              +---------^---------+
                        |
                 0.0.0.0/0
                        |
                 ROUTE TABLE / UDR
                        |
                 +------^------+
                 | WORKLOAD VM |
                 | 10.0.2.4    |
                 +-------------+
