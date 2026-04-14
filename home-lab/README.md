# Home Lab

**Status:** Coming post-Network+ exam (June 2026)  
**Platform:** VirtualBox on Windows 11 (16GB RAM)

---

## What's Being Built

A simulated corporate IT environment running entirely on a single machine using virtual machines. The goal is to replicate what a real helpdesk technician works with daily — Active Directory for user management, a ticketing system for tracking issues, and a domain-joined workstation to troubleshoot against.

---

## Planned VM Environment

| VM | OS | RAM | Role |
|----|-----|-----|------|
| DC01 | Windows Server 2022 | 2GB | Domain Controller — Active Directory, DNS |
| CLIENT01 | Windows 10 | 2GB | Domain-joined workstation |
| HELPDESK01 | Ubuntu Server 22.04 | 1GB | osTicket helpdesk ticketing system |

All VMs run on a VirtualBox Internal Network, isolated from the host's real network.

---

## Planned Labs

- **AD-01** — Windows Server setup, domain promotion, DNS configuration
- **AD-02** — Users, groups, and Organizational Units (OUs)
- **AD-03** — Group Policy Objects (GPOs) — enforce desktop policy, drive mapping
- **AD-04** — Join CLIENT01 to domain, test user login
- **HD-01** — osTicket install on Ubuntu Server (LAMP stack)
- **HD-02** — Configure ticket categories, departments, and SLAs
- **HD-03** — End-to-end ticket workflow — submit, assign, resolve, close

---

*Documentation will be added as each lab is completed.*
