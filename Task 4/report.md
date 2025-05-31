# Task 4 Report: Setup and Use a Firewall on Windows/Linux

**Date:** May 31, 2025  
**Objective:** Configure and test basic firewall rules to allow or block traffic.  
**Tools Used:** UFW (Uncomplicated Firewall) on Linux.  
**Deliverable:** Screenshots showing firewall rules applied.

---

## Task Overview

The goal of this task was to configure and test firewall rules on Linux systems, focusing on blocking and allowing specific network traffic. The task involved working with UFW on Linux, following a structured set of steps to manage firewall rules, test them, and document the process. The outcome aimed to demonstrate basic firewall management skills and an understanding of network traffic filtering.

---

## Step-by-Step Execution

### 1. Open Firewall Configuration Tool
- **UFW (Linux):** On a Linux system (Ubuntu 22.04), I opened a terminal and checked the status of UFW using the command:
  ```
  sudo ufw status
  ```
  UFW was initially disabled, so I enabled it with:
  ```
  sudo ufw enable
  ```

---

### 2. List Current Firewall Rules
- **UFW (Linux):** I ran the following command to list the current UFW rules:
  ```
  sudo ufw status
  ```
  The output showed no specific rules for ports 23 or 22 initially.

---

### 3. Add a Rule to Block Inbound Traffic on a Specific Port (Port 23 for Telnet)
- **UFW (Linux):** I added a rule to block inbound traffic on port 23 with the command:
  ```
  sudo ufw deny 23/tcp
  ```
  I verified the rule with `sudo ufw status`, which showed:
  ```
  To                         Action      From
  --                         ------      ----
  23/tcp                     DENY        Anywhere
  23/tcp (v6)                DENY        Anywhere (v6)
  ```

---

### 4. Test the Rule by Attempting to Connect to That Port Locally or Remotely
- **UFW (Linux):** On the Linux system, I used another machine to attempt a Telnet connection to port 23:
  ```
  telnet <linux-machine-ip> 23
  ```
  The connection was refused, confirming the UFW rule successfully blocked the traffic.

---

### 5. Add a Rule to Allow SSH (Port 22) if on Linux
- **UFW (Linux):** I added a rule to allow inbound traffic on port 22 for SSH:
  ```
  sudo ufw allow 22/tcp
  ```
  I verified the rule with `sudo ufw status`, which showed:
  ```
  To                         Action      From
  --                         ------      ----
  23/tcp                     DENY        Anywhere
  22/tcp                     ALLOW       Anywhere
  23/tcp (v6)                DENY        Anywhere (v6)
  22/tcp (v6)                ALLOW       Anywhere (v6)
  ```

---

### 6. Remove the Test Block Rule to Restore Original State
- **UFW (Linux):** I removed the rule blocking port 23 with:
  ```
  sudo ufw delete deny 23/tcp
  ```
  I confirmed the removal with `sudo ufw status`, which now only showed the SSH rule.

---

### 7. Document Commands or GUI Steps Used
- **UFW (Commands):**
  ```
  sudo ufw enable
  sudo ufw status
  sudo ufw deny 23/tcp
  sudo ufw allow 22/tcp
  sudo ufw delete deny 23/tcp
  ```

---

### 8. Summarize How Firewall Filters Traffic
Firewalls filter traffic by evaluating packets against predefined rules. In this task:
- **UFW (Linux):** UFW uses iptables under the hood to filter traffic. The `deny 23/tcp` rule dropped all inbound TCP packets on port 23, while `allow 22/tcp` permitted SSH traffic. UFW simplifies rule management by providing a user-friendly interface for iptables.

---

## Outcome
This task successfully demonstrated the ability to configure and test firewall rules on Linux systems. I gained hands-on experience with  UFW, learning how to block and allow specific traffic, test rules, and restore the original state. The process enhanced my understanding of network traffic filtering and the role of firewalls in securing systems.

---

## Answers to Interview Questions

1. **What is a Firewall?**  
   A firewall is a network security device or software that monitors and controls incoming and outgoing network traffic based on predefined rules. It acts as a barrier between a trusted internal network and untrusted external networks, such as the internet.

2. **Difference Between Stateful and Stateless Firewall?**  
   - **Stateless Firewall:** Examines packets independently without tracking the state of connections (e.g., whether a packet is part of an established session). It filters based on static rules like IP addresses or ports.  
   - **Stateful Firewall:** Tracks the state of active connections (e.g., TCP sessions) and makes decisions based on the context of the traffic, such as allowing return traffic for an established connection.

3. **What Are the Differences Between Inbound and Outbound Rules?**  
   - **Inbound Rules:** Control traffic entering the system (e.g., blocking Telnet requests to port 23).  
   - **Outbound Rules:** Control traffic leaving the system (e.g., restricting a system from initiating connections to certain external ports).

4. **How Does UFW Simplify Firewall Management?**  
   UFW simplifies firewall management by providing a user-friendly interface to manage iptables rules. It uses straightforward commands like `ufw allow` and `ufw deny` to create rules, abstracts complex iptables syntax, and supports default policies for easier configuration.

5. **Why Block Port 23 (Telnet)?**  
   Port 23 is used by Telnet, a protocol that transmits data in plaintext, making it vulnerable to interception and attacks. Blocking it prevents unauthorized access and reduces the risk of exploitation, especially since Telnet is rarely used in modern secure environments (SSH is preferred).

6. **What Are Common Firewall Mistakes?**  
   - Allowing unnecessary ports or services (e.g., leaving port 23 open).  
   - Misconfiguring rules, such as blocking legitimate traffic or allowing too much access.  
   - Not logging or monitoring traffic, making it hard to detect issues.  
   - Forgetting to update rules after system changes.

7. **How Does a Firewall Improve Network Security?**  
   A firewall improves network security by filtering traffic, blocking unauthorized access, and preventing malicious connections. It enforces security policies, protects against attacks like DDoS or port scanning, and isolates internal networks from external threats.

8. **What is NAT in Firewalls?**  
   NAT (Network Address Translation) in firewalls modifies the source or destination IP addresses of packets as they pass through. It’s often used to map private IP addresses to a public IP (e.g., in a router), enabling multiple devices to share a single public IP while hiding internal network structures from external networks.

---

## Conclusion
I successfully completed Task 4 by configuring and testing firewall rules on Linux systems. The process involved blocking Telnet traffic on port 23, allowing SSH on port 22 (on Linux), and restoring the original state, all while documenting the steps and outcomes. This task provided valuable insights into firewall management and network security practices, preparing me for real-world scenarios where traffic filtering is critical.

