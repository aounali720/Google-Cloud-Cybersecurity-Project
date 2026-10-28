# Google Cloud security incident lab

A Google Cloud training scenario involving an exposed storage bucket, broad firewall rules and an insecure VM configuration. I used Security Command Center and the Google Cloud console to review the findings and work through the recommended remediation steps.

This was a **simulated incident**, not a confirmed breach of an organization.

## Environment

- Google Cloud Security Command Center
- Compute Engine and Cloud Storage
- VPC firewall rules and Cloud Shell

## Findings and changes

| Area | What I found | What I changed |
| --- | --- | --- |
| Compute Engine | VM had a public address, disabled Secure Boot, default service account and broad API access | Stopped `cc-app-01`, created `cc-app-02` from a snapshot, and removed the old instance |
| Cloud Storage | Public access through `allUsers` and ACL configuration | Removed public permissions and switched to uniform bucket-level access |
| VPC firewall | Open SSH/RDP paths and disabled firewall logging | Added a more restrictive rule (`limit-ports`) and limited administrative network access |

The lab included checking relevant PCI DSS 3.2.1 requirements. Completing the exercise does **not** establish PCI DSS compliance, nor does it prove that every possible cloud risk was removed.

## Notes

The accompanying [lab report (PDF)](Google%20cloud%20secuirity%20project.pdf) has the original walkthrough and screenshots. Check current Google Cloud guidance before applying similar configuration changes in another environment.
