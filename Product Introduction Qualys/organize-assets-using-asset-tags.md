# Organize Assets Using Asset Tags

## Asset Tags – Use Cases

It is recommended that you build an asset tag hierarchy that emulates your existing infrastructure in a way which is useful to both the security and infrastructure teams. In this course, we focus on the second use case.

### Use Case 1 – Organizing the Asset Inventory

- OS: Windows
- TYPE: Server
- TYPE: Network Device

### Use Case 2 – Identifying Assets Which Share Common Criteria for Reporting or Remediation Purposes

- INFO: Domain Controller
- BUS: Customer Payments

### Use Case 3 – Providing Additional Information (e.g., for Operational and Troubleshooting Purposes)

\- INFO: Load Balancer Detected

## Example Using Asset Tags for Vulnerability Scanning

Asset tags can be used to focus a vulnerability scan on a particular network block of assets.

- If specifying more than one tag, ensure that you make appropriate use of the Any/All drop-down menu.
- If the address range includes Cloud Agent hosts, then select Temporarily add agent addresses.

## Example Using Asset Tags to Prioritize Remediation

Asset tags can be used to create a prioritization report which will guide the remediation team on requirements for each patch group.

Example: Production servers on the San Diego corporate LAN.

\- Notice the use of All, which means an asset needs to have all four of these tags in order for it to be included in this report.

## Example Using Asset Tags to Focus a Vulnerability Report

\- Asset tags can help you create a report which focuses on a particular group of assets that are of interest to the stakeholders (report recipients).

# Organize Assets Using Asset Tags

## 1. Asset Tag Use Cases

Asset tags can be used in VMDR for the following purposes:

1. Identifying assets for meaningful reports – Identify assets in order to produce more meaningful reports.
2. Prioritizing remediation – Prioritize groups of assets for remediation activities.
3. Directing vulnerability scans – Direct a scan towards a particular group of assets.

### Example 1: Targeting a Vulnerability Scan

- A tag can automatically be applied to assets which have an IP address within a certain subnet.
- This tag can be used as the target for a vulnerability scan.

### Example 2: Prioritizing Remediation

- Select a number of different tags in the VMDR prioritization report.
- Use the All dropdown choice to prioritize remediation for assets that have all the selected tags applied.
- Example: Windows servers in the production domain that have an IP address on the San Diego LAN.

### Example 3: Focusing a Vulnerability Report

- Focus a report on a certain group of assets.
- Example: The report recipient is the manager of the IT operations team who wants to know the current risks to live Windows servers.

## 2. Creating Asset Tags

The first tag created will identify all assets on a specific subnet. This is particularly useful as part of a vulnerability scan.

### Naming Convention and Favorites

- Keep to a consistent naming convention so you can identify tags more easily and use them more efficiently.
- When typing queries in a subscription with many asset tags, save a tag as a favorite so you can find it again more easily.

### Asset Criticality Score (ACS)

- Setting an asset criticality score is essential if you want to take advantage of Qualys TruRisk as a way of measuring the risk that assets pose to the organization.
- The asset criticality score should reflect the impact on the organization if an asset were to be compromised.

## 3. Creating a Dynamic Asset Tag for a Subnet

The tag in this example will be applied to all assets in the internal network regardless of their importance. For that reason, an asset criticality score of 1 is selected.

If there are high-value assets on this subnet, their criticality can be measured using other, more specific tags.

### Dynamic Tag Configuration

1. Create a dynamic tag.
2. Select a rule engine.
3. Select the appropriate rule engine for the intended criteria.
4. Enter the IP address range for the subnet.
5. Enable Evaluate rule on creation.
6. Click Create to create the tag.

### Key Concepts

- Dynamic tag: Assigned to assets automatically when certain query conditions are fulfilled.
- Rule engine: Used to define the criteria for applying the tag.
- Evaluate rule on creation: Allows the platform to start applying the tag to relevant assets immediately rather than waiting for the next set of scan results.

After creating the tag, the platform evaluates which assets should have the tag applied.

## 4. Creating a Dynamic Asset Tag for a Domain

The next tag identifies all assets that belong to a certain domain. The intention is to use this tag to focus a report on a specific group of assets.

### Configuration

1. Type the tag name according to the naming convention.
2. Set the asset criticality score to 3, because all assets on the production domain are expected to be at least of medium importance.
3. Select Asset Inventory as the rule engine.
4. Enter the appropriate query.
5. Enable Evaluate rule on creation.
6. Click Create.

## 5. Key Takeaways

- Asset tags help identify assets for vulnerability scanning, remediation prioritization, and reporting.
- Consistent naming conventions make tags easier to identify and manage.
- Asset criticality scores should reflect the potential organizational impact if an asset is compromised.
- Dynamic asset tags automatically apply to assets that meet specified query conditions.
- Different rule engines can be used to create dynamic tags for different use cases.


Here are accurate, structured notes based on the provided tutorial for creating asset tags in Qualys CSAM (Cyber Security Asset Management).

### **Tutorial Overview**
**Objective:** Create two dynamic asset tags that can be used for VMDR scanning or reporting.
**Application:** Qualys CSAM (Tags section)

---

### **Tag 1: NW: Internal LAN**
*Purpose: Identify all assets on a specific subnet.*

1.  **Basic Details:**
    *   Name: `NW: Internal LAN`
    *   Mark as Favourite: Checked (recommended for easy finding later).
2.  **Asset Criticality Score:**
    *   Toggle: Enabled
    *   Score: `1` (Lowest)
    *   *Reasoning:* The tag applies to ALL internal network assets regardless of their individual importance.
3.  **Tag Properties:**
    *   Tag Type: **Dynamic**
    *   Rule Engine: `IP Address In Range(s)`
    *   IP Address Range: `10.115.117.0/24`
4.  **Evaluation:**
    *   Evaluate Rule on Creation: **Checked**
    *   *Reasoning:* This forces the platform to apply the tag to relevant assets immediately using existing data, rather than waiting for the next scan results.
5.  **Action:** Click **Create**.

---

### **Tag 2: DOM: Production**
*Purpose: Identify production domain assets.*

1.  **Basic Details:**
    *   Name: `DOM: Production`
    *   Mark as Favourite: Checked.
2.  **Asset Criticality Score:**
    *   Toggle: Enabled
    *   Score: `3` (Mid-tier)
3.  **Tag Properties:**
    *   Tag Type: **Dynamic**
    *   Rule Engine: `Asset Inventory`
    *   Query: `asset.subdomain:qualystraining.local`
4.  **Evaluation:**
    *   Evaluate Rule on Creation: **Checked**
5.  **Action:** Click **Create**.

---

### **Key Takeaways & Concepts**
*   **Dynamic Tags:** Tags that automatically get applied to assets as soon as they meet the specified query requirements.
*   **Asset Criticality Score:** A 1-5 scale representing the impact to the organization if an asset is compromised. Taking advantage of this feature is essential for utilizing Qualys TruRisk.
*   **Evaluate Rule on Creation:** A crucial checkbox that triggers immediate evaluation against already-scanned assets, bypassing the wait time for the next scheduled scan.
*   **Next Steps:** Once created, these dynamic tags can be applied to Scan Jobs or Reports.
