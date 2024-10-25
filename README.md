# Building-a-SOC-at-Home

<h1>Building a SOC at Home</h1>

<h2>Description</h2>
In this lab, I utilized the Vultr cloud platform to build a SOC. The goal of this lab was to gain practical experience in working in a SOC. Though I currently work as a system and information assurance administrator, my passion is in cybersecurity. That being said, performing labs like this is a great way to gain the hands on knowledge required for the career field. The lab itself was straightforward. I went from the planning phase, to building alerts and dashboards, to finally creating a ticketing system. I set up an Ubuntu CLI to run the ELK stack, Windows Server 2022 to build domain clients, Ubuntu Server, Kali Linux to brute force domain clients, Ubuntu Fleet server, and a Mythic server for C2C. 
<br />

<h2>Tools and Systems Used</h2>
Windows Server 2022, Ubuntu CLI, ElasticSearch, Kibana, Logstash, Vultr, Mythic, Kali Linux, Crowbar, Microsoft Active Directory, Sysmon
<br />

<h2>Skills Learned</h2>
- Run Sysmon to log and aggregate data<br />
- ELK to build alerts and dashboards<br />
- Create Active Directory Forest, Organizational Units within the domain, and domain user accounts<br />
- Utilize Crowbar on Kali Linux to brute force remote connection on a domain user account<br />
- Show failed and successful logon attempts in ELK dashboard</b><br />


<h2> Overview </h2>
** This is not my own creation. I followed this lab from a series of videos by MyDFIR on YouTube** <br/>
This lab was extremely well done and helpful. I highly recommend this to anyone who is trying to get into Cybersecurity but doesn't have the hands on experience as a SOC analyst. Although on the job you may not be required to build the SOC from the ground up, doing so enforces the concepts and how the servers and applications communicate with each other. This lab, though very well done, does still require troubleshooting much as anything in IT and Cybersecurity does.  <br/>

This lab began with the planning process. I utilized draw.io to create a rough map and outline the IP scheme I would use. <br /> <br />
<img src="https://imgur.com/xn4Pmd3.png" />

This proved to be very helpful as a future reference through the project to remmeber how each machine would talk to each other. It is important to note that is not set in stone, as your progress through the lab you may want to make changes. As long as those changes are documented, there is no harm in it. <br />

The biggest part of the lab is the ELK stack. The SOC revolves around dashboards and alerts. It was incredible to see the geolocation of the SSH and RDP attempts on my VMs. In addition, I gathered the IP addresses, attempted user names and passwords, and timestamps. 

<br />

As the lab progressed, it turned into thousands of attempts on the machines. Not only did I create dashboards, but I set up alerts to associate with either failed ssh or failed RDP attempts. To demonstrate successful attempts, I set up a Kali box to brute force into the Windows machine using Crowbar. With the gathered credentials, I was then able to RDP into it and disable the firewall. This fell into the phases of the attack diagram I built first. <br />
<img src="https://imgur.com/uCSnFxA.png" />
<br /> <br /> <br /> <br />
Planning out the phases of the attack was great practice at thinking as an attacker and what the end goal is. For the C2 server, I set up a Mythic server to run Apollo as seen in the diagram. This allowed me to set up an agent on the victim's machine and gather information by executing commands from my Mythic server. 
<br /> <br /> <br /> <br />
<img src="https://imgur.com/hHygfAu.png" />
<br />
<img src="https://imgur.com/zBRCbba.png" />
<br />
<img src="https://imgur.com/vcwVHg1.png" />
<br />

After performing the attack, I went back on the blue team side and created alerts for successful RDP and SSH attempts. This displayed that being a cyber defender is about always improves the defenses. Attackers only need to get it right once, so we must always be learning and improving.  <br />

The next task was setting up the OsTicket system on an Apache server. The initial setup was not difficult, but I am currently working on getting the OsTicket API to work correctly with the webhook on Elastic. The test runs successfully, and the machines can ping each other, but tickets will not populate on my dashboard. Overall, this lab has been extremely helpful. My goal is to build this on a home server and use it to not only practice labbing but practically use it on my home network. I will cover the building and configuration of my home server in a future post. Thank you for reading. 
<br />
<img src="https://imgur.com/fO7UG0B.png" />
<img src="https://imgur.com/gu8b9Rr.png" />
<img src="https://imgur.com/XFsQliw.png" />
