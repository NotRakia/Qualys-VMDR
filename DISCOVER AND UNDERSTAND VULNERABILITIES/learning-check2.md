Why does Qualys recommend performing scans in “authenticated” mode?

a. Because it includes “Risk” in addition to “Severity”

b. Because it is more likely to discover high-severity vulnerabilities 

c. Because it includes all QIDs in every scan 
d. Because it provides the most accurate results with fewer false positives - selected

Correct

Potential Vulnerabilities include vulnerabilities that cannot be fully verified. In these cases, at least one necessary condition for the vulnerability is detected. It's recommended that you investigate these vulnerabilities further. The service can verify the existence of some potential vulnerabilities when authenticated trusted scanning is enabled.

Please note that even if a QID is detected by an authenticated scan or a cloud agent that doesn't mean that the vulnerability will be categorized as Confirmed. You can have potential vulnerabilities detected by authenticated scans and agents. These often include vulnerabilities where we don't have any mechanism to detect if the patch/workaround is applied or not.
