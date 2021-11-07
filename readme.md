# codepath_homework

<img src='/DESU-Logo.png' height="auto" width="720"/>

<h2>Assignment 9 - Pentesting Live Targets</h2>

For this assignment, we were asked to "hack" into a live webservice using some of the methods that we've learned so far. In particular, it asked for us to perform the following hacks

<ul>
	<li>CSRF (Cross-Site Request Forgery)</li>
	<li>IDOR (Indirect Object Reference)</li>
	<li>Session Hijacking/Fixation</li>
	<li>SQLi (SQL Injection)</li>
	<li>Username Enumeration</li>
	<li>XSS (Cross-Site Scripting)</li>
</ul>

#
<h2>Exploit in _: CSRF</h2>

#
<h2>Exploit in Red: IDOR</h2>
On the public site under the section "Finding a salesperson", when you click on a sales person it gives the sales person info back, however the url has a queryStringParameter that denotes the id of a salesperson. Specifically, there is one that's missing from the list and it's id #10. When putting it into the other 2 sites, it just takes us back to the sales person page however on the Red, it loads a page that isn't public.

#
<h2>Exploit in _: Session Hijacking/Fixation</h2>

#
<h2>Exploit in Blue: SQLi</h2>
On the public site under a sales person, if you input a single quote, you get a database query error. On the other sites, it sanatizes the single quote.

#
<h2>Exploit in Green: Username Enumeration</h2>
Depending on the username inputted. If you inspect the element where it tells you "Login was unsuccessful", the class of the span element will tell you if it "failed" or if it was a "failure". When putting in a valid username, it says "failure" so we can denote that failure means the username exists

This is not good as someone could use that information to get a valid admin username then use something like SQLi to login as an admin.

#
<h2>Exploit in Green: XSS</h2>
XSS occurs in the feedback section on the public site. When you go to submit the feedback, you can insert a javascript with the proper tags. On the admin side, when you go to look at the feedback, the script will execute. 

This is not good as someone can get login credentials or some sort of key information.