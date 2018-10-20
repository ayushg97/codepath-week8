# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi)

We use the provided sql in the hints and set it as the id. For blue, it returns a result as it is not sanitized. However, for red and green the sanitation leads to a redirect as shown in the gif. Instead of an id number, you put 
' OR SLEEP(5)=0--' . Which results in this url. When accessed, it will return Daron Burke of id=1.

https://35.184.88.145/blue/public/salesperson.php?id=%27%20OR%20SLEEP(5)=0--%27

![](https://github.com/ayushg97/codepath-week8/blob/master/sqli.gif)

Vulnerability #2: __________________


## Green

Vulnerability #1: Username Enumeration

When the username exists, the style of the "Log in was unsuccessful." text is of class "failure".
When the username does not exist, the style of the text is of class "failed".
This can be used to determine whether or not a username exists in the database, and is a form of enumeration.
The mistake the developer made is creating custom styling based on the type of login error.

![](https://github.com/ayushg97/codepath-week8/blob/master/usernameenumeration.gif)

Vulnerability #2: __________________


## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)

You can access a salesperson by their id parameter in the url. The two people, Lazy Lazyman and Testy McTesterson are not viewable on the public pages. However, they can be directly accessed on the red website. The blue and green websites redirect the user back to the list of salespeople if they are lacking the proper permissions.

![](https://github.com/ayushg97/codepath-week8/blob/master/idor.gif)

Vulnerability #2: __________________


## Notes

Describe any challenges encountered while doing the work

