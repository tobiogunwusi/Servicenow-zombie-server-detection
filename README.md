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

# 🧟‍♂️ Automated Zombie Server Detection for ServiceNow

**Turn "Legacy Debt" into "Automated Savings."**

This ServiceNow utility detects "Zombie Servers"—infrastructure that is powered on and reachable (responding to Discovery) but has **zero active user connections**.

## 📸 Project Screenshots

### 1. The Value (ROI Dashboard)
<img src="Zombie%20CI%20Report.png" alt="Zombie CI Report" width="600">

### 2. The Result (Server Form)
<img src="CI%20Form.png" alt="CI Form" width="600">

### 3. The Logic (Flow Designer)
<img src="Zombie%20CI%20Flow.png" alt="Zombie CI Flow" width="600">

### 4. The Code (Pattern Designer)
<img src="Zombie%20CI%20Pattern2.png" alt="Zombie CI Pattern2" width="600">
<br>
<img src="Zombie%20CI%20Pattern1.png" alt="Zombie CI Pattern1" width="600">

## 🔗 Context
Built as a Proof of Concept inspired by the **Berlin ServiceNow Developer Meetup** discussions on Hybrid Infrastructure Governance.
## 🔗 Context
Built as a Proof of Concept inspired by the **Berlin ServiceNow Developer Meetup** discussions on Hybrid Infrastructure Governance.
