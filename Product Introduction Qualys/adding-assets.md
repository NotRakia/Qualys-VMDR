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

## Key Application
When preparing a vulnerability scan, identify the host assets to scan, add them to your Qualys subscription, and enter their IP addresses using the appropriate format.
