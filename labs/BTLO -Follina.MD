# Follina (CVE-2022-30190) — BTLO Challenge
**Date:** 16 May 2026
**Platform:** Blue Team Labs Online
**Category:** Incident Response
**Difficulty:** Easy
**Points:** 10

## What was the scenario?
Analyzing and reseaching a sample of a new RCE (Remote Code Execution) vulnerability

## Tools I used
*Virustotal
*Malwarebazaar
*Any.run
OSINT

## What I found
The malware was a threat used to exploit MS Word. Opened Files above 4096 bytes triggered an html payload from an external server. 
It would then silently try to kill Microsoft Support Diagnostic Tool (msdt.exe). 
In my IOCs (Indicators of Compromise);
*SHA1 hash of the sample was 06727ffda60359236a8029e0b3e8a0fd11c23313
*The malicious URL it contacted was https://www.xmlformats.com:443/office/word/2022/wordprocessingDrawing/RDF842l.html
*The hosting service was xmlformats.com

## What was tricky
I was working with the real Follina Malware and needed to be very careful not to infect my system. 
I uploaded the zip file to VirusTotal but VirusTotal couldn't give me the details i needed as the zip file was password protected.
I ended up using Malwarebazaar with tag:follina, looked for the closest date to the one in Virustotal and used the details there. 
I had a problem with the the name of the XML file that is storing the extracted URL and the MITRE technique being T1059 instead of T1203 
as it met the definition of T1203. 

## What I learned
*Chrome is good at detecting malicious files. Had to for it to download.
* Using a dirty Virtual machine when working with suspicious zipped files.
* There are online sandboxes and threat intelligence and multi-engine malware analysis tool like any.run i can use if analyzing any thing i don't trust.
*VirusTotal can help find hashes, behaviours such as the MITRE ATT&CK Tactics and Techniques.

## MITRE ATT&CK
T1059 - Command and Script  Interpreter
T1203 - Exploitation for Client Execution  (personal opinion)

### RESULTS
