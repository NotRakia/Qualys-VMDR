# Add Scannable Host Assets to VMDR

## Overview

Scannable Host Assets

Scannable Host assets are typically assets which are in a fixed location on the network rather than say belonging to the remote workers who may travel around to different locations.

When you add scannable host you have to choose the tracking methods. That is how will discovered vulnerabilities be associated with each asset.

Example. If the assets have a DHCP dynamic IP address then most likely we should select DNS tracked. If on the other hand the assets had static IP addresses then we would be selecting IP tracked addresses.

## Adding Assets to VMDR

### Asset Groups

- Allow you to manually group scannable host assets.
- Should be IP ranges not individual list of IPs.
- Usually used for scanning whereas IP tags can be used for scanning and reporting.
- Matching asset tags is created for each asset group.
- Will have an asset criticality score (ACS) that reflects the Group's Business Impact Score.

### Asset Groups

- Are one method of organizing scannable host assets.
- Is a list of scannable hosts.
- Optionally, we can add user who will manage these assets and even associate scanner appliances in this group.

### Asset Tag

- Automatically created when you create asset group.
- Beware of the business impact setting which will have an effect on the asset tag's criticality score.

## Adding Internal IP Address Ranges

1. Select IP tracked as the IP addresses are static IP addresses.
2. If they were DHCP addresses, select DNS tracked or NetBIOS tracked.
3. Type the IP address range.
4. Start a vulnerability scan immediately using all the default settings, if desired.
5. Give the new job a name.
6. Click the Launch button.
7. To look at the scan job just created, navigate to the Scan section of VMDR.
8. The new scan job has been launched and is initially in a queued state. This will change to a running state in due course.
9. Navigate back to the Asset section.

## Creating an Asset Group

1. Create an asset group. This is one method of organizing scannable hosts and associating them with users and scanners.
2. Remember that asset tags can also be used to organize assets and are often preferable to asset groups.
3. Give the new group a name.
4. Add the IP address range that should be included in this group.
5. From the list of scannable host assets, select one or more ranges.
6. An asset tag is automatically created for each asset group.
7. The tag's criticality value will be inherited from the group's business impact setting.
8. Select Low to be on the safe side, as the inherited criticality value is often not appropriate.

# Adding Scannable Host Assets to VMDR

## Overview
Laboratory activity that adds scannable host assets to the subscription, launch an initial scan, and create an Asset Group.

## Key Concepts

### 1. Tracking Methods

The tracking method depends on how the assets obtain their IP addresses.

- **IP Tracked Hosts:** Select this when assets use static IP addresses.
- **DNS Tracked Hosts:** Select this when assets use DHCP IP addresses.

### 2. Adding Scannable Host Assets

To add scannable host assets:

1. Click **New**.
2. Select the appropriate tracking method.
3. Click the **Host IPs** tab.
4. Enter the IP addresses or IP ranges.
5. If the assets are likely to have digital certificates, select **Add to CertView Module**.
6. Click **Add**.
7. Click **Apply**.

**IP ranges used in the lab:**

- `64.41.200.243-64.41.200.250`
- `10.115.117.171-10.115.117.183`

### 3. Launching an Initial Vulnerability Scan

After adding the assets:

1. Open the **Host Assets** tab.
2. Select the bottom row of hosts.
3. Click the drop-down arrow.
4. Click **Launch Scan**.
5. In the Title field, type `New assets scan`.
6. Click **Launch** to scan immediately using default settings.
7. Review the confirmation screen and click **Close**.

**Scan Status:** A newly launched scan job is initially in a **Queued** state. It will change to a **Running** state in due course.

### 4. Creating an Asset Group

An Asset Group is one method of organizing scannable hosts and associating them with users and scanners. Asset Tags can also be used to organize assets.

To create an Asset Group:

1. Open the **Assets** section.
2. In the Asset Group tab, click **New**.
3. Click **Asset Group**.
4. In the title, type `AG: External Assets`.
5. Click the **IPs** tab.
6. Click **Select IPs/Ranges**.
7. Select the bottom row of IP addresses.
8. Click **Select**.
9. Click the **Business / CVSS Info** tab.
10. Click the drop-down menu next to Business Impact.
11. Select **Low**.
12. Click **Save**.

### 5. Business Impact and TruRisk

- The Business Impact score affects the assets' TruRisk scores.
- Consider setting Business Impact to **Low** and using the Asset Criticality Score alone to define business criticality of an asset.

## Key Takeaways

- Add scannable host assets to the subscription before scanning.
- Use **IP Tracked Hosts** for static IP addresses and **DNS Tracked Hosts** for DHCP IP addresses.
- Qualys CertView can be used for assets likely to have digital certificates.
- You can launch a vulnerability scan using default settings.
- A newly launched scan job initially appears as **Queued** before changing to **Running**.
- Asset Groups organize scannable hosts and can associate them with users and scanners.
- Business Impact affects asset TruRisk scores.

## Key Application

Learned some idea how to add scannable host assets, launch an initial vulnerability scan, and organize the new assets into an Asset Group.
