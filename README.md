Incident Response Playbooks

Comprehensive Cloud & Linux Incident Response Procedures
(Developed by En Mong)

📌 Overview

This repository contains two fully developed Incident Response Playbooks and a documented execution workflow that demonstrates hands-on incident-handling skills. These playbooks were developed in accordance with NIST SP 800-61r2, CISA guidance, and industry best practices.

📄 The included playbooks:

Scenario 5 — Cloud Misconfiguration: AWS S3 Over-Privileged Access
(Root cause: Default CSP privileges leading to sensitive data exposure)

Scenario 8 — Linux Rootkit Compromise: Slapper-Worm OpenSSL Exploit
(Root cause: Unpatched Linux service exploited for rootkit installation)

🖥️ The repository also includes:

A screenshot of scenario execution showing validation of incident scripts and automated detection logic.

These IR artifacts demonstrate operational readiness across cloud security, malware analysis, forensics, containment strategy, eradication, and post-incident documentation.

🚨 Scenario 5: AWS S3 Misconfiguration (Default CSP Privileges)

Scenario 5 Playbook

This playbook outlines a full end-to-end response to an incident where sensitive tax/financial data becomes exposed due to excessively permissive default IAM roles (e.g., AWS ReadOnlyAccess), resulting in unauthorized vendor access.

🔍 Key Incident Elements

Over-privileged default IAM policy

Unauthorized vendor access to S3 buckets

Violations of least-privilege principles

Shared bucket segmentation issues

🔧 Tools & Platforms (From the Playbook)

AWS IAM, S3 Access Logs, CloudTrail, Macie

QRadar SIEM, Nessus, Suricata IPS, FortiGate

Chain-of-custody workflows & forensic logging

🛑 Containment Actions Demonstrated

Immediate revocation of excessive IAM permissions

Deny-all bucket policy during investigation

Suspension of vendor IAM roles

CloudTrail log export & evidence snapshotting

🔁 Eradication & Recovery Skills Shown

Custom least-privilege IAM policy creation

Re-segmentation of sensitive buckets

SSE-KMS encryption enablement

72-hour log analysis for validation

📘 References Used

NIST SP 800-61r2, CISA Federal IR Playbooks
(explicitly cited within the playbook)

🐧 Scenario 8: Rootkit Installed on Linux Development Server

Scenario 8 Playbook

This playbook documents the response to a Slapper Worm–style rootkit compromise on a Linux development server, involving unauthorized lateral movement, privilege escalation, and possible source code integrity risk.

🔍 Key Incident Elements

Linux rootkit identification

OpenSSL exploit used by Slapper Worm variants

Unauthorized SSH & process manipulation

Potential CI/CD pipeline exposure

🔧 Tools & Techniques Demonstrated

chkrootkit, rkhunter, AIDE/Tripwire

Volatility Framework (memory forensics)

Disk imaging (dd, FTK Imager)

SIEM correlation (QRadar, ELK, Suricata IDS)

🛑 Containment Actions Demonstrated

Network isolation without reboot (to preserve volatile evidence)

Memory capture + file system snapshot

SSH key rotation & disabling compromised accounts

Enhanced SIEM monitoring & correlation rules

🔁 Eradication & Recovery Skills Shown

Removal of malicious kernel modules & persistence

OpenSSL patching and Linux hardening

Reconstruction from known-good images

Integrity validation of code repositories

▶️ Execution Evidence

The repository includes a screenshot demonstrating scenario execution validation, automated logic, and shell-based playbook handling.

📸 Execution Screenshot
(From: “Incident Response Handling Playbooks”)

Shows:

Scripted scenario handling (playbook.sh)

Dynamic selection of executed scenario numbers

Terminal output verifying correct incident workflow branching.

🏗️ Skills Demonstrated
✔ Cloud Security & Governance

IAM hardening • S3 segmentation • vendor access control • Macie & CloudTrail analytics

✔ Linux Forensics & Malware Response

Rootkit detection • Slapper Worm exploitation analysis • memory forensics • integrity monitoring

✔ NIST-Aligned Incident Response

Preparation

Identification

Containment

Eradication

Recovery

Post-Incident Lessons Learned & Reporting

✔ Forensics & Evidence Handling

Chain-of-custody • artifact preservation • snapshotting • SIEM correlation

✔ Documentation & Reporting

Executive summaries • timelines • root cause analysis • regulatory implications

📁 Repository Structure (Recommended)
/
├── README.md
├── scenario-5-aws-s3-misconfiguration/
│   ├── Scenario_5_Playbook.pdf
│   └── notes/
├── scenario-8-linux-rootkit/
│   ├── Scenario_8_Playbook.pdf
│   └── indicators/
├── execution/
│   └── playbook_execution_screenshot.png
└── scripts/
    └── playbook.sh
