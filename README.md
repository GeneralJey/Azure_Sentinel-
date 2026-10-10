# Microsoft Sentinel SIEM Lab — RDP Attack Monitoring & Geolocation

**Project Status:** Completed | Azure lab decommissioned

**Category:** Security Operations (SOC) · Cloud Security · SIEM · Threat Monitoring

## Project Overview

This project demonstrates the deployment of a Microsoft Azure security monitoring lab to collect, enrich, analyze, and visualize Windows authentication activity associated with attempted Remote Desktop Protocol (RDP) attacks.

The lab used a Windows virtual machine configured as a temporary honeypot, a custom PowerShell script, an IP geolocation service, Azure Log Analytics, and Microsoft Sentinel.

The objective was to transform raw Windows security events into structured data and visualize the geographic distribution of observed authentication attempts.

**Key technical areas demonstrated:**
- Azure virtual machine deployment and configuration
- Windows security event analysis
- PowerShell scripting and log processing
- IP geolocation enrichment
- Custom log ingestion into Azure Log Analytics
- Microsoft Sentinel queries and workbook visualization

## Lab Architecture

The following represents the logical data flow used in the project.

```text
Internet
   |
   v
Azure Windows VM (Honeypot)
   |
   v
Windows Event Viewer
   |
   v
PowerShell Log Processing
   |
   +----> IP Geolocation API
   |
   v
Enriched Custom Log File
   |
   v
Azure Log Analytics Workspace
   |
   v
Microsoft Sentinel
   |
   v
Geographic Attack Visualization
```

## Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Azure | Cloud infrastructure hosting |
| Windows 10 VM | Honeypot and security event source |
| Windows Event Viewer | Authentication event analysis |
| PowerShell | Event processing and enrichment |
| IP Geolocation API | Geographic metadata lookup |
| Azure Log Analytics | Centralized log ingestion and querying |
| Microsoft Sentinel | Security monitoring and visualization |
| Microsoft Defender for Cloud | Cloud security configuration and visibility |

## Implementation Walkthrough

### Phase 1 — Deploy the Azure Honeypot

Deployed a Windows virtual machine in Microsoft Azure to generate and observe security events associated with internet-exposed RDP access.

The virtual machine was used exclusively for a temporary security research lab.

**1. Deploy the virtual machine**

![Azure virtual machine deployment](https://imgur.com/i72JdLm.png)

**2. Configure network access**

Configured permissive inbound firewall rules as part of the isolated honeypot experiment.

![Azure firewall configuration](https://imgur.com/4Eq2vWm.png)

**Security consideration:** Broadly exposing RDP increases the risk of unauthorized access. This configuration should not be used for production systems. Production environments should restrict management access through approved secure access methods, such as VPNs or managed administrative services.

### Phase 2 — Configure Azure Security Services

Created the Log Analytics workspace and reviewed Microsoft Defender for Cloud configuration.

**3. Create a Log Analytics workspace**

![Log Analytics workspace](https://imgur.com/RB79w0D.png)

**4. Configure the cloud security environment**

![Defender for Cloud environment](https://imgur.com/QMpvl11.png)

**5. Review security posture management settings**

![Defender for Cloud configuration](https://imgur.com/CXiAPFD.png)

**6. Verify the Azure virtual machine**

![Azure virtual machine dashboard](https://imgur.com/VLKiK0l.png)

### Phase 3 — Examine Windows Authentication Events

Connected to the Windows virtual machine and reviewed events recorded by the operating system.

**7. Access the virtual machine through RDP**

![Remote Desktop connection](https://imgur.com/x3crNFT.png)

**8. Inspect Windows Event Viewer**

![Windows security events](https://imgur.com/F6w8b98.png)

The Windows event logs provided the source information used for subsequent processing and visualization.

### Phase 4 — Enrich Security Events Using PowerShell

Developed a log-processing workflow using PowerShell and an external geolocation service.

The workflow associated source IP information with geographic metadata and prepared structured log records for ingestion into Azure.

**9. Retrieve IP geolocation information**

![IP geolocation API](https://imgur.com/H2qlWd5.png)

**10. Process event information with PowerShell**

![PowerShell event processing](https://imgur.com/vwBGfVz.png)

**11. Examine the generated custom log**

![Custom security log](https://imgur.com/BVv2BEp.png)

**Technical note:** IP geolocation is approximate and does not establish an attacker's physical identity or precise location. VPNs, proxies, and compromised systems can affect the apparent origin of activity.

### Phase 5 — Ingest and Structure Logs in Azure

Configured custom log ingestion and field extraction to make the enriched data usable for analysis.

**12. Create the custom log in Log Analytics**

![Custom log ingestion](https://imgur.com/jgVateF.png)

**13. Configure structured fields**

![Custom log fields](https://imgur.com/ADphsax.png)

**14. Configure field extraction — Part 1**

![Field extraction configuration part one](https://imgur.com/Yvfq1Ny.png)

**15. Configure field extraction — Part 2**

![Field extraction configuration part two](https://imgur.com/JMbqjg9.png)

**16. Review the enriched log data**

![Enriched log data](https://imgur.com/jG4WSkP.png)

This phase demonstrates how raw security information can be transformed into structured records for centralized analysis.

### Phase 6 — Analyze and Visualize Security Activity

Used Azure log queries and a Microsoft Sentinel workbook to visualize the geographic distribution of observed authentication activity.

**17. Create the log query**

![Log query](https://imgur.com/CRGfvCw.png)

**18. Visualize RDP authentication activity geographically**

![Microsoft Sentinel geographic visualization](https://imgur.com/L4BeSkJ.png)

The resulting visualization provided a geographic overview of observed activity based on enriched source IP information.

## Results and Observations

The lab demonstrated a functioning workflow for:

- Collecting Windows security event information.
- Processing event data with PowerShell.
- Enriching IP addresses with geographic metadata.
- Ingesting custom records into Azure Log Analytics.
- Querying the resulting dataset.
- Visualizing authentication activity in Microsoft Sentinel.

The geographic visualization supported investigation of activity patterns, but it did not independently prove the identity of attackers, successful exploitation, or confirmed compromise.

No attack-prevention or incident-response effectiveness metrics are claimed for this project.

## Security Considerations

This experiment used a deliberately exposed system to observe potentially malicious authentication attempts.

For a production environment, appropriate safeguards would include:

- Restricting inbound RDP access.
- Requiring strong authentication and appropriate administrative access controls.
- Applying operating system and application updates.
- Monitoring authentication activity.
- Using network segmentation and least-privilege policies.
- Establishing incident response and recovery procedures.

The temporary Azure lab was subsequently decommissioned.

## Lessons Learned

This project provided practical experience with:

**Security event collection:** Understanding how Windows records authentication-related activity.

**Log enrichment:** Using PowerShell and external data sources to add investigative context.

**SIEM engineering:** Preparing, ingesting, and querying custom security logs.

**Security visualization:** Presenting event data through Microsoft Sentinel workbooks.

**Cloud security:** Understanding the operational and security implications of exposing cloud-hosted services.

**Threat analysis:** Recognizing the limitations of geolocation data and distinguishing suspicious activity from confirmed security incidents.

## Project Status and Evidence

**Status:** Completed — Lab decommissioned.

The original Azure environment is no longer running. The screenshots in this repository preserve the historical implementation walkthrough.

The project is maintained as a technical portfolio case study rather than an active security monitoring service.

---

**Author:** Jermaine Faltine

[GitHub Profile](https://github.com/GeneralJey) | [LinkedIn](https://www.linkedin.com/in/jermaine-faltine/)
