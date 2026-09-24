# WannaCry Ransomware Behavioral Analysis Lab

## Overview

This project focuses on the controlled analysis of **WannaCry ransomware** within an isolated virtual environment. The objective is to understand ransomware behavior, identify Indicators of Compromise (IOCs), observe network and system-level activity, and study defensive detection and mitigation techniques.

The laboratory environment was created using **VMware**, with Kali Linux used as the analysis workstation and Windows 7 configured as the isolated victim machine.

> **Educational Purpose:** This project was conducted strictly for cybersecurity education, malware analysis, and defensive research within an isolated virtual environment.

---

## Lab Environment

| Component            | Purpose                                |
| -------------------- | -------------------------------------- |
| VMware Workstation   | Virtualization platform                |
| Kali Linux           | Analysis and security workstation      |
| Windows 7            | Isolated victim/analysis target        |
| Wireshark            | Network traffic analysis               |
| Sysinternals/Procmon | Process and system activity monitoring |
| Windows Event Logs   | System activity investigation          |

### Lab Architecture

```text
                    Host Machine
                         |
                      VMware
                         |
              ┌──────────┴──────────┐
              │                     │
         Kali Linux             Windows 7
       Analysis VM             Victim VM
              │                     │
              └──────────┬──────────┘
                    Isolated Network
```

---

## Objectives

The main objectives of this project are:

* Understand the behavior of WannaCry ransomware.
* Analyze system and filesystem changes.
* Observe process and service activity.
* Examine network communication.
* Identify Indicators of Compromise (IOCs).
* Study ransomware-related detection techniques.
* Understand defensive mitigation strategies.
* Document observations in a reproducible laboratory environment.

---

## Methodology

The analysis follows a controlled malware-analysis workflow:

1. Configure the VMware laboratory environment.
2. Isolate the Windows 7 and Kali Linux virtual machines.
3. Create a clean snapshot of the Windows 7 environment.
4. Establish baseline system information.
5. Monitor system and network activity.
6. Conduct controlled malware analysis.
7. Record filesystem, process, registry, and network changes.
8. Extract relevant IOCs.
9. Analyze captured network traffic.
10. Document detection and mitigation techniques.
11. Restore the Windows 7 VM to its clean snapshot.

---

## Analysis Areas

### 1. Process Analysis

The analysis examines:

* Running processes
* Process creation
* Child processes
* Services
* Suspicious process behavior

Tools used include **Process Monitor** and Windows system monitoring utilities.

### 2. Filesystem Analysis

Observed changes include:

* Newly created files
* Modified files
* File extensions
* Directory changes
* Ransomware-related artifacts

### 3. Registry Analysis

Registry activity is examined to identify:

* Modified registry keys
* Configuration changes
* Persistence-related activity
* Other suspicious modifications

### 4. Network Analysis

Network traffic is captured and analyzed using **Wireshark**.

The analysis focuses on:

* Connection attempts
* Destination addresses
* Protocols
* DNS activity
* Suspicious traffic patterns

### 5. Indicators of Compromise

Relevant IOCs are documented, including:

* File hashes
* File names
* File paths
* IP addresses/domains observed during analysis
* Network indicators
* Registry artifacts
* Other behavioral indicators

---

## Defensive Analysis

The project also examines how organizations can detect and mitigate ransomware activity.

Key defensive areas include:

* Operating-system patching
* Network segmentation
* Endpoint monitoring
* Application control
* Offline and tested backups
* Least-privilege access
* Network traffic monitoring
* Security-event logging
* User awareness and phishing prevention

---

## Safety and Isolation

This project was performed in an **isolated VMware laboratory environment**.

The malware sample was **not uploaded to this repository**.

The Windows 7 virtual machine was isolated from the normal host network to prevent unintended interaction with external systems.

Snapshots were used to restore the virtual machine to a clean state after experimentation.

> **Important:** Do not execute ransomware on production systems, personal networks, or systems without explicit authorization.

---

## Project Structure

```text
wannacry-ransomware-analysis-lab/
│
├── README.md
│
├── lab-architecture/
│   └── architecture.png
│
├── analysis/
│   ├── process-analysis.md
│   ├── filesystem-analysis.md
│   ├── registry-analysis.md
│   ├── network-analysis.md
│   └── iocs.md
│
├── screenshots/
│   ├── vmware-lab.png
│   ├── process-monitor.png
│   └── wireshark-analysis.png
│
├── detection/
│   └── detection-notes.md
│
├── mitigation/
│   └── recommendations.md
│
```
