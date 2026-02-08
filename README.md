# 🧟‍♂️ Automated Zombie Server Detection for ServiceNow

**Turn "Legacy Debt" into "Automated Savings."**

This ServiceNow utility detects "Zombie Servers"—infrastructure that is powered on and reachable (responding to Discovery) but has **zero active user connections**.

## 🚀 Features
* **Custom Pattern Extension:** Uses `PowerShell` to query `Get-NetTCPConnection` directly on the host.
* **Flow Designer Logic:** Automatically flags servers as `Zombie Candidates` if connections drop below a defined threshold.
* **ROI Dashboard:** Calculates potential monthly savings based on decommission targets.

## 🛠️ Installation
1.  Download `zombie_server_detection_v1.xml`.
2.  In ServiceNow, navigate to **Retrieved Update Sets**.
3.  Import XML -> Preview -> Commit.
4.  Run Discovery on a Windows Server to see the `active_connections` field populate.

## 📸 Project Screenshots

### 1. The ROI Dashboard
**Value Delivered:** Identifying €200/month in potential savings.
![Zombie CI Report](img/Zombie_CI_Report.png)

### 2. The "Brain" (Flow Designer)
**Logic:** Automated flagging of servers with < 25 active connections.
![Flow Designer Logic](images/your_flow_filename.png)

### 3. The "Eyes" (Pattern Designer)
**Mechanism:** Custom PowerShell execution via MID Server.
![PowerShell Pattern](images/your_pattern_filename.png)

## 🔗 Context
Built as a Proof of Concept inspired by the **Berlin ServiceNow Developer Meetup** discussions on Hybrid Infrastructure Governance.
