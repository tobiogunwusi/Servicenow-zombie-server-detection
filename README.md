# 🧟‍♂️ Automated Zombie Server Detection for ServiceNow

**Turn "Legacy Debt" into "Automated Savings."**

This ServiceNow utility detects "Zombie Servers"—infrastructure that is powered on and reachable (responding to Discovery) but has **zero active user connections**.

## 🚀 Features
* **Custom Pattern Extension:** Uses `PowerShell` to query `Get-NetTCPConnection` directly on the host.
* **Flow Designer Logic:** Automatically flags servers as `Zombie Candidates` if connections drop below a defined threshold.
* **ROI Dashboard:** Calculates potential monthly savings based on decommission targets.

## 🛠️ Installation
1.  Download the XML file from this repository.
2.  In ServiceNow, navigate to **Retrieved Update Sets**.
3.  Import XML -> Preview -> Commit.
4.  Run Discovery on a Windows Server to see the `active_connections` field populate.

## 📸 Project Screenshots

### 1. The Value (ROI Dashboard)
**Identifying potential savings from idle assets.**
![Zombie CI Report](images/Zombie%20CI%20Report.png)

### 2. The Result (Server Form)
**Automatic flagging of "Zombie Candidates" based on live data.**
![CI Form](images/CI%20Form.png)

### 3. The Logic (Flow Designer)
**Automated decision engine (If Connections < Threshold -> Flag as Zombie).**
![Zombie CI Flow](images/Zombie%20CI%20Flow.png)

### 4. The Code (Pattern Designer)
**Custom PowerShell execution via MID Server.**
![Zombie CI Pattern](images/Zombie%20CI%20Pattern2.png)

![Zombie CI Pattern Detail](images/Zombie%20CI%20Pattern1.png)

## 🔗 Context
**The Challenge:** Standard ServiceNow Discovery identifies infrastructure *existence*, but often lacks the granularity to determine *business utility*.
**The Solution:** This project bridges that gap by introducing OS-level session analysis to identify "Zombie Servers"—infrastructure that is technically "up" but providing zero business value.
