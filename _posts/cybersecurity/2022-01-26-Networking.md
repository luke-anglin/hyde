---
layout: post
title: Network Scanning
categories: cybersecurity
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week2.pdf
---

# LAN

- Wireless access points gathers data on your home network, then it is given to the cable modem with a unique IP to work with the Internet
- `192.168` is not routable on the grand Internet, used for private networks

# IP Addressing

- Four sets of bytes for IPv4 (32 total), decimal dot notation
- IPv6 is 128 bits (16 bytes), colon-delimited in hex

# FTP

- Share files, but not secure! Use SFTP or SCP

# Networking Commands

![unix net](https://i.imgur.com/kY9miEW.png)

# Flags

- `SYN`
- `ACK`
- `RST` - 'disordered' termination (reset)
- `FIN` - ordered close to communications
- `PSH` - forces data delivery without buffering
- `URG` - urgent

# Scanning Method

1. Check for live systems - `ping`
2. Check for open ports - `nmap <options> <ip>`
3. Perform banner grabbing/fingerprinting
4. Look for vulnerabilities
5. Draw network diagrams

## Types of Scanning

![Scan types](https://i.imgur.com/uw6YH4e.png)
