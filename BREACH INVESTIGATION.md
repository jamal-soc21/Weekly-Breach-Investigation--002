Weekly Breach Investigation
Breach: CPUID Watering Hole Attack — April 2026

1. Executive Summary
In April 2026, CPUID’s official website was compromised for less than 24 hours.
Attackers replaced download links for CPU‑Z and HWMonitor with trojanized installers containing a rogue DLL (CRYPTBASE.dll).
The campaign deployed STX RAT, impacting over 150 victims across individuals and organizations in multiple sectors.

2. Attack Timeline
April 9, 15:00 UTC — Initial access via compromise of CPUID’s side API, malicious links injected.

April 9–10 — Trojanized installers distributed with signed executables + CRYPTBASE.dll payload.

April 10, 10:00 UTC — Breach discovered and mitigated; CPUID confirmed compromise publicly.

3. MITRE ATT&CK Mapping
Tactic	Technique	ID
Initial Access	Drive‑by Compromise (Watering Hole)	T1189
Execution	DLL Side‑Loading	T1574
Defense Evasion	Virtualization/Sandbox Evasion	T1497
Collection	Input Capture / Infostealer	T1056
Command & Control	Application Layer Protocol (HTTP)	T1071
Impact	Remote Access / Data Theft	T1537


4. Detection Opportunities
Log sources: Web proxy logs, endpoint EDR, DLL load events.

Detection rules:

Alert on unsigned DLLs named CRYPTBASE.dll.

Flag anomalous downloads from rogue domains.

IOCs:

Malicious domains: cahayailmukreatif.web[.]id, transitopalermo[.]com, vatrobran[.]hr

Payload: STX RAT with reused C2 infrastructure from prior FileZilla campaign.

5. Recommended Mitigations
Verify installer integrity via digital signatures before deployment.

Block known malicious domains and monitor outbound traffic to reused C2 servers.

Harden software supply chain by isolating download APIs and enforcing TLS validation.

Deploy EDR rules for DLL side‑loading detection.

6. Analyst Notes
This case highlights the risk of watering hole attacks even on trusted vendor sites.
The attackers reused infrastructure from a prior FileZilla campaign, which lowered their operational security and enabled rapid detection.
Further investigation should focus on strengthening vendor distribution channels, monitoring DLL side‑loading attempts, and improving supply chain resilience.
