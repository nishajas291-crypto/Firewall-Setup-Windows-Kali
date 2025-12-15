
 Firewall Setup and Configuration (Windows & Kali Linux)

 Overview

This repository contains the implementation and documentation of Task 4: Firewall Setup and Configuration, completed as part of a Cyber Security internship. The task was performed on **both Windows and Kali Linux** to demonstrate practical understanding of firewall concepts across different operating systems.

Firewalls are a critical security control used to monitor and filter incoming and outgoing network traffic based on predefined rules.


Objective

* To configure and manage firewall rules on Windows and Linux systems
* To block insecure network services using port-based rules
* To test and verify firewall behavior after rule implementation
* To understand how firewalls improve system and network security

---

Tools and Environment

Windows

* Operating System: Microsoft Windows
* Firewall Tool: Windows Defender Firewall with Advanced Security
* Testing Tool: Command Prompt (CMD)

 Kali Linux

* Operating System: Kali Linux
* Firewall Tool: UFW (Uncomplicated Firewall)
* Testing Tool: Terminal

---

Key Concepts

* Host-based firewalls
* Inbound and outbound rules
* Network ports and protocols
* Traffic filtering
* Security risks of Telnet (port 23)

---

 Task Description

As part of this task,Telnet traffic on port 23 was blocked on both Windows and Kali Linux systems. Telnet is an insecure protocol that transmits data in plain text. Blocking this port helps reduce security risks. Firewall rules were tested to ensure that traffic to the blocked port was denied successfully.

---

Implementation – Windows Firewall

Step 1: Access Firewall Settings

* Open Windows Defender Firewall from the Start menu
* Click Advanced Settings to open firewall rule management

 Step 2: Review Existing Inbound Rules

* Navigate to  Inbound Rules
* Review current firewall rules applied to the system

 Step 3: Block Telnet (Port 23)

* Click New Rule→ Select *Port*
* Choose TCP protocol
* Specify Port 23
* Select Block the connection
* Apply the rule to all profiles (Domain, Private, Public)
* Name the rule as Block Telnet Port 23
*  Step 4: Testing on Windows

* Enable Telnet Client via Windows Features
* Open Command Prompt and run:

  ```
  telnet localhost 23
  ```
* The connection failed, confirming the firewall rule was effective
 Step 5: Restore Configuration

* The test rule was removed after verification to restore the system state

---
 Implementation – Kali Linux (UFW)

 Step 1: Check Firewall Status

```bash
sudo ufw status
```

 Used to verify whether the firewall is active and view existing rules
 Step 2: Enable UFW

```bash
sudo ufw enable
```

 Step 3: Block Telnet (Port 23)

```bash
sudo ufw deny 23
```

 Step 4: Allow SSH (Recommended)

```bash
sudo ufw allow 22
```

 Step 5: Verify Rules

```bash
sudo ufw status numbered
```

 Step 6: Testing on Kali Linux

```bash
telnet localhost 23
```

Connection failure confirmed that port 23 was successfully blocked
Step 7: Remove Test Rule

```bash
sudo ufw delete deny 23
```

 Testing and Verification

On both Windows and Kali Linux systems, connection attempts to port 23  failed after applying firewall rules. This confirms that the firewall configurations successfully blocked Telnet traffic.

---


 Why Telnet (Port 23) Was Blocked

* Telnet sends data and credentials in plain text
* It is vulnerable to interception and attacks
* Blocking Telnet reduces attack surface
* Secure alternatives such as SSH should be used instead

---
 Outcome

* Successfully configured firewall rules on Windows and Kali Linux
* Verified firewall behavior through testing
* Gained hands-on experience with cross-platform firewall management

---

 Conclusion

This task demonstrated practical firewall configuration on both Windows and Linux platforms. By blocking Telnet traffic on port 23 and validating the results through testing, the importance of firewalls in securing systems and filtering network traffic was clearly understood.

 Summary

“I configured firewall rules on both Windows Defender Firewall and UFW in Kali Linux to block Telnet traffic on port 23. I verified the configuration by testing local connections, which failed as expected, demonstrating effective traffic filtering and firewall management.”
