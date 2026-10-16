What's a net cat? — CyLab Security Academy (picoCTF)

**Category:** General Skills  
**Difficulty:** Easy  
**Platform:** CyLab Security Academy (formerly picoCTF)  
**Date Solved:** October 16, 2026  
**Author:** Ikehi Isaac

---

## Challenge Description

> Using netcat (nc) is going to be pretty important. Can you connect to `xebec.cylabacademy.net` at port `18863` to get the flag?

---

## What I Learned

- What **netcat (nc)** is and why it's important in cybersecurity
- How to connect to a remote host and port using `nc`
- How to read the response from a service
- Installing netcat on Termux (Android)

---

## Tools Used

| Tool | Purpose |
|------|---------|
| `nc` (netcat) | Connect to a remote host and port |
| Termux | Terminal environment on Android |
| `pkg install netcat-openbsd` | Installed netcat on Termux |

---

## Step-by-Step Solution

### Step 1: Install netcat on Termux

Netcat doesn't come pre-installed on Termux. Install it with:

```bash
pkg install netcat-openbsd -y
```

Step 2: Connect to the remote service

The challenge gives:

· Host: xebec.cylabacademy.net
· Port: 18863

Command:

```bash
nc xebec.cylabacademy.net 18863
```

Why this works:

· nc = netcat, a tool for reading and writing to network connections
· First argument = the host to connect to
· Second argument = the port to connect to

Step 3: Read the flag

The server responded with:

```
You're on your way to becoming the net cat master
academy{nEtCat_Mast3ry_AFf1FE8E}
```

Step 4: Submit the flag

Copied the entire string (including academy{}) and pasted it into the submission box. Accepted. ✅

---

Key Takeaways

1. Netcat is essential. It's one of the most-used tools in cybersecurity. SOC analysts use it to check if services are running. Penetration testers use it for reverse shells and banner grabbing.
2. Flag format matters. Always copy the whole string — prefix, contents, and closing brace.
3. Syntax is strict. nc host port works — nc [host] [port] does not.
4. Install tools as needed. Termux doesn't come with everything. pkg install gets what you need.

---

Why This Matters in Cybersecurity

Netcat is used in real security work for:

· Banner grabbing — identifying what service is running on a port
· Port checking — verifying if a service is reachable
· File transfer — moving files between systems
· Reverse shells — creating a connection back to an attacker (in pentesting)
· Debugging — testing custom protocols

Every CTF player, SOC analyst, and penetration tester knows nc.

---

References

· netcat manual
· CyLab Security Academy

---

Written by Ikehi Isaac — GitHub

```
