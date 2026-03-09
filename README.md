# Google Cloud Data Breach Incident Response Lab

## Overview
This project demonstrates how to respond to and remediate a simulated data breach in a Google Cloud environment. The lab focuses on identifying vulnerabilities and applying security best practices to secure cloud resources.

The scenario involved vulnerabilities in:

- Compute Engine Virtual Machine
- Cloud Storage Bucket
- Firewall Rules

These vulnerabilities were identified using **Google Cloud Security Command Center** and remediated to improve compliance with **PCI DSS 3.2.1 security standards**.

---

## Skills Demonstrated

- Cloud Security Incident Response
- Vulnerability Identification
- Google Cloud Security Command Center
- Firewall Hardening
- Secure VM Deployment
- Cloud Storage Access Control
- PCI DSS Compliance Remediation

---

## Environment

- Platform: Google Cloud Platform (GCP)
- Services Used:
  - Security Command Center
  - Compute Engine
  - Cloud Storage
  - VPC Firewall Rules
  - Cloud Shell

---

# Incident Scenario

A simulated data breach was detected in the cloud environment. Several misconfigurations were identified that could allow unauthorized access.

The affected resources included:

- A vulnerable VM instance
- A publicly accessible storage bucket
- Overly permissive firewall rules

---

# Remediation Steps

## 1. Compute Engine Vulnerabilities

Issues identified:

- Public IP assigned to VM
- Secure boot disabled
- Default service account used
- Full API access enabled
- Malware communication detected

Remediation:

- Stopped the vulnerable VM `cc-app-01`
- Created a secure VM from a snapshot
- Deployed a new instance `cc-app-02`
- Deleted the compromised VM

---

## 2. Cloud Storage Bucket Misconfiguration

Issues identified:

- Public bucket access
- Public ACL permissions
- Bucket policy only disabled

Remediation:

- Switched bucket access control to **Uniform**
- Removed `allUsers` permissions
- Enforced bucket-level IAM policies

---

## 3. Firewall Security Issues

Issues identified:

- Open SSH access
- Open RDP access
- Firewall logging disabled

Remediation:

- Created restricted firewall rule `limit-ports`
- Allowed SSH only from:
