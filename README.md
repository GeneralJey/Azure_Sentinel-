# Microsoft Sentinel SIEM Lab — RDP Attack Monitoring & Geolocation

**Focus:** Security event collection, enrichment, SIEM analysis, and visualization  
**Tools:** Microsoft Azure, Windows 10, PowerShell, IP geolocation API, Log Analytics, Microsoft Sentinel, Microsoft Defender for Cloud  
**Status:** Completed; Azure lab decommissioned

## Objective

Build a temporary Azure lab to collect Windows authentication activity associated with attempted RDP attacks, enrich source IP information with geographic metadata, ingest structured records into Azure Log Analytics, and visualize the activity in Microsoft Sentinel.

The geographic view supported analysis of observed activity; it did not prove an attacker's identity, exact location, successful exploitation, or confirmed compromise.

## Environment

| Component | Details |
| --- | --- |
| Cloud platform | Microsoft Azure |
| Event source | Windows 10 virtual machine used as a temporary honeypot |
| Event inspection | Windows Event Viewer |
| Processing and enrichment | PowerShell and an IP geolocation API |
| Log storage and queries | Azure Log Analytics |
| Analysis and visualization | Microsoft Sentinel workbooks |
| Additional security service | Microsoft Defender for Cloud |
| Status | Lab decommissioned; screenshots preserve the historical walkthrough |

## Implementation

1. **Deploy the honeypot:** Created a Windows VM and configured inbound network access for the isolated RDP observation exercise.
2. **Set up Azure services:** Created a Log Analytics workspace and reviewed Defender for Cloud configuration.
3. **Inspect authentication events:** Connected to the VM and reviewed Windows Event Viewer records.
4. **Enrich the event data:** Used PowerShell and an external geolocation service to associate source IP information with geographic metadata and prepare structured records.
5. **Ingest and structure logs:** Configured custom log ingestion and field extraction in Log Analytics.
6. **Analyze and visualize:** Queried the resulting data and built a Microsoft Sentinel workbook view of geographic authentication activity.

The lab used permissive inbound rules as part of the honeypot experiment. Broad RDP exposure increases risk and should not be used for production systems. Geolocation is approximate and can be affected by VPNs, proxies, or compromised intermediary systems.

## Evidence

The logical data flow is shown in [images/microsoft-sentinel-lab-architecture.png](images/microsoft-sentinel-lab-architecture.png). The following historical screenshots are linked in the repository README:

- Azure VM deployment — [VM deployment](https://imgur.com/i72JdLm.png), [firewall configuration](https://imgur.com/4Eq2vWm.png), and [VM dashboard](https://imgur.com/VLKiK0l.png).
- Azure security services — [Log Analytics workspace](https://imgur.com/RB79w0D.png), [Defender for Cloud environment](https://imgur.com/QMpvl11.png), and [security posture settings](https://imgur.com/CXiAPFD.png).
- Windows event collection — [RDP connection](https://imgur.com/x3crNFT.png) and [Windows security events](https://imgur.com/F6w8b98.png).
- Enrichment and processing — [geolocation API](https://imgur.com/H2qlWd5.png), [PowerShell event processing](https://imgur.com/vwBGfVz.png), and [generated custom log](https://imgur.com/BVv2BEp.png).
- Ingestion and field extraction — [custom log ingestion](https://imgur.com/jgVateF.png), [custom log fields](https://imgur.com/ADphsax.png), [field extraction part 1](https://imgur.com/Yvfq1Ny.png), [field extraction part 2](https://imgur.com/JMbqjg9.png), and [enriched log data](https://imgur.com/jG4WSkP.png).
- Analysis — [log query](https://imgur.com/CRGfvCw.png) and [Sentinel geographic visualization](https://imgur.com/L4BeSkJ.png).

The Azure environment is no longer active. The screenshots preserve the historical implementation walkthrough; this repository documents a portfolio lab, not a live monitoring service. No attack-prevention or incident-response effectiveness metrics are claimed.

## Lessons Learned

- Windows event data can be processed and enriched before centralized analysis.
- Custom logs need structured fields to support useful querying and visualization.
- Geolocation adds investigative context but cannot establish a person's identity or precise location.
- Exposing cloud-hosted RDP has operational risk; production management access should be restricted and protected.
- A visualization supports investigation but does not, on its own, confirm compromise.

## Next Steps

- Add the PowerShell processing script and representative sanitized sample records if they can be shared safely.
- Document the custom schema, ingestion assumptions, and example queries so the workflow can be reproduced.
- Extend the case study with alerting and response validation only if those capabilities are implemented and documented.
