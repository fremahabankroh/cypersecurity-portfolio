# The Report — BTLO Challenge
**Date:** 17 May 2026
**Platform:** Blue Team Labs Online
**Category:** Security Operations
**Difficulty:** Easy
**Points:** 10

## What was the scenario?
Read a Threat Report from 2022 and suggest useful outcomes for 
intel gathering in a newly established SOC.

## Tools I used
Pdf Reader

## What I found
*There are bodies that compile detailed information on threats

*Threat groups like Yellow Cockatoo and Gootkit abusing SEO, Fancy Lazarus involved in Triple 

*Extortion Ransomware, Conti using crimeware like Qbot and Bazar for initial access.

## Key IOCs and Threat Intelligence Extracted

| Type | Value | Context |
|---|---|---|
| Vulnerability | Log4Shell | Java logging supply chain attack 2021 |
| Vulnerability | ProxyLogon | Microsoft Exchange Server exploit |
| Vulnerability | ProxyShell | Microsoft Exchange Server exploit |
| CVE | CVE-2021-34527 | PrintNightmare — RCE + SYSTEM privileges |
| Threat Actor | Gootkit, Yellow Cockatoo | SEO poisoning for initial access |
| Threat Actor | Fancy Lazarus | Triple extortion ransomware + DDoS threats |
| Malware | IcedID, Bazar, Qbot | Conti ransomware precursors |
| MITRE | T1059 | Affected 50%+ of customers |
| Process IOC | wscript.exe → powershell.exe | Malicious JS execution detection |

## What was tricky
Understanding how windows executed files is very neccessary to properly know
"what process launched this?"

## What I learned
* How to read indusrey threat report

*cmd.exe, wscript.exe and cscript.exe are not the same.

*Detection rules can be written in the SIEM to give specific alerts on process used like "process == powershell.exe
parent_process == wscript.exe
command_line_includes (iex || invoke || invoke-expression)". Here parent process is the process that 
launched another process called "child process"

*VulnNickname is for humans to easily pronounce and ID String is to track the malware.

*Triple Extortion Ransomeware


## MITRE ATT&CK
Discovered a new technique ID - T1059

### Results
<img width="968" height="1184" alt="Screenshot 2026-05-17 at 1 11 51 PM" src="https://github.com/user-attachments/assets/e65e8c55-a370-478c-9eb3-ea1df3e59ae5" />
