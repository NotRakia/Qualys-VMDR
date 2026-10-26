# Performing Basic Cloud Agent Management Tasks (Qualys Enterprise TruRisk Platform)

## 1. Reviewing Agent Status — Agents Tab
**Location:** Agent Management → **Agents** tab

The Agents list displays key columns:

| Column | Purpose |
|---|---|
| **Agent Host** | Hostname + IP address |
| **OS / Version** | Operating system and Cloud Agent version |
| **Last Activity** | Status of last scans (Inventory, VM, PC) |
| **Last Checked In** | Most recent check-in with the platform |
| **Configuration** | Active configuration profile |
| **Agent Modules** | Enabled modules (e.g., VM, PC, FIM, SCA, INV) |
| **Tags** | Asset tags applied to each host |

*Lab environment shows 15 agents, e.g. WIN-2K19-TEMPL... using Training_Profile; others using Initial Profile.*

## 2. Reviewing Agent Configuration — Configuration Profiles Tab
**Location:** Agent Management → **Configuration Profiles**

- Two profiles shown: **Training_Profile** (Order 1, created by Sharda Singh, Jan 31, 2025) and **Initial Profile (Default)** (Order 2, System, Sep 21, 2023).
- Order matters — you can drag profiles to change the order in which they are applied.
- To modify: select profile → **Actions → Edit**.

### Key Edit Mode sections:
| Section | Key findings in lab |
|---|---|
| **General Info** | Profile name; "Prevent auto updating of the agent binaries" is **unchecked** — keeping binaries up to date is the recommended default |
| **Performance** | Customization ON, based on "High". **Agent Status Interval: 900 sec** (900–7200) — governs check-in frequency. Also: Delta Upload Interval (1 sec), Chunk size (4096 KB), Upgrade Reattempt Interval (32400 sec) |
| **VM Scan Interval** | **Data Collection Interval: 240 min** (240–43200) — time between last completed scan and start of next. Scan Delay: 0 min, Scan Randomize: 0 min |

*(Changes were cancelled — no saves made.)*

## 3. Starting an On-Demand Scan
**Steps:**
1. Agents tab → select checkbox for the target host (WIN-2K19-TEMPL...).
2. Click **Actions (1)** → **On Demand Scan**.
3. In the **Run Scan** dialog, choose **Scan Type**:
   - Inventory Scan, **Vulnerability Scan**, Policy/Compliance Scan, UDC Scan, SCA Scan, SWCA Scan
   - Available scans depend on which modules are activated on the agent host.
4. Optional: "Use CPU Throttle limits set in the respective Configuration Profile" (Windows default = 80; Linux = 0).
5. Click **Submit**.

**Behavior:** The scan is not immediate — the agent picks up the job on its **next check-in**. After completion, the **Last Activity** column updates.

## 4. Lab Outcomes — Skills Learned
- Review Agent status
- Review Agent configuration
- Start an On-Demand Scan
