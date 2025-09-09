# Azure SIEM Lab (Microsoft Sentinel with Honeypot)

A hands-on project demonstrating **Security Information and Event Management (SIEM)** using **Microsoft Sentinel** in **Azure** with a deployed honeypot.

---

## 📌 Project Overview

This lab simulates a real-world security monitoring scenario by deploying a **Windows Honeypot Virtual Machine (VM)** in Azure, generating attack events, and collecting logs for analysis in **Microsoft Sentinel**.

Key objectives:

- Deploy and configure Azure resources for SIEM integration.
- Generate real attack logs from a publicly exposed honeypot.
- Ingest security events into Microsoft Sentinel via **Log Analytics Workspace**.
- Use **Kusto Query Language (KQL)** to detect malicious activities.
- Visualize attacker geolocation using Sentinel **Watchlists**.

---

## 🛠️ Lab Architecture
<img width="975" height="557" alt="image" src="https://github.com/user-attachments/assets/cec632e5-4f46-4574-aa44-4d36c22f4cae" />

The project workflow includes:

1. **Azure Resource Setup**  
   - Created a **Resource Group** and **Virtual Network** in Azure.
   - Deployed a **Windows VM as a Honeypot**, configured with **open inbound rules** in its **Network Security Group** to attract attackers.
   <img width="625" height="1350" alt="image" src="https://github.com/user-attachments/assets/f06588a9-a4dd-4713-8a38-0135ec6783e7" />


2. **Honeypot Configuration**  
   - Disabled **Windows Firewall** to ensure accessibility.
   - <img width="975" height="730" alt="image" src="https://github.com/user-attachments/assets/ae801bf3-82cd-4b9f-b743-293567612b4a" />

   - Verified external connectivity by allowing all network traffic.
<img width="975" height="405" alt="image" src="https://github.com/user-attachments/assets/22153a83-391a-482b-83e2-4e6fcc83ec44" />

3. **Event Generation**  
   - Simulated multiple **failed login attempts**.
   - Observed **Event ID 4625 (Failed Logon)** in Windows Event Viewer.
<img width="2730" height="125" alt="image" src="https://github.com/user-attachments/assets/3f17a06a-ad66-4eaf-958e-374fe555f958" />

4. **Log Ingestion to SIEM**  
   - Created **Log Analytics Workspace** to collect logs.
   - Deployed **Microsoft Sentinel** and linked it to the workspace.
   - Installed **Azure Monitoring Agent** on VM to forward security events.

5. **Log Analysis in Microsoft Sentinel**  
   - Built custom queries in **KQL**:
     <img width="975" height="977" alt="image" src="https://github.com/user-attachments/assets/709b15a7-4554-4008-acee-5e6349a3aea3" />


6. **Geolocation Analysis**  
   - Created a **Watchlist** for IP Geolocation enrichment.
   <img width="975" height="186" alt="image" src="https://github.com/user-attachments/assets/d25bbbd3-d4f3-40d6-b374-d48fb086be29" />

   - Generated an **Attack Map** to visualize attacker locations after 12 hours.
<img width="975" height="379" alt="image" src="https://github.com/user-attachments/assets/62365741-6330-415e-be96-6f0f4efb06a8" />

---

## ✅ What I Learned

- How to **deploy and configure Azure resources** for SIEM.
- Captured **real attacker traffic** through a honeypot setup.
- Forwarded logs securely to **Microsoft Sentinel** for analysis.
- Used **KQL** queries for filtering and detecting brute-force attacks.
- Enriched logs with geolocation data using **Watchlists**.
- Built **visual dashboards** (attack map) for actionable intelligence.

---


