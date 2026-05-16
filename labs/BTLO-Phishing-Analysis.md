# Phishing Analysis — BTLO Challenge
**Date:** 16 May 2026
**Platform:** Blue Team Labs Online
**Points:** 10

## What was the scenario?
A user got a suspicious email and forwarded it to the SOC. 
My job was to dig into it and pull out useful information 
about where it came from and what the attacker was trying to do.

## Tools I used
* Thunderbird — to open and read the raw email file
* DomainTools WHOis — to trace who owned the sending IP
* URL2PNG — to screenshot the phishing page safely

## What I found
The tricky part was that the email was actually a bounce message 
* a delivery failure notice. The real phishing email was hidden 
inside it as an attachment. The attacker was pretending to be 
someone filling out a contact form, but buried inside was a link 
promising $6500 per day.

The email originated from IP 103.9.171.10, which traced back to 
a hosting company in Sydney, Australia — meaning the attacker 
rented a server to send from. The phishing page itself was 
hosted on Blogspot, a free Google platform.

By the time I investigated, the page was already taken down — 
but URL2PNG still had a cached screenshot showing the heading 
"Blog has been removed."

## What I learned
This was my first real SOC investigation. I learned that phishing 
emails aren't always obvious. This one was hidden inside what 
looked like a routine bounce message. Reading raw email headers 
to find the originating IP was new to me, and understanding how 
reverse DNS works to identify infrastructure was really useful.

## MITRE ATT&CK
* T1566 — Phishing
* T1583.006 - Attacker abused a free web service (Blogspot)
