# Breach Analysis — CPUID STX RAT

**Date:** April 9–10, 2026  
**Incident:** CPUID website compromised for <24h, download links replaced with trojanized installers.  
**Malware:** STX RAT via DLL side-loading (CRYPTBASE.dll).  
**Impact:** >150 victims across individuals and organizations in multiple sectors.  
**MITRE ATT&CK:** Initial Access (T1189), Execution (T1574), Defense Evasion (T1497), Collection (T1056), C2 (T1071).  





**What happened:**  
In April 2026, CPUID’s official website was compromised for less than 24 hours.  
Attackers replaced the download links for CPU‑Z and HWMonitor with trojanized installers.  

**How it worked:**  
The malicious installers contained a signed executable plus a rogue DLL named *CRYPTBASE.dll*.  
This DLL used side‑loading to deploy **STX RAT**, a remote access trojan with infostealer and HVNC capabilities.  

**Impact:**  
More than 150 victims were affected, including individuals and organizations across multiple sectors.  
Most infections were observed in Brazil, Russia, and China.  

**Key takeaway:**  
This was a watering hole attack against a trusted software vendor, showing how supply chain trust can be abused.
