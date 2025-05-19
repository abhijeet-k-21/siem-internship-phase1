# SIEM Internship – Phase 1: Sysmon Setup & Log Collection

## 📌 Phase Objective

The goal of this phase is to set up a basic cybersecurity lab environment and use Sysmon to generate and collect Windows security logs. This setup forms the foundation for future threat detection and alerting use cases.

---

## 🛠️ Tools Used

- **Windows Virtual Machine** (Target system)
- **Sysmon** – System Monitor by Sysinternals
- **Event Viewer** – For viewing logs
- `sysmonconfig-v2.xml` – Configuration file for Sysmon
- **GitHub** – For tracking progress and storing documentation/logs

---

## ⚙️ Steps Performed

### 🔹 1. Download & Install Sysmon

1. Downloaded the Sysmon ZIP package from the [official Microsoft Sysinternals site](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon).
2. Extracted the files and saved:
   - `Sysmon64.exe`
   - `sysmonconfig-v2.xml`
3. Opened **Command Prompt** as Administrator.
4. Ran the following command to install Sysmon with the config file:
   Sysmon64.exe -accepteula -i sysmonconfig-v2.xml
 5.Confirmed successful installation and verified the Sysmon service is running.

### 🔹 2. Log Collection via Event Viewer Opened:
      Event Viewer → Windows Logs → Security

      Observed the following Event IDs:

       ✅ Event ID 4624 – Successful Logon  
            - Shows successful logon attempts  
            - Screenshot saved as: `/screenshots/4624.png`  
            - Log saved in: `/logs/4624-log.evtx`

       ✅ Event ID 4672 – Special Privileges Assigned  
            - Shows accounts assigned admin privileges on logon  
            - Screenshot saved as: `/screenshots/4672.png`  
            - Log saved in: `/logs/4672-log.evtx`

       ✅ Event ID 4625 – Failed Logon  
            - Captures failed login attempts (brute force tracking)  
            - Screenshot saved as: `/screenshots/4625.png`  
            - Log saved in: `/logs/4625-log.evtx`

---

## 🔐 Use Cases Addressed

| Use Case                         | Description                                                 |
|----------------------------------|-------------------------------------------------------------|
| Brute Force Login Detection      | Multiple failed logins using Event ID 4625                 |
| Successful Login After Brute Force | Tracked using Event ID 4624 after many 4625 entries      |
| Failed Login Threshold Tracking  | Users with 05+ failed logins per day using Event ID 4625   |
| Basic Login Audit Trail          | Combination of 4624, 4625, and 4672                        |



### 🖼️ Screenshots
  -  Sysmon installed successfully.
  -  Event Viewer displaying Event IDs 4624,4625 and 4672.
  -  Additional screenshots of system logs and configurations.

### 📁 Repository Structure

siem-internship-phase-1/

│

├── /logs/                         # Exported logs

├── /screenshots/                  # Screenshots of setup and events

├── /sysmonconfig/                 #sysmonconfig-v2.xml

├── writeups/

└── README.md                      # Documentation
  
### 🧠 Learning Outcomes
-  Understood the purpose and setup of Sysmon.
-  Learned how to monitor important Windows Event IDs.
-  Got hands-on experience with log collection and documentation.

### ✅ Phase 1 Checklist

 -  Windows VM created
 -  Sysmon installed with proper config
 -  Log generation confirmed via Event Viewer
 -  Screenshots uploaded
 -  Repository structured and documented

