Super SSH — CyLab Security Academy (picoCTF)

**Category:** General Skills  
**Difficulty:** Easy  
**Platform:** CyLab Security Academy (formerly picoCTF)  
**Date Solved:** October 16, 2026  
**Author:** Ikehi Isaac

---

## Challenge Description

> Using a Secure Shell (SSH) is going to be pretty important. Can you `ssh` as `ctf-player` to `chatelaine.cylabacademy.net` at port `47815` to get the flag?
>
> You'll also need the password `13792798`. If asked, accept the fingerprint with `yes`.

---

## What I Learned

- How to use **SSH** (Secure Shell) to connect to a remote machine
- The `-p` flag to specify a **non-standard port**
- Accepting an SSH fingerprint for a new host
- Navigating a remote filesystem via command line
- Reading a file with `cat`

---

## Tools Used

| Tool | Purpose |
|------|---------|
| `ssh` | Connect to remote server |
| `cat` | Read file contents |
| `ls` | List files in directory |

---

## Step-by-Step Solution

### Step 1: Open a terminal

On my Android phone, I used **Termux**. On desktop, any terminal works (Bash, PowerShell, etc.).

### Step 2: Connect to the remote machine via SSH

The challenge gives:
- Username: `ctf-player`
- Host: `chatelaine.cylabacademy.net`
- Port: `47815`
- Password: `13792798`

**Command:**
```bash
ssh ctf-player@chatelaine.cylabacademy.net -p 47815
```

Why -p 47815?
By default, SSH uses port 22. The challenge uses a non-standard port, so we specify it with the -p flag.

Step 3: Accept the fingerprint

On first connection, SSH asks:

```
The authenticity of host '[chatelaine.cylabacademy.net]:47815' can't be established.
ED25519 key fingerprint is SHA256:...
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type yes and press Enter.

Step 4: Enter the password

When prompted:

```
ctf-player@chatelaine.cylabacademy.net's password:
```

Type 13792798 and press Enter.

Note: The password will not appear as you type — that's normal for SSH. It's hidden for security.

Step 5: Explore the remote filesystem

Once logged in, list the files:

```bash
ls
```

Output:

```
flag.txt
```

Step 6: Read the flag

```bash
cat flag.txt
```

Output:

```
picoCTF{s3cur3_sh3ll_...}
```

Step 7: Submit the flag

Copy the flag string and paste it into the challenge submission box on CyLab Security Academy.

---

Key Takeaways

1. SSH connects to remote machines securely. It's the standard tool for managing Linux servers.
2. The -p flag specifies a port. Always check the challenge for the correct port.
3. Passwords are hidden when typed into SSH. This is a security feature, not a bug.
4. The remote shell works exactly like a local one. You can run ls, cat, cd, etc.
5. CyLab Security Academy is the new picoCTF. Same challenges, same platform, rebranded by Carnegie Mellon University.

---

Why This Matters in Cybersecurity

SSH is one of the most important tools in a security professional's toolkit:

· SOC Analysts use SSH to investigate remote servers during incidents.
· Penetration Testers use SSH to access compromised hosts.
· Cloud Engineers manage every server via SSH.
· AI Security Specialists use SSH to interact with model training infrastructure.

Mastering SSH is non-negotiable. This challenge was the first step.

---

References

· SSH man page
· CyLab Security Academy
· CyLab Primer — The Shell

---

Written by Ikehi Isaac — GitHub

