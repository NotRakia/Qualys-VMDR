## Lecture
## Configuring a Scan Job

![image](https://github.com/user-attachments/assets/36ca3b46-4a07-48c5-b624-06efc3272ffc)

### Required Scan Components
- **Scanner appliance**: At least one scanner appliance is required to launch a vulnerability assessment scan.
- **Host assets / scan targets**: When selecting a scanner appliance, consider the host assets the scan will target.
- **Option Profile**: Every vulnerability assessment scan must select an Option Profile containing scan preferences and scanning options.
- **Authentication record**: Required only if the selected Option Profile has authentication enabled.

### Scan Target Options
- **Netblocks / IP ranges / single IP address** within the Qualys subscription.
- Host IPs must first be added to the subscription before they can be scanned.
- **Asset Groups**: Any host asset in the subscription can be added to an Asset Group for scan targeting.
- **Asset Tags**: Provide a dynamic and automated solution for managing host assets in the subscription.

### Scan Consistency
- To keep scan data consistent over time, restrict **Scanner roles** from creating their own Option Profiles.
- Changes to Option Profiles can affect the consistency of data used in reports.
- The **Manager user** can create Option Profiles for primary scans and make them **globally available**.
- Scanner roles can then use these global profiles.
- Use case: standardize scanning from the Manager and maintain good subscription hygiene.

---

![image](https://github.com/user-attachments/assets/0e5e6546-77f4-4094-a21c-24ad1e5b2ff1)

### What Host Authentication Does
- **Trusted scanning** allows the service to log in to each target system during scanning.
- Enables in-depth security assessment and better visibility into each system’s security posture.
- Produces the most accurate results with fewer false positives.

### Benefits of Authentication
- Accurate operating system detection.
- Ensures enumeration of software applications on the host system.
- More vulnerabilities detected and maximized KnowledgeBase coverage.
- More **Confirmed** and fewer **Potential** vulnerabilities.
- Response time savings: manually investigating a Potential vulnerability takes longer than a Confirmed one.

### Authentication Vaults
- Supports integration with multiple third-party password vaults.
- Configure at: **Scans > Authentication > Vaults**.
- Then choose **Authentication Vault** in the authentication record.
- At scan time, the service authenticates to hosts using credentials retrieved from the vault.


![image](https://github.com/user-attachments/assets/11fd31c5-210e-43ee-88b9-ceb9d7d3ecdb)

Configuring Other Scan Settings

The Additional section of the Option Profile is where you configure the probing to determine alive/dead status. If the scanner appliance resides on the same subnet as the target hosts, the ARP cache can also be used as a discovery resource.

Qualys recommends default settings here and using the Additional checkbox to add TCP ports unique to your environment. The use case would be if the 13 Standard TCP ports are being blocked by a security layer sitting between the scanner and the target host. You would add the TCP port that the host can be contacted on. That way, the scanner would get a reply on that port, and the host discovery module would mark the target as alive.

The Blocked Resources section will ignore IPs or ports. An example would be an Intrusion Detection System residing on the same subnet as the scanner; it may block the scanner from the network. You can specify the IP of the IDS, and the scan will ignore that IP even though the entire subnet is targeted. Additionally, you can identify specific ports to ignore. It is possible to select Full port detection and ignore a custom port list to reduce from all 65535 TCP and 65535 UDP ports. You could also use this to ignore ports that are causing scan delays.


![image](https://github.com/user-attachments/assets/94243b12-ae36-4f73-b637-8b4cf3fc4833)

Configuring an Option Profile - Ports

In this course we focus on the basic configuration settings in an option profile, such as the TCP and UDP port settings, preset scan performance options, vulnerability detection options, and the different options for performing a scan in authenticated mode.

Full scans require many connections to be made. There are 65535 ports for TCP and another 65535 for UDP also. Many of those ports will not be open, and the scanner cannot just move on. It must wait for a timeout which can take several minutes per port.

The Standard Scan setting is the best balance of coverage to scan performance as determined by Qualys research. You can use the Additional ports field to add more ports to the Standard setting based on your unique environment.

Light Scan setting and identifying all specific ports for your environment is a way to fine-tune the best scan performance.

Network filtering devices and host-based firewalls should be configured to allow ports to be scanned internally.

A formal 3-way handshake for TCP is not performed by default. This checkbox to Perform a 3-way Handshake can be used for troubleshooting. It is not a long-term setting that should be used because you will lose TCP-based OS detection. The use case for this setting is to troubleshoot an environment where you are scanning through an IDS. IDS can typically block RST packets that immediately follow a SYN packet.

Once the open TCP and UDP ports have been determined, the scanner will interact with the port to determine the protocol service.

The list of services the scanning engine can identify can be found by navigating to Help – About.

Each service will have a name, port type, and complete description.

![image](https://github.com/user-attachments/assets/689a4184-c405-4396-bb5e-4691a46723ef)

Recommendations for On-Premises Scans

Use Case: This is an authenticated scan of your company’s internal infrastructure. It is to identify vulnerabilities as a rogue team member or vendor would see. Also, it is for verifying patching has happened.

Option Profile Settings

Standard scan setting for TCP and UDP

Add additional ports specific to your environment

Complete Vulnerability Detection

Authentication

Load Balancer Detection

Additional Certificate Detection

Dissolvable Agent

Enable parallel scaling

Custom Overall Performance setting (50 internal scanners)

*Add a Custom HTTP Header to identify the Qualys scanner in your log files


## Video Lecture:

Here are accurate, structured notes based on the provided video transcript for configuring a scheduled vulnerability scan in Qualys.

### **Tutorial Overview**
**Objective:** Learn how to configure a scheduled, authenticated vulnerability scan, including setting up an Option Profile, creating Authentication Records, and scheduling the scan.

---

### **Part 1: Core Concepts & Best Practices**

**Basic Scan Components:**
*   **Scanner Appliance:** Required to launch the scan.
*   **Scan Targets:** Netblocks, specific IP ranges, single IPs, or **Asset Tags** (dynamic/automated management).
*   **Option Profile:** Contains scan preferences/options.
*   **Authentication Record:** Required only if the Option Profile has authentication enabled.

**Scanner vs. Cloud Agent:**
*   **Scanner Appliance:** Has a *remote* perspective of hosts. Required for "Remote Only" QIDs in the KnowledgeBase (requires a network connection back to the host).
*   **Cloud Agent:** Has a *local* perspective. Cannot detect "Remote Only" QIDs. A supplementary scan is required for Cloud Agent hosts using a dynamic search list filtered for Remote Only QIDs.

**Option Profiles & Consistency:**
*   Changes to Option Profiles affect report data consistency.
*   **Best Practice:** The Manager user should create globally available Option Profiles. Scanner roles then use these to standardize scanning and maintain data hygiene.

**Host Authentication (Trusted Scanning):**
*   Allows the scanner to log into target hosts.
*   **Benefits:** Accurate OS detection, accurate software enumeration, more vulnerabilities detected (maximizes KnowledgeBase coverage), more *Confirmed* and fewer *Potential* vulnerabilities, fewer false positives, and time savings.

**Scan Configuration Recommendations:**
*   **Discovery:** Use default settings; add custom TCP ports unique to your environment. ARP cache can be used if the scanner is on the same subnet.
*   **Ports:** Standard scan is the best balance of coverage vs. performance.
*   **Scanning Strategy:** Scan as much as possible, as often as possible. (Note: Cloud Agents scan every 4 hours by default).
*   **Unified Vulnerability View:** Enable this to ensure no duplicate asset records.
*   **Proximity:** Keep scanner appliances close to targets; avoid traversing firewalls or load balancers.

---

### **Part 2: Step-by-Step Demonstration**

#### **Step 1: Create an Option Profile**
1.  Go to the **Option Profiles** tab and click **New** > **Option Profile**.
2.  **Basic Details:**
    *   Title: `Authenticated scan internal assets`
    *   Check **Set this as the default profile** (makes it available to all scanner-level users).
3.  **Scan Tab Settings:**
    *   *Port Selection:* Standard scan (add custom ports if necessary).
    *   *Close vulnerabilities when host not found alive:* Set to `12` (if not found after 12 scans, close vulns to keep dashboard clean).
    *   *Search for load balancers during scan:* Check this (improves accuracy).
    *   *Additional Certificate Detection:* Check to find/test certs in additional locations.
    *   *Windows dissolvable agent* (default) & *Windows share enumeration*: Leave/enable.
4.  Click **Save**.

#### **Step 2: Configure Authentication Records**
*Note: Authentication must be enabled in the Option Profile, but actual credentials are configured here.*

**Record 1: Windows / Active Directory**
1.  Go to the **Authentication** tab and click **New**.
2.  Title: `AR training domain`.
3.  *Login Credentials:* Domain Type = Active Directory. Domain Name = `Qualys training local`. Enter Username and Password.
4.  Check **Enable agentless tracking** (crucial for merging scan and Cloud Agent records to prevent duplication).
5.  Click **Save**.

**Record 2: Unix / Linux / Mac**
1.  Click **New** > **Unix**.
2.  Title: `AR Linux hosts`.
3.  *Login Credentials:* Enter Username and Password.
4.  *Root Delegation Tab:* Click **Add root delegation** > choose `sudo` > enter password. (Allows the user account to execute commands with root access).
5.  *Agentless Tracking Tab:* Check **Enable agentless tracking**.
6.  *Assets Tab:* Select **Asset Tags**. Add tags (e.g., `OS Linux server`, `OS Linux desktop`).
7.  Click **Create**.

#### **Step 3: Configure the Scheduled Scan**
1.  Go to the **Schedules** tab and click **New** > **Schedule Scan**.
2.  **Basic Details:**
    *   Title: `Authenticated scan internal assets`.
    *   Option Profile: The default profile created earlier is already selected.
    *   Scanner Appliance: Select your appliance (e.g., `scanner Appliance zero 1`).
3.  **Target Hosts Tab:**
    *   Select **Tags**.
    *   Check **Include Cloud Agent hosts** (temporarily add agent addresses).
    *   Click **Add Tag** and search for/select `NW internal lan`.
4.  **Scheduling Tab:**
    *   **Duration:** Check the box to limit scan time.
    *   **Pause:** Set to `08` hours.
    *   **Resume:** Set to `1 day` (scan will pause after 8 hours and resume 1 day after the original start time).
    *   **Recurrence (Occurs):** Select `Weekly` and `Friday`. Use the calendar icon to set the first date (e.g., Friday the 7th).
5.  Click **Save**.



## Creating a Scheduled Vulnerability Scan in VMDR — Accurate Notes

### **Lab Objective**
Create a **scheduled, authenticated vulnerability scan** for assets on the internal network using an internal scanner appliance.

The lab covers three main tasks:
1. Configure scan settings via an **Option Profile**
2. Configure authentication via **Authentication Records**
3. Configure a **Scheduled Scan Job**

---

## Part 1 — Create the Option Profile

1. Go to **Scans > Option Profiles**.
2. Click **New** > **Option Profile**.
3. Set **Title**: `Authenticated Scan - Internal Assets`.
4. Check **Set this as the default profile**.
   - This makes the profile automatically available to all users with scanner-level privileges or higher.
5. Open the **Scan** tab.
   - Leave **Port Selection** on default: **Standard Scan**.
   - You can add additional ports if assets listen on non-standard ports.
6. Under **Close Vulnerabilities on Dead Hosts**:
   - Check **Close vulnerabilities when host is not found alive**.
   - Set value to `12`.
   - Meaning: if a host is not found after 12 scans, its vulnerabilities are automatically closed.
7. Check **Search for load balancers during scan**.
   - Helps highlight load balancer presence in results, since load balancers can affect scan accuracy.
8. Scroll down and configure additional settings:
   - **OS authentication** is enabled by default.
   - Check **Enable additional certificate detection**.
   - **Windows Dissolvable Agent** is enabled by default.
   - Check **Enable Windows Share Enumeration**.
9. Click **Save**.

---

## Part 2 — Configure Authentication Records

### **Windows Authentication Record**
1. Go to the **Authentication** tab.
2. Click **New** > **Windows**.
3. Set **Title**: `AR: Training Domain`.
4. Open **Login Credentials**.
5. Configure:
   - **Domain Type**: `Active Directory`
   - **Domain Name**: `qualystraining.local`
   - **User Name**: `qualys`
   - **Password**: `Training123!`
   - **Confirm Password**: `Training123!`
6. Check **Enable agentless tracking**.
   - Essential for merging vulnerability scan records with Cloud Agent scan records.
   - Prevents duplicate asset records.
7. Click **Save**.

### **Unix Authentication Record**
1. Click **New** > **Unix**.
2. Set **Title**: `AR: Linux Hosts`.
3. Open **Login Credentials**.
4. Configure:
   - **Username**: `qualys`
   - **Password**: `Training123!`
   - **Confirm Password**: `Training123!`
5. Open **Root Delegation**.
   - Click **Add Root Delegation**.
   - Select **Sudo**.
   - Enter password: `Training123!`
   - Click **Save**.
   - Root delegation allows the Unix user account to execute commands with root access on scanned hosts.
6. Open **Agentless Tracking**.
   - Check **Enable agentless tracking**.
7. Open **Assets**.
   - Select **Asset Tags**.
   - Click **Add Tag**.
   - Search for `Linux`.
   - Select:
     - `OS: Linux Server`
     - `OS: Linux Desktop`
8. Click **Create**.

---

## Part 3 — Configure the Scheduled Scan

1. Go to the **Schedules** tab.
2. Click **New** > **Schedule Scan**.
3. Set **Title**: `Authenticated Scan - Internal Assets`.
4. Confirm the **Option Profile** is already selected:
   - `Authenticated Scan - Internal Assets (default)`
5. Select **Scanner Appliance**:
   - `ScannerAppliance01`
6. Open the **Target Hosts** tab.
   - Select **Tags**.
   - Check **Temporarily add agent addresses** to include Cloud Agent hosts.
   - Click **Add Tag**.
   - Search for `NW`.
   - Select `NW: Internal LAN`.

### **Configure Scheduling**
1. Open the **Scheduling** tab.
2. Check **Duration**.
3. Set:
   - **Pause after**: `08` hours
   - **Resume**: `1 day`
   - This means the scan pauses after 8 hours if not finished and resumes automatically one day after the original start time, continuing where it left off.
4. Set **Occurs**:
   - Select **Weekly**
   - Select **Friday**
5. Use the calendar icon to select the start date:
   - Click **Friday 7th**
6. Click **Save**.

---

## Result
- The scheduled scan appears in the **Schedules** list.
- It shows:
  - Title: `Authenticated Scan - Internal Assets`
  - Targets: Asset Tags Included
  - Scanner: `ScannerAppliance01`
  - Next Launch date/time
- The lab is complete once the scheduled authenticated scan job is configured.

---

## Key Takeaways
- **Option Profiles** define scan settings and can be standardized by making them default/global.
- **Authentication Records** enable trusted scanning and should include **agentless tracking** to avoid duplicate assets.
- **Root Delegation** is required for Unix/Linux authenticated scans to run privileged checks.
- **Asset Tags** provide dynamic targeting for scheduled scans.
- **Scheduling options** allow long scans to pause and resume automatically.
