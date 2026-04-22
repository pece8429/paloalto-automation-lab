# Palo Alto Firewall Automation Lab (Ansible)

## 📌 Overview

This project simulates an enterprise firewall automation workflow using Ansible, modeled after real-world network and security operations.

It demonstrates how firewall rule requests can be processed end-to-end, including validation, object creation, policy deployment, commit operations, verification, and audit logging.

The project supports both:
- **Mock Mode** → fully runnable locally without a firewall
- **Real Mode** → designed to integrate with Palo Alto PAN-OS devices using Ansible collections

---

## 🎯 What This Project Demonstrates

- Request intake (ServiceNow-style JSON input)
- Input validation (required fields, IP format)
- Object creation (address objects)
- Firewall rule creation/update (idempotent logic)
- Commit step (simulated or real)
- Post-deployment verification
- Dry-run capability (`--check`)
- Structured audit and logging output
- Separation of concerns using Ansible roles

---

## 🏗️ Project Structure
paloalto-automation-lab/
│
├── inventory/
│ ├── firewall_hosts.ini
│ └── group_vars/
│ └── firewalls.yml
│
├── playbooks/
│ └── process_request.yml
│
├── roles/
│ └── palo_request/
│ └── tasks/
│ ├── main.yml
│ ├── validate.yml
│ ├── objects.yml
│ ├── policy.yml
│ ├── commit.yml
│ └── verify.yml
│
├── requests/
│ └── sample_request.json
│
├── reports/
│ └── (generated output files)
│
├── ansible.cfg
└── README.md


---

## 🔄 Workflow

Request (JSON)
↓
Validation
↓
Object Creation (Address Objects)
↓
Rule Creation / Update
↓
Commit
↓
Verification
↓
Audit Logging

