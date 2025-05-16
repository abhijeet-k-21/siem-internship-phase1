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

### 🔹 2. Log Collection via Event Viewer
Opened:
Event Viewer → Windows Logs → Security

Observed the following Event IDs:

   -  4624 – Successful logon
   -  4672 – Special privileges assigned to new logon


🖼️ Screenshots
Sysmon installed successfully.

Event Viewer displaying Event IDs 4624 and 4672.

Additional screenshots of system logs and configurations.

# 📁 Repository Structure

siem-internship-phase-1/

│

├── /logs/                # Exported logs (if any)

├── /screenshots/         # Screenshots of setup and events

├── writeups/

└── README.md             # Documentation

# 🧠 Learning Outcomes
Understood the purpose and setup of Sysmon.

Learned how to monitor important Windows Event IDs.

Got hands-on experience with log collection and documentation.

✅ Phase 1 Checklist
 Windows VM created

 Sysmon installed with proper config

 Log generation confirmed via Event Viewer

 Screenshots uploaded

 Repository structured and documented

