## Lecture

![image](https://github.com/user-attachments/assets/f922d77c-c4c6-435e-9ff9-8c7402ba0e96)

Too many vulnerabilities are deemed critical. 52% of vulnerabilities are rated high or critical by CVSS …and less that 5% of vulnerabilities contribute to more than 80% of risk

The take-away here is that security stakeholders are measuring the wrong cyber risks - and because they’re measuring the wrong risks, they're miscommunicating cyber risk. Ultimately, they’re misled to remediate, of ill-equipped to eliminate critical cyber risk altogether.

![image](https://github.com/user-attachments/assets/596bc051-0aaf-4f4f-aede-6a3a4bc51801)
What is a modern security strategy?

It’s the economically efficient elimination of digital risk. Not all risks. Just those that threaten businesses objectives.

Why a modern security strategy is needed:

Invariably, all business objectives will be enabled by digital and AI transformation. “89% of large companies globally have a digital and AI transformation underway.” https://hbr.org/2023/07/the-value-of-digital-transformation(opens in a new tab)

Regulators know what’s coming. They’re responding by demanding more cybersecurity risk management transparency. www.sec.gov/news/press-release/2023-139(opens in a new tab) and www.digital-operational-resilience-act.com/(opens in a new tab)

Boards are paying close attention. “Corporate leaders have begun to see cyber risk for what it is: a strategic, enterprise risk, which they—not their CISOs—own.”  www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/nacd-directors-handbook-on-cyber-risk-oversight/(opens in a new tab)

Less than 1% of vulnerabilities contributed to the highest risk and were routinely exploited in the wild. This article explains the statistics in more detail: https://blog.qualys.com/vulnerabilities-threat-research/2023/12/19/2023-threat-landscape-year-in-review-part-one(opens in a new tab)

This slide shows a simple risk-analysis matrix where a risk is measured based on likelihood on the x-axis and on impact (or “consequences”) on the y-axis. The point is to find out the high-likelihood and high-impact risks to your infrastructure and prioritize those for remediation.

![image](https://github.com/user-attachments/assets/b61b4cf1-9670-4d78-bc4a-8d147d86e23d)
![image](https://github.com/user-attachments/assets/bf4102a2-3ea0-4620-8ea8-cd3241f02cbb)
![image](https://github.com/user-attachments/assets/88decedc-601a-41ae-ba9a-f8f854c7c11e)

The Asset Criticality Score (ACS) sets the business context of an asset. It is assigned explicitly to Asset Tags and implicitly to assets. The ACS of an asset has a major impact on the downstream TruRisk calculation for that asset. We look at the benefits of TruRisk and how to implement it later in this course.

An Asset Tag represents an infrastructure component and should be assigned a corresponding ACS value to indicate its importance to the organization. A Tag which represents a business-critical component (hardware, software, or service) should be assigned a higher ACS value than a Tag which represents a component which is unimportant to the organization. For example:“Production Servers” Asset Tag might have an ACS value of 4 or 5 (the maximum).

“MacBook” Asset Tag might have an ACS value of 1 (the minimum) or 2.

Impact or consequences could refer to factors such as operational disruption, financial loss, reputational damage, and regulatory non-compliance. You would need to define what these terms mean to your organization, based on factors that the organization wishes to avoid.

The ACS can be set manually by the user, can be imported as part of the CSAM CMDB Sync feature (that is, inheriting the criticality setting configured in Service Now), and inherited from an Asset Group’s Business Impact setting.

![image](https://github.com/user-attachments/assets/f6237bc1-a52d-46e5-84c9-ecb597f8be99)
Qualys TruRisk™ calculates a total risk score that represents the likelihood of exploitation by using business criticality, CVSS score, threat intelligence, and applied mitigation controls. Arbitrary-based scoring systems only represent the vulnerability metrics of the risk equation without consideration of real-time threat data that is commonly used to decide where the business needs to focus its efforts on trying to lower its risk exposure. QDS range is 1-100 and has four levels: Critical (90-100), High (70-89), Medium (40-69) and Low (1-39).

Qualys Detection Score (QDS) begins with the CVSS base score of detected vulnerabilities. It then adds temporal factors such as Threat Intelligence (including exploit code maturity, associated malware, active threat actors, and vulnerabilities trending on the dark web) and mitigating and remediating controls related to the exposure.

QDS is derived from the following factors:

Vulnerability technical details (e.g., CVSS base score)

Vulnerability temporal details (Is the exploit code mature?  Is the vuln associated with ransomware?)

Vulnerability remediation details (Has the vendor released a patch?)

QDS considers:  

CVSS Score

External Threat Intelligence (exploit code maturity, malware, active threat actors, and vulnerabilities trending on the dark web).

Mitigating Controls (CIDs) associated with the vulnerability (host specific).

Remediating Controls or patches

It is important to note that if multiple CVEs contribute to a QID, the CVE with the highest score is considered for the QDS calculation.

![image](https://github.com/user-attachments/assets/3f4c713e-a9c9-4860-a0fe-ba12339aab51)

The TruRisk score includes QDS values which have been derived not from vulnerabilities, but from CSAM Software Rules and CSAM Port Rules. These Rules cover open but unauthorized ports, installed but unauthorized software, missing software (required but not installed).

CSAM will also automatically assign a QDS when it has detected installed software which is EOL or EOS.

![image](https://github.com/user-attachments/assets/e396a8db-d2c3-4301-b12b-745250a26863)

Note: The values demonstrated in this table do not reflect any type of standard or benchmark for a Remediation SLA.

However, the values do correctly demonstrate that as Asset Criticality and Vulnerability Risk increase—the time to remediate decreases. More time is provided for lower risk assets and vulnerabilities.

There are other methods of implementing remediation SLAs using the Prioritization Report which will are explored more fully in the Operationalizing Qualys TruRisk course.

![image](https://github.com/user-attachments/assets/6945fcd6-a609-4e76-bd3f-4c9405ba9393)

VMDR Prioritization identifies and remediates the vulnerabilities that pose risk to your organization and business. The Prioritization process correlates the vulnerability information with threat intelligence and asset context to zero in on the highest risk vulnerabilities.  

An important advantage of the VMDR Prioritization Report, comes from its ability to quickly move to remediation. The Qualys Prioritization Report provides remediation options for ”Qualys Patchable” vulnerabilities.  This is accomplished with the help of Qualys Cloud Agents and the Qualys Patch Management application.

![image](https://github.com/user-attachments/assets/f74b709d-9b45-499c-999b-3638295838e0)

The Steps to TruRisk Dashboard is a great place to start when faced with these kinds of questions:

“How do we quickly map the latest news to our assets at risk?”

“Do we have time in our project roadmap to define roles and responsibilities and milestones?”

“We will need to set a series of meetings to track, discuss, and decide which risk-based scoring system to use. (Which system is best?)”

“How will the team align that to the business, to justify the dollars?”

“Can we quantify our appetite to fail?”

“Do we even know how to see business impact for our crown jewel/tier 0 assets?”

Once you start rolling on the above, two questions come into focus: “What will that cost the business, and can I connect the dots for my leaders?”

## Lecture-Video:

## Prioritizing Remediation Actions Using the Qualys VMDR Prioritization Report

### Why Prioritize
- Not all vulnerabilities are equal.
- Less than 5% of vulnerabilities cause over 80% of risk.
- Focus efforts on remediating that 5%.
- Effective prioritization is part of an effective modern security strategy.
- Prioritization means the economically efficient elimination of digital risk.
- In particular, the digital risks that threaten our business objectives.
- End goal for prioritization should be to improve business outcomes.

### Qualys TruRisk
- Qualys TruRisk helps prioritize effectively by automatically calculating how much risk an asset currently poses to the organization.
- This TruRisk score is generated using a combination of threat intelligence as well as an asset criticality score.
- Threat intelligence combined with the CVSS score of a vulnerability means prioritizing based on the likelihood that the vulnerability will be exploited, as well as the potential impact.
- Result: automatic generation of the Qualys detection score, which the platform assigns to each vulnerability.
- Inventory risks such as open ports or end-of-life software are also given a Qualys detection score.

### Business Context and Asset Criticality Score
- Business context is provided by the asset criticality score or ACS.
- The ACS is assigned by the user by the use of asset tags.
- The highest score of five would mean that an asset is part of a mission critical system.
- When assigning ACS values, consider what might happen if this asset were compromised.
- Consider how much impact that would cause to business objectives.
- A score of five should only be applied to the most critically important parts of the infrastructure.
- A score of one should be applied to assets which, if compromised, would not impact business operations.
- An example might be development and test assets.
- An asset is likely to have multiple tags assigned to it.
- The tag with the highest value will be used to calculate the asset’s TruRisk score.

### Remediation SLAs
- Example SLA: critical vulnerabilities on an asset with a severe TruRisk score should be remediated within one day.
- The prioritization report enables implementation of remediation SLAs by focusing on groups of assets, using tags, and selecting the appropriate QDS, ACS, and TruRisk values.
- For customers who have Qualys Patch Management, a workflow is provided by means of the Patch Now button.
- Start a patch deployment job based on the selections made in the report.

### Demonstration: Using the VMDR Prioritization Report
- In the prioritization screen, choose the Reports tab and click the plus button to create the report.
- The prioritization report works with asset tags to focus on a particular group of assets.
- In the search field, type **production**, which is in the name of the tag associated with the assets to prioritize.
- All matching tags are now visible.
- Click the tag **DOM production** to select it.
- Click the arrow to the right of the field to prioritize the selected asset tag above the search field.
- Click the toggle switch to change to TruRisk mode.
- The report is presented using the TruRisk data.
- The report enables filtering by TruRisk score, asset criticality, and Qualys detection score.
- Click the checkbox next to **high** to remove assets with a high TruRisk score.
- From the results in the TruRisk score panel, click the checkbox next to **severe**.
- Using the remaining selections means prioritizing the most critical vulnerabilities on the most important assets in the production domain.
- To prioritize, click the **Prioritize Now** button.
- The results show the number of affected assets, the number of vulnerabilities, and the number of patches required to remediate according to the criteria selected.
- If required, click the **Patch Now** button to launch a patch deployment job with this data preselected.

### Implementing Remediation Strategy
- The prioritization report allows implementation of the remediation strategy in different ways for any group of assets.
- Filter by asset criticality and Qualys detection score, or by using Qualys TruRisk.
- The Export button in the top right corner allows export of this data in the form of a dashboard widget to monitor remediation requirements.

### Summary
- The VMDR prioritization report can be used to implement remediation SLAs.

## Lab-Lecture:
## Prioritize Remediation Actions using the VMDR Prioritization Report

### Steps

1. Click on the plus symbol in the middle of the screen to continue.

2. The Prioritization Report works with asset tags to focus on a particular group of assets.
   - In the search field, type the word **Production** and press enter.

3. In the search results, click the tag: **DOM: Production**

4. Click the arrow to the right of the search field.

5. Above the search field, click the toggle switch to change to **TruRisk** mode.

6. The report enables us to filter by **TruRisk score**, **asset criticality**, and **Qualys Detection Score**.
   - In the **TruRisk Score** panel, click the checkbox next to **High**.

7. In the **TruRisk Score** panel, click the checkbox next to **Severe**.

8. Using the remaining selections means that you will be prioritizing the most critical vulnerabilities on the most important assets in the **Production** domain.
   - Click the **Prioritize Now** button.

9. The results show:
   - the number of affected assets
   - the number of vulnerabilities
   - the number of patches required to remediate, according to the criteria that you have selected.

10. If required, you could click on the **Patch Now** button to launch a patch deployment job with this data pre-selected.
    - Click anywhere to continue.

11. Using the Prioritization Report you could implement your remediation strategy in different ways.
    - For any group of assets, you could filter by **Asset Criticality** and **Qualys Detection Score** as we have seen, or by using **Qualys TruRisk**.

12. The **Patch Now** button provides workflow from prioritization straight through to patch deployment.
    - In the top right corner you can also export your choices in the form of a dashboard widget so that you can monitor remediation requirements.

13. In this lab, you have learned how the VMDR Prioritization Report can be used to implement your remediation SLAs.
    - You can filter the report by asset tag, asset criticality, and by QDS.
    - You may now close this browser tab.

### Tutorial Completed
- Congratulations on finishing this tutorial!

### Example 1
- **Asset Tag = DOM: Production**
- **Asset Criticality Score = 5**
- **Qualys Detection Score = High, Critical**
- This would prioritize the most critical vulnerabilities on the most critical production assets.

### Example 2
- **Asset Tag = DOM: Production**
- **TruRisk Score = Critical**
- This would prioritize all vulnerabilities on the production assets which currently pose the most risk to the organization.
