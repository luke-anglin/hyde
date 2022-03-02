---
layout: post
title: Security Assessments
categories: cybersecurity
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week7.pdf
---

## Addressing Risk - The Security Cycle

Four activities

- Monitor
- Audit
- Improve
- Secure

## Permission Levels

- Promiscuous - everything allowed
- Permissive - anything not specifically prohibited
- Prudent
- Paranoid - very few things permitted

## Categories

- Security audit - often necessary for regulations
- Vulnerability assessment - no exploits, looks to see what is out there
- Penetration test - tries to exploit, rules of engagement (ROE) are very important

## Security Auditing

- Checking operations
- Asks:
  - Are policies understood and followed
  - Are the proper security controls in place
- Purpose:
  - Appropriate - Is the level of security control suitable for the risk it addresses?
  - Installed correctly
  - Addressing purpose

Auditing benchmarks - ISO 27002, CSF, ITIL, COBIT, COSO

### Audit Planning and Implementation

- Survey the site
- Review documentation
- Review risk analysis output - what are the critical systems (the database, perhaps? the accounting server for banking?)
- Review server and application logs - are there errors? are configs/permissions changing
- Review incident logs -
- Review results of penetration tests

### Collecting Audit Data

- Questionanaires
- Interviews
- Observation
- Checklists
- Reviewing documentation
- Reviewing configurations
- Reviewing policy
- Performing security testing

### Audit Areas

![Audit areas](https://i.imgur.com/CZgDv5f.png)

### Security Audit Report

- Findings
- Recommendations
  - Timeline for implementation
  - Level of risk
  - Management response
- Follow-up

### Post-Audit Activities

- Exit Interview
- Data Analysis

### Vulnerability vs. Penetration Testing

![V vs P](https://i.imgur.com/DPgtfq6.png)

#### Report format (both)

- Executive summary - for the Scott's of the world
- Summary of findings and recommendations
- Detailed findings
- Methodology
- References
- Appendices

## Security Monitoring

- Baselines
- Alarms, alerts, trends,
- CCTV
- Systems that spot irregular behavior

### Security Monitoring for Computer systems

- Real-time: host and network IDS, system integrity monitoring, data loss prevention (DLP)
- Non-real-time: application and system logging
- Log activities: host-based activity (startups and shutdowns), network and network devices (performance, logins . . .)

#### Types of log information to capture

**False positives** and **false negatives**!

- Event logs - general
- Access logs - requests for resources
- Security logs - security-related
- Audit logs - any events that provide more input to auditing

# IDSes

## Analysis methods

- Pattern or signature based IDSes: rule-based detection, pattern matching, stateful matching, known signatures for malwares and attacks
- Anomaly-based IDSes: Profile-based systems
- Common methods of detecting anomalies: Statistical methods, traffic methods, protocol patterns

# Backups

- Full
- Incremental
- Differential - only backs up the files that are different from the latest full backup

# Web servers and applications

## Parts

- Front end
- Application server
- Database server

## Common setups

- Apache
- Nginx
- IIS
- Open source setup: linux (the OS) apache (the web server) mysql (the relational DB) and php (application layer)

### Common misconfigurations

- Default passwords
- TLS certificates
- Scripts
- Remote admin
- Third party apps

## Web server attack methodology

1. Information gathering (`robots.txt`)
2. Web server footprinting - banner grabbing, getting mroe information
3. Website mirroring - `wget`
4. Vulnerability scanning - `nikto`
5. Session hijacking - XSS
6. Web server password cracking

## Attacks

- DoS
- MiTM
- Phishing
- Directory traversal up to `root`
- Hidden code
- Web cache poisoning
- Hidden code - `<input type=hidden name = "price">`

## Attack tools

- Wfetch
- Brutus
- THC-Hydra
- Metasploit
