# 🚩 Shark on Wire 1

### 📑 Challenge Overview

* **Author:** Danny
* **Category:** Forensics
* **Difficulty:** Medium
* **Platform:** picoCTF Gym

---

### 🔍 Discovery & Analysis

The challenge provided a `.pcap` file. My initial analysis involved a deep dive into the entire capture to identify readable data.

**My Investigative Process:**

* **The Dead End:** I started by looking through the **whole pcap file**. I quickly realized that the **TCP streams were encrypted**, making them impossible to read directly without a private key.
* **Strategic Pivot:** After hitting the wall with TCP, I shifted my focus to the **UDP streams**.
* **Brute-Force Analysis:** I began "brute-forcing" the analysis by manually looking through the UDP streams one by one.
* **The Hypothesis:** I operated on the theory that a **lower packet number** might mean a higher chance of finding the exact flag text in its simplest form.
* **The Lead:** During this manual search, I encountered significant amounts of "junk data" designed to mislead the investigator.

---

### 🛠️ Methodology

1. **Traffic Triage:** Opened the file in **Wireshark** and bypassed the encrypted TCP traffic.
2. **Manual Stream Hunting:** * Right-clicked a UDP packet and selected **Follow > UDP Stream**.
* Manually cycled through the streams (Stream 0, 1, 2...).


3. **Discovery:** Found that Stream 6 contained the plaintext flag, confirming that the "junk" in previous streams was merely noise.
4. **Process Optimization:** After finding the flag, I discovered a **much easier way** to perform this task. Instead of manual brute-forcing, using **Ctrl+F** to search for the "pico" string in packet bytes or checking the **Protocol Hierarchy** would have yielded the result in seconds.

---

### 🖼️ Technical Evidence

| Step | Visual Reference |
| --- | --- |
| **Encrypted/Junk Analysis** |![](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/shark%20on%20wire%201/junk%20data.png)|
| **Following the Stream** |![](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/shark%20on%20wire%201/this%20stream.png)|
| **Flag Recovery** |![](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/shark%20on%20wire%201/flagggggg.png)|

---

### 🧰 Tech Stack

* **Operating System:** Kali Linux VM (Oracle VirtualBox)
* **Forensics Tools:** **Wireshark**
* **Technique:** Network Traffic Analysis (NTA) / Stream Following / String Searching

---

### 🏁 Flag

`picoCTF {StaT31355_636f6e6e}`

---

### 💡 Key Lessons (The "Efficiency" Pivot)

* **Encryption Awareness:** Identifying early on that TCP streams are encrypted saves time that would otherwise be wasted on unreadable data.
* **Tool Mastery over Brute-Force:** While manual searching (brute-forcing) works for smaller files, mastering Wireshark's search functions (**Ctrl+F**) and **Protocol Hierarchy** is essential for professional-grade forensics.
* **Identifying Noise:** CTF creators often use "junk data" in early streams to test an analyst's persistence.
