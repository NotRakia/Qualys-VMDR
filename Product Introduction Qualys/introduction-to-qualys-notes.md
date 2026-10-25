# Effective Vulnerability Management (EVM)

## Overview

VMDR helps to implement EVM through three steps: **See, Understand, and Act.**

### 1. See
- Identify all assets.
- Detect critical vulnerabilities across OS and applications.

### 2. Understand
- Know what poses the most risk to your organization.
- Automatically prioritize the riskiest vulnerabilities of your most critical assets.
- Communicate risk effectively to different stakeholders.

### 3. Act
- Implement remediation.
- Implement mitigation.

---

# Qualys Enterprise TruRisk Platform

The Qualys Enterprise TruRisk Platform lets you **Measure, Communicate, and Eliminate** cyber risk.

### 1. Measure
This means you can calculate the known and unknown cyber risk across your internal and external attack surface and quantify it in a way that meets the unique demands of your business.

### 2. Communicate
This means you can go beyond just enumerating your cyber risk posture throughout your organization.

### 3. Eliminate
This means you can't just rely on patching alone. You should eliminate the most critical vulnerabilities living across your environment with easy-to-use workflows that unify your security and IT teams like never before.

---

# Qualys Sensors

## Overview

Qualys Sensors:
- Are software agents or hardware/virtual appliances that collect inventory, security, and vulnerability data.
- Act as the eyes and ears of the Qualys Enterprise TruRisk Platform, continuously monitoring and assessing the security posture of systems, applications, and networks.
- Are centrally managed and self-updating.
- Are used for:
  - **Discovery:** Asset discovery and inventory.
  - **Assessment:** Vulnerability and compliance.
  - **Patch:** Patch management.

## Qualys Sensors for VMDR

### 1. Local Scanner Appliances
- Scan anything with an IP.
- Available as a physical appliance and as a virtual appliance.

### 2. Internet (Remote or External) Scanners
- Conduct perimeter discovery and scanning to get an attacker's view.

### 3. Cloud Agents
- Qualys Cloud Agent is installed as a local system service on each host.
- One agent per host.
- Agents operate with system-level privileges, automatically sending assessment data back to the Qualys Cloud Platform at regularly scheduled intervals.

The sensors covered in this course are **Local Scanner Appliances, Internet (or "Remote") Scanners, and Cloud Agents.**

---

# Use Cases of Qualys Sensors

## 1. Local Scanners (Scanner Appliances)

### Overview
- Are deployed on local area networks and are commonly used to scan assets within reserved or private IP address ranges.
- Can be deployed as physical or virtual appliances.
- Once installed, each Scanner Appliance keeps itself updated with the latest vulnerability signatures via its connection to the Qualys Cloud Platform.

### Use Cases
A Qualys Scanner Appliance is used to conduct vulnerability and policy compliance scans of host assets. It has a remote perspective of any host you target.

Its ability to perform a vulnerability assessment test is directly impacted by:
- The number and type of open service ports on any given host.
- The presence of any network filtering devices that might potentially obstruct individual scan packets.

### Scanner Placement and Network Considerations
Scanning through firewalls is common, but the recommendation would be to locate a scanner appliance in each security zone.

- The most optimal placement would be to have the appliance as close to the scan targets as possible.
- Ensure that you have the proper routing between the scanner appliance and host targets.

---

## 2. External (Internet) Scanners

### Overview
- Are always available using the Qualys Cloud Scanner setup around the globe at Qualys Security Operations Centers (SOCs).
- Scan assets from the outside using the Qualys External Scanners already associated with your account.
- Provide an **external attacker view** of your vulnerabilities from the outside.
- Allow you to automatically launch scans against your external (public IP) assets.

If you have a Scanner role or above in Qualys, you'll automatically be able to launch scans against your external (public IP) assets.

### Scanning Considerations
External scans should mirror an attacker's perspective.

- No "safelisting" is necessary.
- Firewalls should block these scans to simulate real-world attack conditions.

### How to Find the Qualys External Scanner IP Ranges
1. Log into your Qualys VMDR subscription.
2. Go to **Help (upper right corner) > About**.

---

## 3. Cloud Agent

### Overview
- Qualys Cloud Agents run as a local process on the host they protect.
- Qualys agents support a wide variety of OS platforms.
- Agents play a special role in VMDR by providing the patching and response functions.
- They deliver vulnerability assessment for assets that are not easily scanned by an appliance, such as:
  - Laptops used by roaming users.
  - Distributed offices.
  - Public cloud instances.
- They are lightweight, extensible, self-updating, and centrally managed.

### Asset Visibility and Assessment
The Qualys Cloud Agent:
- Allows global visibility of IT assets, including cloud, mobile, and virtual devices that are not always connected and are not easily scanned with other Qualys Sensors.
- Helps monitor ephemeral cloud instances, roaming devices, and remote systems that are difficult to monitor using only network scanners.
- Communicates with the Platform efficiently. Once the initial full profile of the asset is uploaded to the Platform, only detected changes are uploaded in the future, which can significantly reduce network bandwidth compared to traditional network scanning.

### Management and System Impact
- Agents are lightweight, remotely deployable, self-updating, and centrally managed.
- They are designed to have minimal system and network impact.
- The Cloud Agent is modular. Since it runs locally on the host, it offers additional functionality, such as patching, deploying scripts, file integrity monitoring, or threat response.
- Qualys continually offers new modules to work with the Agent to provide a single security and compliance solution for the global asset inventory.

### CAPS Feature
The **Cloud Agent Passive Sensor (CAPS)** feature monitors network traffic within the agent's subnet to detect devices not presently under management and eliminate blind spots.

### Qualys Applications and Agent Modules
Global AssetView (GAV) or CyberSecurity Asset Management (CSAM) will be automatically activated, depending on which app is included in your subscription. This provides the Platform asset inventory for the Agent host.

The following app modules can also be activated, depending on what is included in your subscription:
- Vulnerability Management (VM)
- Security Configuration Assessment (SCA)
- Policy Compliance (PC)

### Agent-Exclusive App Modules
The following Qualys app modules are Agent-exclusive:

- Patch Management (PM)
- File Integrity Monitoring (FIM)
- Custom Assessment & Remediation (CAR)
- Endpoint Detection & Response (EDR)
- Cloud Agent Passive Sensor (CAPS)
- Software Composition Analysis (SwCA)

---

# Key Takeaways

- **See:** Identify assets and detect critical vulnerabilities.
- **Understand:** Determine risk, prioritize vulnerabilities, and communicate risk to stakeholders.
- **Act:** Implement remediation and mitigation.
- **Measure, Communicate, Eliminate:** Use the Qualys Enterprise TruRisk Platform to quantify, communicate, and reduce cyber risk.
- **Local Scanner Appliances:** Assess host assets from the network perspective, particularly within local or private IP ranges.
- **External Scanners:** Assess public-facing assets from an external attacker's perspective.
- **Cloud Agents:** Provide ongoing asset visibility and assessment for hosts that are difficult to scan with network appliances, while also supporting additional security functions.
- **Sensor placement:** Place scanner appliances close to their targets, with proper routing and consideration for security zones.
- **Agent-exclusive modules:** Include Patch Management, FIM, CAR, EDR, CAPS, and SwCA.
