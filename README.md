# BTLO SOC Alpha 2 - Threat Hunting Report

This repository contains my **SOC Alpha 2** challenge investigation from **Blue Team Labs Online (BTLO)**. The objective was to analyze event logs, filter relevant security events, and identify suspicious activity using various threat-hunting techniques.

---

## 🔍 Overview

- **Platform**: Blue Team Labs Online (BTLO)
- **Challenge**: SOC Alpha 2  
- **Focus Areas**:
  - Analyzing event logs
  - Filtering for suspicious IPs and login attempts
  - Investigating PowerShell activity
  - Identifying malicious queries and potential exploitation tools

---

## 🏹 Threat Hunting Steps

### 🔹 **Hunt 1: Suspicious Logon Activity**
1. **Filtered event logs** for a specific date to narrow down suspicious activities.
2. **Identified highest frequency IP addresses** associated with events.
3. **Checked event details**, revealing **logon type 3**, indicating a network-based logon.
4. **Correlated event IDs** to track successful logins from suspicious IPs.

![Screenshot 2025-02-10 124740](https://github.com/user-attachments/assets/35a4d3ca-2b8c-43e8-a045-059b6a59124b)

![Screenshot 2025-02-10 131515](https://github.com/user-attachments/assets/475a4621-af55-4309-ae79-ca4e781084ff)

![Screenshot 2025-02-10 131611](https://github.com/user-attachments/assets/ad9f4e4b-cfa9-4af4-ae56-a3ca6a1555c8)

![Screenshot 2025-02-10 131700](https://github.com/user-attachments/assets/fa7b2fe8-01b0-4942-b9b3-ae4b7b1f20fe)

![Screenshot 2025-02-10 132231](https://github.com/user-attachments/assets/4ca8c589-f7bc-4dbb-b91f-89f897bcf496)


### 🔹 **Hunt 2: PowerShell Execution**
1. **Filtered logs for `powershell.exe` executions**.
2. **Investigated exclusion paths** to determine if execution bypassed Defender.
3. **Googled known techniques** to check if bypass methods were used.

![Screenshot 2025-02-10 133642](https://github.com/user-attachments/assets/d8ac7d1e-6adb-4710-b431-9e53afbb0761)

### 🔹 **Hunt 3: Malicious Queries & Execution**
1. **Filtered by event ID, query name, and execution process IDs**.
2. **Investigated URLs** associated with suspicious DNS queries.
3. **Mapped execution process ID to potential attacker persistence mechanisms**.

![Screenshot 2025-02-10 134445](https://github.com/user-attachments/assets/e8a0c1fb-6671-4c74-b0bc-7b4e9fb8357b)

![Screenshot 2025-02-10 135125](https://github.com/user-attachments/assets/046868f9-c690-47ec-bdb0-056bca75919b)

![Screenshot 2025-02-10 135641](https://github.com/user-attachments/assets/fed29297-4431-4ac1-8f18-0d855b550f42)


### 🔹 **Hunt 4: Advanced Tooling (Mimikatz)**
1. **Checked for all relevant event IDs**, but initially found no matches.
2. **Searched specifically for Mimikatz**, a well-known credential dumping tool.
3. **Analyzed execution artifacts**, confirming potential credential compromise.

![Screenshot 2025-02-10 140705](https://github.com/user-attachments/assets/043e8fde-fa5d-4cbc-ad3e-083606478052)

![Screenshot 2025-02-10 140746](https://github.com/user-attachments/assets/e52756ed-1cbd-48dd-9ab8-4cbb99dc8d6f)

---


### !!! Answers !!!

![Screenshot 2025-02-10 141234](https://github.com/user-attachments/assets/8221c9e9-e099-4e7a-b5ac-e49fd88e9994)


---

## 📌 Notes

- This is a **learning-based project** for improving blue team skills.
- The logs used are from a **training lab (BTLO)**, not real-world incidents.
- Feel free to contribute by adding detection rules, scripts, or alternative analysis methods.

---

### ⭐ Thanks for checking out this repo! If you have suggestions or improvements, feel free to contribute.
