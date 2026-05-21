Securing a Web Application on GCP 🌐
> Designed and secured a web application environment on Google Cloud Platform — implementing IAM hardening, cloud security controls, and misconfiguration remediation to protect workloads from unauthorised access.
![GCP](https://img.shields.io/badge/Cloud-GCP-4285F4?style=flat&logo=googlecloud)
![Cloud Armor](https://img.shields.io/badge/WAF-Cloud_Armor-4285F4?style=flat)
![HIPAA](https://img.shields.io/badge/Security-Hardening-green?style=flat)
---
📌 Overview
This project focuses on hardening a GCP-hosted web application — moving from a baseline misconfigured state to a security-hardened, audit-ready posture across compute, networking, identity, and application layers.
---
🔐 Security Controls Implemented
Identity & Access Management
Control	Before	After
Service account keys	Static JSON keys	Workload Identity — no keys
IAM roles	Primitive Editor role	Custom least-privilege roles
Storage access	AllUsers on buckets	Uniform bucket-level access
Network Security
Control	Implementation
WAF	Cloud Armor — OWASP Core Rule Set
HTTPS	HTTP → HTTPS redirect enforced
Database	Cloud SQL private IP only (no public)
Firewall	Deny-all default; explicit allow rules
SSH	OS Login; direct SSH from internet blocked
Application Layer
Security headers: HSTS, X-Frame-Options, CSP
Secrets in Secret Manager — none in env vars or code
Container scanning via Artifact Registry
TLS 1.2+ enforced; TLS 1.0/1.1 disabled
Monitoring
Cloud Audit Logs — Admin Activity + Data Access
Security Command Center findings reviewed and remediated
Cloud Armor request logging enabled
---
🛠️ Key Misconfigurations Remediated
Finding	Risk	Fix
Public Cloud Storage buckets	Data exposure	Uniform access + remove allUsers
Editor role on service account	Privilege escalation	Custom least-privilege role
Static SA keys	Credential theft	Workload Identity
Cloud SQL public IP	Attack surface	Private IP + Private Service Connect
HTTP allowed	MITM	Redirect all to HTTPS
Audit logs disabled	Blind spots	Enable Data Access logging
---
📚 Lessons Learned
Security Command Center Premium surfaces misconfigurations automatically — best starting point
Workload Identity migration requires careful SA mapping — test in dev first
Cloud Armor sensitivity level 2 is safe for most apps; level 3 needs tuning
Cloud SQL SSL must be set at instance level AND in the connection string
---
👤 Author
Moses Gnamisan Daniel — Cloud Security & DevSecOps Engineer
![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin)
