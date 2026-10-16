# Super SSH — CyLab Security Academy (picoCTF 2024)

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
