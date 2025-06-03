# Security Measures and Learnings for Our T-Pot Project (by Rayane Ibn Atik, Hassan Basli, and Sadki Amine)

As part of our project on the T-Pot honeypot system, our group (Rayane Ibn Atik, Hassan Basli, and Sadki Amine) considered several security aspects related to setting up and running a system designed to attract and record malicious traffic. This document outlines our approach and key learnings.

## 1. Isolating the Honeypot Environment
We understood that a honeypot, by its nature, is exposed to attacks. To protect our other systems and the host institution's network, we deployed T-Pot on a dedicated virtual machine. This VM was isolated to the extent possible, ensuring that any potential compromise would be contained.
Network access to the T-Pot VM was restricted, only allowing necessary inbound traffic to the honeypot services and outbound traffic for system updates and our access for management.

## 2. Secure Access to Management Interfaces
T-Pot exposes management interfaces (e.g., SSH, web UI for Kibana) on non-standard ports (e.g., SSH on 64295, Web UI on 64297).
We ensured that strong, unique passwords were used for the OS user account (`<OS_USERNAME>`) and the web interface user (`<WEB_USER>`).
Access to these management ports was limited, ideally only from our specific IP addresses, if feasible within the project environment.

## 3. System Hardening and Updates
The underlying Linux operating system was kept up-to-date with the latest security patches.
T-Pot itself is designed to run services in Docker containers, which provides a layer of isolation between services.
We regularly checked for T-Pot updates as per the project's recommendations, although our project had a fixed duration.

## 4. Monitoring the Honeypot Itself
While the honeypot's purpose is to be attacked, we also monitored its system health (CPU, memory, disk usage) to ensure it wasn't being overwhelmed in a way that could affect its stability or data collection capabilities.

## 5. Data Handling
We were mindful that the data collected (e.g., attacker IPs, malware samples if any) should be handled responsibly, in line with academic integrity and ethical considerations discussed in our course.

## 6. Understanding Risks
We learned that no honeypot is perfectly secure. There's always a theoretical risk that an attacker could find a vulnerability in a honeypot service and use it to compromise the honeypot system itself (a 'breakout').
This reinforced the importance of the isolation measures mentioned earlier and not placing any sensitive or real data on the honeypot system.

## 7. Key Security Learnings by Our Group (Rayane, Hassan, Sadki)
- The importance of layered security (network isolation, strong credentials, containerization).
- Understanding that even systems designed to be 'attacked' require careful security management.
- The value of non-standard ports for management interfaces to reduce casual scanning.
- The ongoing need for vigilance and updates in any internet-exposed system.
