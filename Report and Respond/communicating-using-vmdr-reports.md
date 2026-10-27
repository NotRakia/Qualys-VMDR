Lecture:
![image](https://github.com/user-attachments/assets/6075e421-d967-43e5-b564-24a05719815a)

![image](https://github.com/user-attachments/assets/2c29481f-c95a-4158-9cf9-14c087e14052)

![image](https://github.com/user-attachments/assets/91cd6ec8-5664-4dd7-9eaa-34e354a9d137)
This diagram illustrates the basic components needed to build a report (scorecard reports, authentication reports and asset search reports, do not require a report template).

All report types require that you select a report source or the assets you intend to target in your report. You can accomplish this using a range of IP addresses or even a single IP, or any asset groups or asset tags you've created.

For the report types that require a report template, you can choose a custom template that you have created, or select one from the Qualys Report Template Library. A report template provides dozens of options for selecting the data and findings that will be included in your report, how that data will be displayed, and who will be able to view the reports that are generated.

Notice that a Qualys scanner appliance is not included in this diagram.  Running a report does not in any way launch a scan. Scanning and reporting are separate tasks, and therefore scans must be completed, prior to building their associated reports.

![image](https://github.com/user-attachments/assets/88b0ee7c-adcc-40cd-9d03-c665bcf38de3)
The TruRisk Summary report provide executives with a comprehensive overview of the organization's security risk landscape, based on TruRisk analysis. This report offers unprecedented insights into an organization’s security risk posture and actionable insights, empowering executives to prioritize and address the most critical risks efficiently. Armed with actionable insights, practitioners and managers can present the organization's security posture to Chief Information Security Officers (CISOs).

Video Lecture:
# Structured Notes: Communicating Scan Results Using VMDR Report Templates

## Purpose of VMDR Reports
- VMDR reports are especially useful when we need to provide information to stakeholders who do not have a login to the QUALIS platform.
- We can communicate measurements, comparisons, and progress in an easy to understand format.

## General Guidelines
- Meet stakeholders where they are at the scale of their accountability.
- Rather than bombard them with details that they don’t understand or even care about.
- Identify who our stakeholders are and what they need to see for their own job requirements.
- Example: is the report for a security operations technical staff member, or is it for an infrastructure team who carry out patching tasks?

## Components of a Report
- In the findings tab of the report template, specify which assets are being reported on and which set of scan results is the basis of the data.
- In the display tab, choose the specific elements which will appear in the report.
- In the filter tab, choose which vulnerabilities are being reported on.
- Choose to highlight running or stop services, open or closed ports.
- Finally, schedule the report to run at certain times.
- Recommendation: the report schedule should match the scanning schedule.
- If you scan weekly, the report schedule should also be weekly.

## Findings Tab
- Choose whether the report will be based on a specific scan job or instead if it uses host-based findings.
- Host-based findings use data from different scans to show vulnerability history and trending.
- General scanning recommendation: scan all assets for all vulnerabilities.
- Reporting recommendation: focus the report on a subset of assets which are of interest to the stakeholder.
- You might also need to focus the report on a certain subset of vulnerabilities such as those related to the latest patch.
- Patch Tuesday reports can be run on demand or on a schedule.
- Keep your reporting schedule aligned to your scanning schedule.

## Demo: Create a Report Template and Scheduled Report Job
- Create a search list to focus the report on a specific group of Qs.
- Click the new button.
- Select static list from the options in the dropdown menu.
- In the title field, type Microsoft Patch Tuesday Qs and press enter.
- Mark the checkbox to make this search list globally available in VMDR.
- This makes it available to other users in this subscription.
- Choose the Qs to include in this list.
- Select Qs from the options on the left.
- Click the manual button to manually add the Qs to the list.
- The Q IDs for each Patch Tuesday can be found on the Qualys blog.
- Paste the relevant Q IDs in the box.
- Click okay to continue.
- Click save to save the list.

## Access the Report Section
- Use the navigation bar to access the report section.
- Select reports from the report screen.
- Choose the templates tab to create a new template.
- Use the new button.
- Choose scan template from the dropdown menu to create a template that will use scan data.

## Create the Report Template
- Create a report template which will focus on the Patch Tuesday Q IDs for a specific group of assets.
- In the title field, type Microsoft Patch Tuesday Q IDs and press enter.
- Recommended: keep reports consistent.
- Click the checkbox next to make this a globally available template so that it is visible to other users in the subscription.
- Select the findings tab to configure any specifics about the source data.
- For this template, choose to include data from a range of scan results or from one specific scan result.
- Host-based findings use data from more than one scan.
- Job is selected by default.
- To filter the template so that reports focus on a specific group of assets, add one or more tags.
- Select add tag to choose the assets to focus on.
- In the tag search field, type server and press enter to find tags that include the word server.
- Select OS Windows server from the search results.
- This report will present data from assets with the OS Windows server tag.
- Include findings from both agent data and scan data: choose the radio button next to all data.

## Display Settings
- Select display from the left side menu.
- Customize what sections will appear in the report output.
- Click text summary to include a summary text in the report.
- Select vulnerability details to see information about specific vulnerabilities in the report.
- Select threat to include details about the threats posed by discovered vulnerabilities.
- Click impact to include information about the impact of reported vulnerabilities.
- Choose patches and workarounds to get information on how to remediate or how to lessen the impact of the vulnerabilities in the report.
- Click virtual patches and mitigating controls to get further information in the report on available virtual patches or controls.
- Note that true risk details are already included by default.

## Filter Tab
- Choose specific Qs for the report to focus on.
- Earlier, a search list was created as a manually selected list of Qs.
- Use the custom radio button so that you can select the search list created earlier.
- Click add lists to see the available search lists.
- Choose static search lists like the one created in this demo, and also dynamic search lists, which function as a saved knowledge base search.
- Select the checkbox next to Microsoft Patch Tuesday Qs to choose the previously created list.
- Click okay to accept this selection.
- Select the checkbox next to exclude superseded patches.
- This refines the report information by excluding information about patches which have been superseded by later patches.
- Click save to save these settings.
- A template has now been successfully created upon which scheduled reports will be based.

## Configure the Schedule
- Select the schedules tab.
- Choose new to create a new schedule.
- Select scan report from the dropdown menu.
- Choose template based to schedule a scan report using the template created earlier in this demo.
- In the title field, type Microsoft Patch Tuesday Q IDs.
- Click select next to the report template field.
- Select the template created earlier: Microsoft Patch Tuesday Q IDs.
- Note that the report format may be changed, but leave this on CSV for now.
- The assets can also be changed at this point if required.
- Select scheduling.
- Click the calendar icon to set the start date.
- Choose February 8th from the calendar widget as the start date for this report to run.
- Scroll down to further adjust scheduling options.
- Next it occurs: click the dropdown menu to select how frequently the report should run.
- Choose weekly.
- Select Saturday.
- Given these settings, the report will run every Saturday starting on February 8th.
- Click schedule to accept these settings with this schedule.
- The schedule job has now been created.
- Recommended: your reporting schedule should coincide with your scanning schedule.
- If you scan weekly, then you should report weekly.

## Conclusion
- have learned how to create a scheduled report using a search list and a report template.

Lab Lecture:
