# Start Your Cyber Security Journey — TryHackMe Notes

> **Module:** Start Your Cyber Security Journey
> **Platform:** TryHackMe
> **Rooms Covered:** Offensive Security Intro · Defensive Security Intro · Careers in Cyber

---

## Room 1 — Offensive Security Intro

### What is Offensive Security?

Offensive security means **thinking and acting like a hacker** — but with permission. The goal is to find vulnerabilities in systems before real attackers do, so they can be fixed.

> **The core idea:** To beat a hacker, you have to think like one.

Two broad sides of cybersecurity:

| Side | Goal |
|------|------|
| **Offensive Security** | Break into systems, find weaknesses, exploit vulnerabilities |
| **Defensive Security** | Protect systems, detect attacks, respond to incidents |

---

### Practical — Hacking a Fake Bank (FakeBank)

TryHackMe simulates hacking a fake bank website to demonstrate how offensive security works in practice.

**Tool used: `gobuster`**

`gobuster` is a command-line tool used to brute-force hidden directories and pages on a website by trying a wordlist of common names.

```bash
gobuster dir -u http://fakebank.com -w wordlist.txt
```

| Flag | Meaning |
|------|---------|
| `dir` | Directory/file brute-forcing mode |
| `-u` | Target URL |
| `-w` | Wordlist file to use |

**What happened:**
- Gobuster discovered a hidden page: `/bank-transfer`
- This page was not linked anywhere on the site but was still accessible
- A real attacker could use this to perform unauthorized transfers
- A penetration tester would report this as a **security vulnerability**

> **Key takeaway:** Just because a page isn't linked doesn't mean it's hidden. Security through obscurity is not real security.

---

### Offensive Security Careers

| Role | What They Do |
|------|-------------|
| **Penetration Tester** | Paid to ethically hack into systems to find vulnerabilities |
| **Red Teamer** | Simulates full real-world attacks to test an organisation's detection and response |
| **Security Engineer** | Designs and builds secure systems and fixes vulnerabilities found by testers |

---

## Room 2 — Defensive Security Intro

### What is Defensive Security?

Defensive security focuses on **preventing, detecting, and responding** to cyber attacks. Unlike offensive security, defenders protect systems and networks rather than breaking into them.

**Two main tasks of defensive security:**
1. Preventing attacks from happening in the first place
2. Detecting and responding when attacks do happen

---

### Security Operations Center (SOC)

A **SOC** is a team of cybersecurity professionals who monitor an organisation's networks and systems **24/7** for malicious activity.

**What a SOC team does:**
- Monitors logs and alerts from systems
- Investigates suspicious activity
- Responds to security incidents
- Ensures vulnerabilities are patched

**Areas the SOC covers:**

| Area | Description |
|------|-------------|
| **Threat Intelligence** | Gathering information about current and future attackers |
| **DFIR** | Digital Forensics & Incident Response |
| **Malware Analysis** | Analysing malicious software to understand how it works |

---

### Threat Intelligence

**Threat Intelligence** means collecting and analysing data about potential attackers — their tools, tactics, and motives — so defenders can better prepare.

- **Goal:** Understand who might attack you and how
- **Sources:** Open-source feeds, dark web, incident reports, vendor reports
- **Output:** Actionable intelligence to help the SOC detect and block threats

> Threat intelligence helps shift defence from **reactive** (responding after an attack) to **proactive** (anticipating attacks before they happen).

---

### Digital Forensics and Incident Response (DFIR)

#### Digital Forensics
The process of collecting and analysing **digital evidence** from computers, phones, and networks — typically after an attack or crime.

**Forensics investigators look at:**
- File system — deleted files, modification timestamps
- System memory — running processes, open connections at time of attack
- System logs — what happened and when
- Network logs — communication records

#### Incident Response
A structured process for **handling a cyberattack** while minimising damage and recovering quickly.

**The 4 phases of Incident Response:**

| Phase | Description |
|-------|-------------|
| **1. Preparation** | Having a plan, trained team, and tools ready before an attack |
| **2. Detection & Analysis** | Identifying that an incident has occurred and understanding its scope |
| **3. Containment, Eradication & Recovery** | Stopping the attack, removing the threat, restoring systems |
| **4. Post-Incident Activity** | Reviewing what happened and improving defences |

---

### Malware Analysis

**Malware** (malicious software) is any software intentionally designed to cause harm.

| Type | Description |
|------|-------------|
| **Virus** | Attaches itself to a legitimate file and spreads when that file is run |
| **Trojan Horse** | Disguises itself as a legitimate program to trick users into running it |
| **Ransomware** | Encrypts the victim's files and demands payment for the decryption key |

**Two approaches to malware analysis:**

| Approach | Description |
|----------|-------------|
| **Static Analysis** | Examining the malware without running it — reading the code, strings, file structure |
| **Dynamic Analysis** | Running the malware in a safe isolated environment (sandbox) and observing its behaviour |

---

### SIEM — Security Information and Event Management

A **SIEM** is a tool that collects logs and events from across an organisation's systems and presents them in one place for analysis.

- Aggregates logs from firewalls, servers, endpoints, and applications
- Correlates events to detect patterns that indicate an attack
- Generates alerts for the SOC to investigate
- Examples: **Splunk**, **IBM QRadar**, **Microsoft Sentinel**

> **For a SOC Analyst:** The SIEM is your main dashboard. Most of your day involves investigating SIEM alerts.

---

## Room 3 — Careers in Cyber

### Why Cybersecurity?

- Massive global talent shortage — millions of unfilled positions worldwide
- High salaries compared to other tech fields
- Constantly evolving — never the same work twice
- Direct impact — your work protects real people and organisations

---

### Cyber Security Career Paths

#### Security Analyst
Monitors and protects an organisation's systems by investigating alerts and incidents.

- Works with the SIEM to review logs and alerts
- Responds to threats and escalates serious incidents
- Produces reports on security posture
- **Entry point for most people getting into cyber**

---

#### Security Engineer
Builds and maintains the tools and systems that keep an organisation secure.

- Designs firewalls, SIEM configurations, detection rules
- Fixes vulnerabilities identified by penetration testers
- Bridges the gap between IT and security

---

#### Incident Responder
First responder when a cyberattack occurs — contains the damage and restores systems.

- Works under pressure during live incidents
- Follows the incident response process (Preparation → Detection → Containment → Recovery)
- Produces detailed post-incident reports

---

#### Digital Forensics Examiner
Investigates cybercrime and collects court-admissible digital evidence.

- Recovers deleted files and analyses system artefacts
- Maintains a strict **chain of custody** for evidence
- Works with law enforcement or legal teams

---

#### Malware Analyst
Analyses malicious software to understand how it works and how to defend against it.

- Reverse engineers malware using tools like IDA Pro, Ghidra
- Writes threat reports and indicators of compromise (IOCs)
- Also known as a **reverse engineer**

---

#### Penetration Tester
Ethically hacks into systems — with written permission — to find vulnerabilities before real attackers do.

- Conducts tests on web apps, networks, and physical security
- Produces a detailed report of findings and recommendations
- Uses the same tools as real attackers

---

#### Red Teamer
Takes penetration testing further — simulates a full, realistic attack against an organisation to test its **people, processes, and technology**.

- Goes beyond finding vulnerabilities — tests whether the SOC can detect and respond
- Uses advanced techniques to stay undetected (like real attackers)
- Provides the most realistic measure of an organisation's security posture

---

### Career Path Summary

| Role | Focus | Good For |
|------|-------|----------|
| Security Analyst | Detection & monitoring | Starting out in cyber |
| Security Engineer | Building & maintaining defences | Those with a dev/IT background |
| Incident Responder | Handling live attacks | People who work well under pressure |
| Digital Forensics | Investigating after attacks | Detail-oriented, methodical thinkers |
| Malware Analyst | Understanding malicious code | Those with a programming background |
| Penetration Tester | Finding vulnerabilities | Those who love problem-solving and hacking |
| Red Teamer | Simulating real-world attacks | Experienced pentesters |

---
