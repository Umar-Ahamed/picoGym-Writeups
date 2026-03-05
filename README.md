# 🚩 picoCTF Investigation Journal

### 🎯 Objective

To document the systematic identification and exploitation of vulnerabilities within the **picoCTF Gym**. This repository focuses on capturing the "Chain of Thought" during manual exploitation, protocol analysis, and forensic discovery.

### 📂 Investigation Logs

This directory serves as a technical record, organized by challenge category.

| Category | Solved | Latest Investigation |
| --- | --- | --- |
| **Web Exploitation** | 1 | [Crack the Gate 1](https://github.com/Umar-Ahamed/picoGym-Writeups/blob/main/Web%20Exploitation/Crack%20the%20Gate%201.md) |
| **Forensics** | 0 | Pending |
| **Cryptography** | 0 | Pending |

### 🛠️ Tech Stack & Lab Environment

Following the same modular setup as my SOC lab, these investigations are performed in a controlled environment:

* **Virtualization:** Oracle VirtualBox.
* **Operating System:** Kali Linux (Guest VM).
* **Web Analysis:** **Burp Suite Professional/Community** paired with **FoxyProxy** for efficient request interception.
* **Reconnaissance:** Firefox Developer Tools (Inspector/Debugger), `curl`, `strings`.

### 🚀 Methodology (SOP)

To maintain the high standards set in my **Baseline Analysis** logs, every CTF write-up follows a 4-step Standard Operating Procedure:

1. **Initial Observation:** Documenting the challenge prompt and initial "guess" or hypothesis.
2. **Investigation/Troubleshooting:** Recording every attempt, including failed paths (e.g., attempting Base64 before pivoting to ROT13).
3. **Exploitation:** Step-by-step instructions on the final successful attack vector.
4. **Evidence:** Visual confirmation via screenshots of source code, tool outputs, and captured flags.
