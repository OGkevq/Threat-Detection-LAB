# Threat Detection LAB

## Objective

The Threat Detection Lab project was a simulated scenario in which a penetration tester attempted to execute malware samples on a device. My job was to use PicoSecure Tools to detect the attacks. Each time I detected an attack, I would have to use a new method of detection for the next attack. This helped to build my defensive strategies as well as understand the Pyramid of Pain Framework.

### Skills Learned

- Proficiency in analyzing malware
- Ability to recognize attack patterns
- Create Rules to detect cyberattacks 
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- PicoSecure Malware Sandbox
- Firewall & Hash managers
- DNS Filter
- Sigma Rule Builder

## Steps
This lab was set up on a virtual machine through TryHackMe
1. Analyze the "sample1.exe" using the the Malware Sandbox Tool
2. Review the results from the analysis

  ![Threat Detection sc1 2](https://github.com/user-attachments/assets/e0573754-07f8-4874-bc2e-824b1affcb97)

  Ref 1: The image shows the results from the analysis
  
3. After seeing the results had some hashes, I decided to use the manage hash tool. I added the MD5 hash of the malware into the hash blocklist. That was solution #1. 
4. Using hashes is a good way to block specific malware, but malware is susceptible to change and therefore the hash may not be the same. In "sample2.exe" the malware was recompiled and with it came a new file hash. 
5. Scan "sample2.exe" using the Malware sandbox tool
6. After scanning the file, the results showed a suspicious connection to IP 154.34.10.133:444. I used this information to create a firewall rule in the firewall manager so that any data moving out of the private network to the malicious IP address was denied.

  ![Threat Detection sc2 1](https://github.com/user-attachments/assets/06dc85d3-2b3a-4b35-ae9a-c16ca3bc0359)

  Ref 2: The image above shows the new firewall rule being applied.
  
7. A motivated attacker can get around this rule by using a new public IP address. A new method is needed for the next sample. With "sample3.exe" the perntester has a new public IP address with plenty more backups just in case. 
8. Analyze the "sample3.exe" using the the Malware Sandbox Tool
9. The results from the analysis show new suspicious connections. This time instead of focusing on the IP addresses, I looked at the domains. It seemed the malware connected to the domain "emundyn.bresonicz.info" multiple times.
10. I created a DNS rule using the DNS Rule Manager to prevent access to the suspicious domain

  ![Threat Detection sc3 1](https://github.com/user-attachments/assets/ddf7e102-5b26-4e7a-9503-d94ae79b856b)

  Ref 3: Creation of the DNS rule to prevent connection to "emundyn.bresonicz.info" 
  
11. For the new malware "sample4.exe" blocking hashes, IPs, or domains won't help. I need to use a new method. With this in mind, I use the Malware Sandbox Tool to analyze "sample4.exe."
12. I noticed the malware causes the machine to turn off real-time monitoring. This seems like a command I can prevent.

  ![Threat Detection sc4 1](https://github.com/user-attachments/assets/d6742774-483a-4585-8ed5-9379233bb9ef)

  Ref 4: The image shows a portion of the results of the malware scan malware on "sample4.exe

13. 
14. I use this information along with the Sigma Rule Builder to create a t
15. tr
16. rtr
17. tr
18. t
19. grg

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
