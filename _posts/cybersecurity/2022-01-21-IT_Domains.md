---
layout: post
categories: cybersecurity
title: Seven Domains of IT
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week1.pdf
---

![Seven Domains](https://i.imgur.com/4gQRnBw.png)

## Seven Domains of a Typical IT Infrastructure

- User - deals with authentication
- Workstation - the computer/office
- LAN - segmentation and authentication
- LAN to WAN - our access point to the Internet, ingress/egress filtering with firewalls, IDS . . .
- WAN
- Remote Access Domain - hotels, coffee shop . . . vpns are important here for encryption
- System/Application Domain - Databases, web servers, application servers . . . this is what attackers are after, so need good encryption

# Linux Folder Structure

- `/dev` - pointers to storage and IO systems
- `/etc` - admin, password and shadow files
- `/home`
- `sbin` - admin binaries like daemons
- `/usr` - unique files to user

# Linux Password Architecture

- `/etc/passwd` - text file, human-readable, the `x` is where the password would be
- `/etc/shadow` - hashed passwords, everyone can read but only root can change it (though I'm not sure why you would)
  - Colon-delimited, user is at the beginning and then after colon is the hashed password, followed by some metadata
  - Metadata includes minimum and maximum days required between valid passwords/password changes
  - Hashed password = `"$id$salt$hashed"`
    - ID identifies the _type of hash_, like `$6` is `SHA512`
    - Salt is random data added

# Windows Password Architecture

![Windows Passwords](https://i.imgur.com/qc77zhE.png)

# Password Cracking

- Active online - _actively_ trying to guess online passwords
- Passive online - sniffing, running a program online
- Offline - dictionary-style, hybrid, brute-force

# John the Ripper

- Built into cyberrange
- `john shadow_file` first time, `john --show shadow_file` to dump the info again

# Assignments

- Lab 1 posted soon
- Read chapter 2 of book
