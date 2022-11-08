# Pen Testing Live Targets

Time spent: **7** hours spent in total

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

Vulnerability #1: Session Hijacking/Fixation

Description: Here I logged into the blue site on Google Chrome with the pperson credentials and then obtained the php sesion id. After, I then openeded up the php session id url to change the session id on Safari to that of the one on Google Chrome. Lastly, I accessed the URL for the blue site, and upon doing so gained access to the pperson login screen due to stealing their php session id.

<img src="[blue-vuln1.gif](http://g.recordit.co/L1SAOXwLX0.gif)">

Vulnerability #2: SQL Injection

Description:Here I accessed the salespeople library and selected Samuel Hunter. After, I selected the url and added "' OR SLEEP(5)=0--'" this allowed me to gain access to the user Daron Burke. This means the URL responds to SQL input which means the developers did not sanitize the URL input.

<img src="[green-vuln1.gif](http://g.recordit.co/tbHm7SO5Lv.gif)">


## Green

Vulnerability #1: Username Enumeration

Description:By inspecting the HTML, I am able to find the message that indicates the error in the login process. However, there is a difference in how the error message is printed. For a username of pperson, which is an established login, the error message reads "failure". On the other hand, for a username of moo, which isnt an established login, the message reads "failed". From this, one can infer that if a username is real, it will show failure and if a username isnt real it will show failed, which is valuable information.

<img src="[green-vuln1.gif](http://g.recordit.co/V2IEHFVPDU.gif)">

Vulnerability #2: Cross-Site Scripting

Description:By injecting JavaScript into the name field, one can then see that the "Contact us" page will accept scripts which is a big vulnerability. Upon sending the message, and clicking feedback, the XSS attack can be seen.

<img src="[green-vuln1.gif](http://g.recordit.co/JQOk4xsxHc.gif)">

## Red

Vulnerability #1: Insecure Direct Object Reference

Description: By changing the value of the value of the id from 5 to 11. One can access wht was originally private data. The user Lazy Lazyperson was not orignially seen on th epublic site which means injecting text into the url can bypass private access.

<img src="[red-vuln1.gif](http://g.recordit.co/1Mi5uK18AK.gif)">


## Notes

Describe any challenges encountered while doing the work
