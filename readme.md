# codepath_homework

<img src='/DESU-Logo.png' height="auto" width="720"/>

<h2>Assignment 10/11 - HoneyPot</h2>

For this assignment, we were to create a VM instance via a cloud environment and deploy a honeypot so that we can catch hackers and get sensitive information from them. In a sense, we're hacking the hackers as security "professionals".

The service that we will be using as our honey pot is the <b>Modern Honey Network</b> which is an open source honeypot which is well supported, but also very basic for our usecase and to showcase what an acutal honeypot can do.

In terms of cloud provider, the guide followed <b>Google Cloud Platform</b> so I decided to follow that. Upon completion, this can also be easily setup in AWS (Amazon Web Services) or Microsoft's Azure Cloud Platform. Below will be GIFs on how I deployed the Modern Honey Network (Admin Console), The Dioanaea HoneyPot Deployment, and a screenshot of the database (copy of the source is included in the repository).

# <h2>MHN Admin Deployment</h2>
For Deploying the MHN Admin, I first had to create a VM instance with the ubuntu image. Also, I added some firewall rules so that the application would run the way it's supposed to. Specifically, I had to add the ports <b>80</b> (HTTP), <b>3000</b> (Honeypot), and <b>10000</b> (HoneyPot Feeds) because they allowed for certain parts of the application to be accessed from anywhere. Once that was complete, I ssh'd in and ran the install script to run the app. Once it was completed, I was able to access the app (with my admin credentials) via the public ip of my instance.

Here are some gifs of some of the steps
<p align="center">
		<img src="/img/start-instance-mhn.gif" height="auto" width="80%">
		<br/>
		<span>Starting the MHN VM instance (<b>Google Cloud</b>)</span>	
</p>
<p align="center">
		<img src="/img/ssh-into-mhn-admin.gif" height="auto" width="80%">
		<br/>
		<span>SSHing into VM</span>	
</p>
<p align="center">
		<img src="/img/logging-in-mhn-admin.gif" height="auto" width="80%">
		<br/>
		<span>Logging into MHN Admin</span>	
</p>

# <h2>Dioanaea HoneyPot Deployment</h2>
Deploying the HoneyPot itself was very similar to the process of deploying the MHN Admin (Deploy the VM, add firewall rules etc.). The differences this time was we were allowing all TCP/UDP ports and we deployed the command given from the MHN Admin onto the HoneyPot VM in order to see who is hacking our HoneyPot on the MHN Admin side.

The following are some gifs of the process.
#
<p align="center">
		<img src="/img/start-instance-honeypot.gif" height="auto" width="80%">
		<br/>
		<span>Starting the Honeypot VM instance (<b>Google Cloud</b>)</span>	
</p>
<p align="center">
		<img src="/img/ssh-into-honeypot.gif" height="auto" width="80%">
		<br/>
		<span>SSHing into Honeypot Instance</span>	
</p>
<p align="center">
		<img src="/img/nmap-kali.gif" height="auto" width="80%">
		<br/>
		<span>NMap Attack on HoneyPot</span>	
</p>
<p align="center">
		<img src="/img/proof-nmap-attack.gif" height="auto" width="80%">
		<br/>
		<span>NMap Attack (Result)</span>	
</p>

# <h2>Database Backup</h2>
After I attacked the HoneyPot, I backed up the database using the command provided.

Here are some gifs of attacking the honeypot/backing up the database.
<br />
<a href="/session.json">Link to the database json file</a>
# <h2>Additional Honeypot Deployment</h2>
<code><b>For this one, I will be deploying to AWS because I didn't want to do the same thing again</b></code><br/>
I followed the same process as above, except with the AWS convention. The results are below.
#
<p align="center">
		<img src="/img/deploying-second-honeypot-aws.gif" height="auto" width="80%">
		<br/>
		<span>Creating the HoneyPot VM Instance</span>	
</p>
<p align="center">
		<img src="/img/honeypots.png" height="auto" width="80%">
		<br/>
		<span>MHN-Admin HoneyPot instances</span>	
</p>

