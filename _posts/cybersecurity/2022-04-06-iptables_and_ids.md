---
title: iptables and SnortIDS
categories: cybersecurity
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week12.pdf
layout: post
---

# iptables

- Linux-based IPv4 packet filter stored in `/usr/sbin/iptables`
- Uses the x_tables kernel module
- Chains have a default policy and rules
- Five predefined chains
  - PREROUTING - before routing decisions are made
  - INPUT - controls the behavior of any packets coming directly to that system - `iptables -P INPUT DROP`
  - FORWARD - incoming connections destined for a later computer (i.e they're forwarded)
  - OUTPUT - outgoing packets from that machine (will use this in lab)
  - POSTROUTING - after routing decisions are made
- Three most common policies and rules are **ACCEPT, DROP and REJECT**

## iptables Usage

- `iptables [command-type] [pattern-match options] -j [action]`
- `iptables -A INPUT -s 192.168.1.10/24 -j ACCEPT`
- `-A` - APPEND to input chain
- `-p tcp` - protocol
- `--dport ssh` - destination port ssh/22
- CIDR for a network range, just an IP for one

## iptables Important Connection States and Ports

- Generally the ports and the connection states are missed, need **new and established on INPUT**, only **established on OUTPUT**
- Make sure you use `-p tcp`
- `--dport ssh` is for the input because it's destined for our ssh port
- `--sport 22` is for the output because it's coming _from_ our ssh port
- `iptables -A INPUT -p tcp --dport ssh -s 192.168.100.10 -m state --state NEW,ESTABLISHED -j ACCEPT`
  - Allows new and established connections in
- `iptables -A OUTPUT -p tcp --sport 22 -d 192.168.100.10 -m state --state ESTABLISHED -j ACCEPT`
  - Only allows established connections out

## Rule saving

- Saving rules - `sudo /sbin/iptables-save`
- Listing rules - `iptables -L`
- Clear rules - `iptables -F`

# Snort Rules

`[action] [protocol] [source IP] [source port] [direction] [destination IP] [destination port]` - rule header

![examples](https://i.imgur.com/bhZiok4.png)

## BASE

- A web frontend to Snort
