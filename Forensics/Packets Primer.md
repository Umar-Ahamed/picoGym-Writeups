# 🚩 Packets Primer

### 📑 Challenge Overview
* **Author:** LT 'syreal' Jones
* **Category:** Forensics
* **Difficulty:** Medium
* **Platform:** picoCTF Gym

---

### 🔍 Discovery & Analysis
The goal was to analyze a network packet capture (`.pcap`) file to locate a flag hidden within the transmitted data.

**My Investigative Process:**
* **Initial Observation:** I downloaded the `network-dump.pcap` file to my **Kali VM**.
* **Tool Selection:** Since this is a network forensics task, I utilized **Wireshark** for deep packet inspection.
* **Reconnaissance:** I opened the capture and began scanning the packet list. I focused on the "Info" column to see if there were any suspicious plaintext transmissions.
* **The Lead:** I noticed a series of packets. By selecting a packet and looking at the **Packet Details** and **Hex Dump** panes, I saw a string that followed the `p i c o C T F { ... }` format, but with spaces between the characters.

---

### 🛠️ Methodology
1.  **File Acquisition:** Downloaded the packet capture and verified it was a valid pcap file.
2.  **Traffic Analysis:** * Opened the file in **Wireshark**.
    * Examined the ASCII/Hex output in the bottom pane.
3.  **Data Extraction:**
    * Identified the flag in a packet where the data was sent in plaintext.
    * The flag appeared as: `p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ b 9 d 5 4 b d 1 }`.
4.  **Verification:** Removed the spaces from the string to assemble the final flag for submission.

---

### 🖼️ Technical Evidence
| Step | Visual Reference |
| :--- | :--- |
| **Network Triage** | ![Wireshark Packet Analysis](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/Packets%20Primer/The%20Pcap.png) |
| **Data Identification** | ![Identifying the Flag](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/Packets%20Primer/Found%20the%20flag.png) |
| **Flag Recovery** | ![Final Flag Assembly](https://raw.githubusercontent.com/Umar-Ahamed/picoGym-Writeups/refs/heads/main/Images/Packets%20Primer/Ctf%20Flag.png) |

---

### 🧰 Tech Stack
* **Operating System:** Kali Linux VM (Oracle VirtualBox)
* **Forensics Tools:** **Wireshark** (Packet Dissector)
* **Technique:** Network Traffic Analysis (NTA) / PCAP Carving

---

### 🏁 Flag
`picoCTF{p4ck37_5h4rk_b9d54bd1}`

---

### 💡 Key Lessons
* **Plaintext Exposure:** This challenge demonstrates why encrypting traffic is vital. Any data sent over an unencrypted protocol (like standard HTTP or Telnet) can be intercepted and read easily using a sniffer.
* **Hex/ASCII Correlation:** In network forensics, the Hex dump pane is often your best friend for finding "human-readable" strings that the dissector might not automatically highlight as a "flag."
