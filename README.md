# Brute-Force
Attacks against an SSH server using Hydra


## Objective
The objective of this assignment is to perform a brute-force password attack against an SSH server using Hydra while capturing and analyzing network traffic with Wireshark. The goal is to assess the effectiveness of brute-force attacks and discuss security implications.

### Introduction
Brute-force attacks are a method used by attackers to systematically guess login credentials by attempting numerous username and password combinations. Hydra is a powerful tool designed for this purpose, capable of executing high-speed login attempts against various network protocols. In this assignment, we simulate an attack on an SSH server and analyze network traffic using Wireshark.

### The tools I will use include:

- Kali Linux: The attacker's machine, equipped with penetration testing tools.

- Ubuntu: The target machine is running an SSH server.

- Hydra: A fast and flexible login cracker for brute-force attacks.

- Wireshark: A network protocol analyzer used to capture and inspect traffic.


## Steps and Results

*1: Setting Up the Environment*

To begin, Kali Linux and Ubuntu virtual machines were set up, ensuring that both were properly configured for network communication. The Ubuntu machine was configured to run an SSH server, while the Kali machine was prepared with Hydra installed as the attack tool. Wireshark was also launched on Kali to monitor and capture network traffic
<img width="1431" alt="Screen Shot 2023-09-21 at 8 56 58 PM" src="https://github.com/user-attachments/assets/dc498431-1ab1-4123-a1f3-7baa3bd35830" />


*2: Initiating the Brute-Force Attack*

Hydra was executed against the SSH server using a default wordlist. The tool systematically attempted multiple username and password combinations in rapid succession. As the attack progressed, unsuccessful login attempts were recorded, and eventually, Hydra successfully authenticated using a weak credential.
<img width="1251" alt="Screen Shot 2023-09-21 at 11 16 17 PM" src="https://github.com/user-attachments/assets/812bbde7-93c7-4acd-b710-67ba6dd552d5" />

*3: Capturing and Analyszing Network Traffic*

Wireshark was used to capture packets during the attack. The network traffic analysis revealed patterns of repeated failed authentication attempts. These appeared as SSH handshake packets showing rejected login requests. A successful login attempt was identified by a change in the packet flow, often marked by a red-colored alert in Wireshark, indicating an unexpected authentication success.

*4: Reviewing System Logs*

To further validate the attack, system logs on the Ubuntu machine (/var/log/auth.log) were examined. The logs displayed multiple failed SSH login attempts, followed by a successful authentication. This reinforced the findings from Wireshark and highlighted the impact of brute-force attacks on server logs.
<img width="912" alt="Screen Shot 2023-09-21 at 8 20 41 PM" src="https://github.com/user-attachments/assets/87311ee1-19c7-4b71-a862-1fbb9a4a610b" />

*5: Security Implications*

This exercise demonstrated the risks associated with weak passwords. Hydra efficiently exploited the vulnerability, emphasizing the necessity of robust security measures. To mitigate such attacks, organizations should implement multi-factor authentication (MFA), enforce strong password policies, and deploy intrusion detection systems (IDS) or fail2ban to limit repeated login attempts.
<img width="1046" alt="Screen Shot 2023-09-21 at 10 57 17 PM" src="https://github.com/user-attachments/assets/aeb0b247-06fc-40e7-a4a2-053bd358f006" />

### Conclusion
This assignment provided valuable insight into the mechanics of brute-force attacks and their impact on system security. By using Hydra, we were able to demonstrate how easily weak credentials can be exploited, reinforcing the importance of strong password policies and authentication mechanisms. The analysis using Wireshark allowed us to observe the network footprint of such attacks, highlighting how they can be detected and mitigated through security monitoring. Ultimately, this exercise emphasized the critical need for proactive security measures, such as implementing multi-factor authentication, using intrusion detection systems, and enforcing account lockout policies. Understanding these vulnerabilities and their mitigation strategies is essential for strengthening overall cybersecurity defenses.
