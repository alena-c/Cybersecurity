# Project 8 - Pentesting Live Targets

Time spent: **6** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: __________________

Description: 

<img src="blue-vuln1.gif">

Vulnerability #2: __________________

Description: 

<img src="blue-vuln2.gif">

## Green

Vulnerability #1: __________________

Description: 

<img src="green-vuln1.gif">

Vulnerability #2: ___________User Enumeration_______

Description: If the log-in was not successful, regardless of the reason, the users is supposed to be notified about it with a bolded message/marker: "Log in was unsuccessful". That's the default behavior on both red and blue targets. The green target, although, has a vulnerability whicht makes the the user distinguish the login faliure due to the wrong username vs the wrong password. This vulnerabilty is due to the typo in its html code: under the <span> tag, the class attribute has a value "failed" instead of the correct "faliure". This makes the text prompt appear in bold if the username is correct (wrong password) and not in bold when the username is wrong. The gif shows how this issue can be fixed by inspecting the element.

<img src="green-vuln2.gif">


## Red

Vulnerability #1: 

Description: 

<img src="red-vuln1.gif">

Vulnerability #2: ___________Cross-Site Requiest Forgery (CSRF)_______

Description: 

<img src="red-vuln2.gif">


## Notes

Describe any challenges encountered while doing the work


## License

Copyright 2020 Alena Chernenko


