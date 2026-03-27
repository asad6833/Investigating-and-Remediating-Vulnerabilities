# 🔐 Investigating and Remediating Vulnerabilities (Firefox - GSA Lab)

## 📌 Scenario
You are a security expert hired by **Structureality** to assess vulnerabilities on their mail server:

- Target: `mail.structureality.com (10.1.16.2)`
- Focus: **Mozilla Firefox vulnerabilities**
- Tool: **Greenbone Security Assistant (GSA)**

Your goal is to:
1. Perform a vulnerability scan
2. Analyze results
3. Remediate vulnerabilities
4. Verify remediation

---

## 🎯 Objectives

- Perform vulnerability scanning using GSA
- Analyze critical Firefox vulnerabilities
- Apply remediation on MS10 server
- Validate remediation with re-scan

---

## 🖥️ Lab Environment

| System | Role |
|------|------|
| Kali Linux | Scanning system |
| MS10 | Mail server |
| Network | 10.1.16.0/24 VLAN (VyOS) |

TASK 1:Starting GVM
<img width="684" height="500" alt="image" src="https://github.com/user-attachments/assets/3c6f5aa2-1c26-4274-adf7-d2efadd4f147" />
<img width="1317" height="810" alt="image" src="https://github.com/user-attachments/assets/62f4b004-8ca9-4ca4-8a32-1262d335e1e3" />
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/e23b5531-2ee8-4146-a48a-06b70b44ee49" />
---

# 🚀  GSA Login Interface 
![95962be9316535e543014da2360f5ef9a7c75b98](https://github.com/user-attachments/assets/280b1ef2-945c-4939-a233-18e4ab7b275b)
<img width="827" height="693" alt="image" src="https://github.com/user-attachments/assets/de1bf678-0064-4fd7-8b0a-583ae5a234af" />
<img width="480" height="693" alt="image" src="https://github.com/user-attachments/assets/fe78fa63-d7c7-4548-bdba-6beb74ab1cb6" />

Firefox Scan Configuration (GSA) 
<img width="1268" height="1428" alt="image" src="https://github.com/user-attachments/assets/0fd77852-4ed9-4355-b7b2-3b2b70b82b0d" />
<img width="796" height="519" alt="image" src="https://github.com/user-attachments/assets/ca9bb348-2676-432c-9a67-e5b3057b80ab" />
<img width="1280" height="1134" alt="image" src="https://github.com/user-attachments/assets/d283b07b-c459-4f56-bb5f-be27ff81e3b0" />

Vulnerability Scan Running
<img width="1035" height="446" alt="cceec56837a11546f332550efb22174373c88354" src="https://github.com/user-attachments/assets/7270c554-f91c-4671-84af-724292862fcf" />
<img width="1343" height="420" alt="image" src="https://github.com/user-attachments/assets/fa66e363-593c-44c6-853b-28394151d23c" />
<img width="1400" height="724" alt="image" src="https://github.com/user-attachments/assets/84665e86-b48e-4de4-b177-8744e3e1b593" />











```bash
sudo gvm-start





Step 2: Access GSA
URL: https://127.0.0.1:9392
Login:
Username: admin
Password: Pa55w0rd!
🖼️ Screenshot: GSA Login

Step 3: Create Scan Configuration
Clone Empty Scan Config
Name: Firefox
Configure:
NVT Family: General
Filter: Mozilla Firefox Security Update
Severity: 10.0
Platform: Windows
NVT Family: Port Scanners
Enable:
Nmap (NASL wrapper)
Ping Host
🖼️ Screenshot: Scan Config Setup

Step 4: Export Scan Config
Export file
Rename to:
Firefox Config.xml
🖼️ Screenshot: Export Config

Step 5: Create Scan Task
Setting	Value
Name	Firefox Scan
Target	mail.structureality.com
Schedule	Once
Scan Config	Firefox
🖼️ Screenshot: Create Scan Task

Step 6: Run Scan
Start scan
Monitor progress
🖼️ Screenshot: Scan Running

Step 7: Export Scan Task
Export task
Rename to:
Firefox Scan.xml
🔍 TASK 2: Analyze & Remediate
Step 1: Review Scan Results
Click Last Report
Go to Results tab
Open each vulnerability
🖼️ Screenshot: Scan Results

Step 2: Identify Required Firefox Version
Scroll to Solution section
Note minimum required version

👉 Example:

Firefox version required: 115.x.x
Step 3: Login to MS10
Username: structureality\jaime
Password: Pa55w0rd!
Step 4: Install Updated Firefox

Path:

C:\LABFILES\Lab06
Run installer
Upgrade Firefox
Step 5: Verify Firefox Version
Open Firefox
Go to:
Menu → Help → About Firefox
🖼️ Screenshot: Firefox Version Check

🔁 TASK 3: Verify Remediation
Step 1: Re-run Scan
Use existing:
Firefox Scan task
Start scan again
Step 2: Confirm No Vulnerabilities
Open Results tab
Verify:
No critical findings
🖼️ Screenshot: Clean Scan Results

Step 3: Export Final Report
Download filtered report
Rename:
Remediated.xml
✅ Final Outcome

✔ Vulnerabilities identified
✔ Firefox upgraded
✔ All critical vulnerabilities remediated
✔ Clean scan confirmed

🔐 Skills Demonstrated
Vulnerability Scanning (GSA / OpenVAS)
Vulnerability Analysis
Patch Management
Remediation Validation
Security Operations Workflow
📚 CompTIA SecurityX Mapping
2.1 – Design and analyze resilient systems
Vulnerability management lifecycle implementation
🧠 Key Takeaways
Always validate vulnerabilities before remediation
Patch management is critical in enterprise security
Re-scanning is mandatory to confirm fixes
Automation tools like GSA improve detection accuracy
