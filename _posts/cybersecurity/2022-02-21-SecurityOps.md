---
layout: post
categories: cybersecurity
title: Security Operations
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week6.pdf
---

There is an **SOC** (Security Operations Center) and potentially a **NOC** (Network Operations Center)

## Goals of an SOC

- Provide a means to **report** incidents
- Provide **handling** to constituents
- **Disseminate** info about the incidents to constituents/external parties

# Security administration

## Positions

- Security analyst - From tier 1 (greenies) to tier 3 (seniors, generally take large issues, in free time pen test and vulnerability test)
- Security engineer/architect
- SOC manager - oversees the analysts, reports to CISO
- CISO - Chief Information Security Officer (first guy to get fired)
- Incident response manager - manages technical aspects of responding to incidents

## Roles

- Control access
- Documentation, procedures, guidelines
  - critical (sensitive) assets list
  - organization's security process
  - policies, procedures, guidelines
  - compliance (regulatory (laws) or organizational)
- Disaster assessment and recovery
  - incident response team
  - emergency operations group

## Security Administration Responsibilities

- Implement/manage security tools
- Investigate suspicious activities and put them down
- Prevent downtime through DDOS or just when the company has to shut down to kill an incident
- Strategy on the security front
- Audit and compliance support

## Security outsourcing

- Advantages
  - More expertise
- Disadvantages
  - The outsourcing firm doesn't know enough about the internal
  - No in-house capability
  - Privacy/data security concerns (addressed below)
  - IP Ownership and legalistics (addressed below)

### Common outsourcing agreements

- Service-level agreement - **SLA** - who does what?
- Blanket purchase agreement - **BPA** - payment details
- Memorandum of understanding - **MOU** - commitment to each other, letter of intent, what we want to do 
- Interconnection of security agreement - **ISA** - technical requirements of interconnected assets - who owns what?

## Compliance

- Event logs
  - Too much will reduce processing speed and hog disk
- Compliance liaison - prevent setting weak passwords, for example.
- Remediation - fixing non-compliance, fixing broken things

# Professional Ethics 

* Be an example
* Encourage ethical procedures 
* Inform users about security things 

## Professional requirements 

An organization should . . . 

* collect only what it needs 
* not share info/data 
* keep its information updated 
* only use information for the purposes it was collected 
* destroy information that is no longer necessary 

# Personnel Security Principles 

* Limiting Access 
  * Least privilege or need to know - only grant access to what a user needs 
* Separation of duties 
  * Different users must contribute to get something done - you can't create a new vendor and cut a check to that vendor 
* Job rotation - prevents collusion 
* Mandatory vacations 
  * Another person will do their duties, preventing fraud 
* Security training and awareness 
  * Social engineering specifically (intimidation, name-dropping, appeals for help, phishing)

# Infrastructure Policies 

## Security Policy Hierarchy

![](https://i.imgur.com/BlCpYV0.png)

* Guidelines - NIST writes SP 800 guidelines 

### Terms 

* Functional policy - an organization's management diretion for security in functional areas like email, remote access, Internet surfing . . . use words like *will* and *should* 
  * Privacy policies are an example 
* Mandated requirements for hardware and software that address risks in the organization 
  * Antivirus 
  * Password generation token 
* Baselines - basic security configs 
* Guidelines - generally for acceptable system purchases

## Data Classification Standards 

Mandatory access control (MAC) requires these standards

* Value 
* Sensitivity - how bad is it if it gets posted on WikiLeaks
* Criticality - if this was lost, what's gonna happen? 

## Configuration Management 

* Process of managing changes to existing configurations 
* Evaluates how modifications might affect security 


Things you might want 

* Hardware configuration chart
* Patch and service pack management - checks often for updates/changes 

### Change Management Process 

* Configuration control - management of baseline settings for a system device 
* Change control - management of changes 
  * Peer review 
  * back out plans 
  * documentation 

### Change Control Procedure

![](https://i.imgur.com/lVET3zx.png)


# Application Software Security 

## System development life cycle 

![](https://i.imgur.com/srExp3C.png)

* Use before rolling out a big system like SIS 

## NIST System development life cycle 

![](https://i.imgur.com/ak5bw2S.png)

## Software Development Life cycle 

![](https://i.imgur.com/EApXTFq.png)

* No going backwards! Make a new version like 1.1

# Software Assurance, Development and Security 

* Validate input 
* Handle errors and exceptions 