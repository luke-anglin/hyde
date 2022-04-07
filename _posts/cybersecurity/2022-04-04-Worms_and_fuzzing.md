---
title: Fuzzing and Worms
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week12.pdf
categories: cybersecurity
---

# Fuzzing

- Fuzzing is sending invalid data in hopes of causing an error (buffer overflow, segfault . . . )
  - Not just random input
  - Infinite space problem - infinite # of malformed input (infinite monkey theorem, eventually you'll cause an invalid input)
  - Mutational fuzzing - truncating/changing the vald input data
  - Generational fuzzing - has inside information about the application, tailors the fuzzes to that (open source software, unit testing . . . )
  - Heartbleed - example of above, in 2014, was a major vulnerability in OpenSSL relating to the heartbeat TLS connection (avoids repeating the handshake) (found by ethical hackers, and all was safe)

# CTF summary tips

- `strings <file>` to see if the flag is obvious
- `file <file>` to determine the type of the executable
- `chmod +x <file>` to make executable
- Run the program and see what it doees
- Fuzz the program to make it fail ungracefully, if possible
- Disassemble
  - `ndisasm -a <file>`
  - `objdump -D <file>`
- Debug
  - `gdb <file>`
  - `edb --run <file>`

# Slammer (Sapphire) Worm

- Fastest worm in history, affected >90% of vulnerable hosts in 10 mins
- 376 bytes
- Exploited MS SQL server
- Buffer overflow
- UDP port 1434
- Spreads via random IPs
- DoS (accidental)

## Slammer - the vulnerability

- `Ssnetlib.dll`
- `Sqlservr.exe`
- Builds 3 strings together into a 128 byte buffer in the stack, the second string, the database name, which _should_ be 16 chars or left.
- Top left corner of the datagram like the `04` in the picture signals the name of the database
- Uses `GetTickCount` as a seed for a random IP, then shuffles bits
- Sends data to jump to it's own code

## Blocking slammer

- `WS2_32!sentto()` API - blocks certain `sendto` calls
- Send blocking
- Stack tracing - sees that `sent to` is pointing to its own code, which shows its a worm
- Caller's address (CA)
- `buf <= CA < buf + len` - see if the worm code is included in the buffer: if `True`, then that's probably a worm!
- `buf: 0x1050db73 <= 0x1050dce9 < 0x1050dceb`

## Mitigation

- Reboot
- Patches
  - MS 02-039
  - SQL 2000 Service Pack 3
- ACL/Firewall rules on UDP port 1434

