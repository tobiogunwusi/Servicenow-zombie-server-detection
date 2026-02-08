# 🧟‍♂️ Automated Zombie Server Detection for ServiceNow

**Turn "Legacy Debt" into "Automated Savings."**

This ServiceNow utility detects "Zombie Servers"—infrastructure that is powered on and reachable (responding to Discovery) but has **zero active user connections**.

---

## 🧠 Problem Statement

Traditional ServiceNow Discovery marks servers as "Alive" if they respond to basic probes—even if they have **zero active users**. In a hybrid infrastructure, these idle servers are "Silent Killers" of the IT budget. They consume:

* **Compute Resources** (CPU/RAM)
* **Software Licenses** (Windows Server, SQL, etc.)
* **Operational Overhead** (Patching, Backup, Monitoring)

These are called **"Zombie Servers"** — infrastructure that is technically *up* but providing *zero business value*.

**The Solution:** 🚀
This project implements a **Custom Governance Workflow** to:
1.  **Interrogate** the OS for active TCP user sessions (using PowerShell).
2.  **Enrich** the CMDB with "Real-Time Utilization" metrics.
3.  **Automate** the classification of "Zombie Candidates."
4.  **Visualize** the financial impact ($) of idle assets.

---

## 🛠️ Architecture Overview

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Discovery Pattern** | PowerShell / WMI | Injects custom command to count `ESTABLISHED` TCP connections. |
| **CMDB Extension** | Dictionary Override | Extends `cmdb_ci_win_server` to store utilization metrics. |
| **Flow Designer** | Flow Logic | Evaluates data post-discovery and flags "Zombie Candidates". |
| **Analytics** | Reporting Engine | Calculates potential monthly savings based on decommission targets. |

---

## 📌 CMDB Schema Extensions

Added to the **Windows Server** table (`cmdb_ci_win_server`):

| Field Name | Type | Purpose |
| :--- | :--- | :--- |
| `u_active_connections` | Integer | Stores the count of active TCP sessions found during Discovery. |
| `u_is_zombie_candidate` | Boolean | **True** if connections < Threshold. Triggers review workflow. |
| `u_est_monthly_cost` | Currency | Estimated operational cost (Default: $200). Used for ROI calculation. |

---

## 🧪 Discovery Pattern Extension

The solution extends the standard **Windows OS - Servers** pattern.
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
This project bridges that gap by introducing OS-level session analysis to identify "Zombie Servers"—infrastructure that is technically "up" but providing zero business value— directly eliminating unnecessary operational costs.
