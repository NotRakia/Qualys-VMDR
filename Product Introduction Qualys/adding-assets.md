# Adding Assets to VMDR

## Overview
For scanning to begin, you must first add scannable host assets to your subscription.

## Key Concepts

### 1. Scannable Host Assets
- Typically assets in fixed locations, such as servers or workstations on the corporate LAN.
- The tracking method impacts how the hosts will be listed in scan reports.
- Scan results are always sorted by IP address.

### 2. IP Address Formats

IPs may be entered in any of the following formats:

| Format | Example |
|---|---|
| List of single IPs | `17.16.20.5, 17.16.20.21` |
| IP ranges | `167.216.205.1-167.216.205.254` |
| CIDR | `192.168.87.0/24` |

### 3. Tracking Methods
- **IP Tracked Addresses**
- **DNS Tracked Addresses**
- **NetBIOS Tracked Addresses**

## Key Takeaways
- Add scannable host assets to your subscription before scanning.
- The tracking method determines how hosts are listed in scan reports.
- Scan results are always sorted by IP address.
- IP addresses can be entered as individual IPs, IP ranges, or CIDR notation.

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


