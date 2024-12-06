---
layout: post
title: How to not fuck up a technical interview - Part 2
categories: Interview
---

TECHNICAL KNOWLEDGE

Every organization is different, so every interview process is different. Some organizations might talk to you for 15 minutes and decide that's enough- others decide to waste a massive amount of time and energy scheduling interviews that number dangerously close to two digits (another topic for another day). That being said, there are some general themes that an old hand with a bit of grey in their beard can attest show up consistently when you interview for infosec jobs. One of these themes is what I like to call the 'Technical Interview'.

At some point in the application process, you will most likely be tested on your technical acumen. How intensive, and what content is in these interviews can vary as widely as all the specializations running around in the infosec space. If you apply to a red-team/pentesting position, chances are that they'll ask you questions regarding your ability to compromise computer systems. Be ready to talk about CTFs, certifications, and the like.

For the purposes of this post, I'm going to describe a general 'Cyber Security Analyst' position. The ideal candidate would be someone who takes initiative, and has a solid understanding of general IT & security fundamentals. Like I said in Part 1, we don't need an Ozzy-tier rockstar to join our team.

I'll outline some of the technical fundamentals I've seen lacking in candidates-

- Email Security (aside- infosec literature always harps on the fact that most security incidents of some kind have email based attack vectors as their root cause. So why can't propesctive candidates fucking figure out that interviews may put priority on email related scenarios & questions? Take a ride on the fucking clue bus.)
- Incident Response
- IT/Security Tool Stacks

Let's get deeper than Ron Jeremy on these topics, so you fuckers can respond to technical questions without muttering some made-up BS, or drop a patented 'idunno'.


1. EMAIL SECURITY

	Jesus. Mary. And Joseph. I won't repeat my aside above, but suffice to say that candidates get blindsided like Eric Lindros when you ask them about email. Most candidates are somewhat able to identify malicious content based on the body or attachments of an email. Great. You passed L1 SOC basics. I expect an infosec analyst worth their salt to understand more than that.

	1A. EMAIL HEADERS

		Do people even know what email headers are? Just knowing what these are, and vaguely what they mean will make you a much stronger SOC/Security analyst candidate. Email headers are metadata. If you don't know what metadata is, fuck off back to school. If you're a SOC analyst who has no fucking clue about email headers, either whoever taught you to do SOC is a fucking moron, or you suck at your job. Or both.

	1B. AUTHENTICATION FRAMEWORKS

		SPF, DMARC, DKIM (among others, these are the 3 I ever hear about). These are good to know. Not all organizations have email authentication deployed to the degree they'd like, so the importance of these isn't always paramount. Often candidates don't even know these acronyms, or have a general idea where they fit in the technology stack. This isn't rocket science, fucking figure it out people.


2. INCIDENT RESPONSE

This isn't as technical as my points above- but I've found candidates that seem to struggle to understand how incident response processes should go. As an 'eXpErIeNcEd PrOfEsSiOnAl' I find this intuitive. NIST divides the incident response process into four sections (https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-61r2.pdf)-
		
	- Preparation
	- Detection & Analysis
	- Containment, Eradication & Recovery
	- Post-Incident Activity

For fucks sake, understand this. Know what activities fall under which category. Again, this isn't rocket science. For example-
	
	- Preparation: Deploying EDR agents to workstations & endpoints.
	- Detection: EDR agent flagging a suspicious file and reporting the incident to the mothership.
	- Analysis: A SOC jockey going into the EDR console to analyze logging & activity related to the incident. Ideally the Root Cause of the incident is found.
	- Containment: Said SOC jockey finding the suspicious activity significant enough to action the alert. Containment actions are informed by what is discovered in the analysis phase. 
	- Eradication & Recovery: Our SOC jockey carries out remediation action (or foists the burden to some IT nerd) to remove the suspicious files from the device, or reimages the device and returns it to the user.
	- Post-Incident Activity: SOC jockey brings up the incident in a meeting with their boss to exchange feedback. Their boss is either an asshole that scolds the SOC jockey over a minor error, or their boss is a moron who doesn't understand security, or even computers really, and just prays that nothing of substance happens to expose them as the moron they are on their corporate ladder climbing journey. In rare cases, the boss is someone with actual subject matter expertise, and isn't a complete douchebag that only became a manager so he could shit on junior analysts that you can't reasonably expect to do better. In this rare case, valuable lessons are learned, and the SOC is better prepared to handle the next incident.

For a job where you may be expected to carry out incident response (so most of them in infosec), be prepared to describe an incident response in detail. Expect whoever's interviewing you to give you an unusual scenario, so as to fool the kind of moron that spends all their time on rote memorization of different incident response scenarios. Again, Google is Google, you are an analyst. Use your goddamned brain. Identities. Workstations. Servers. Applications. On-Prem Networks. Cloud Environments. Know the fundamentals of all of these, because if someone throws you a cloud incident response scenario, and you know fuck-all about cloud, you're completely fucked. That segues me nicely to my last point...


3. TOOL STACKS

People seem to struggle with how the pieces fit together in the technology stack of an organization. You may think- 'but if you're hiring junior people, you can't really expect them to understand tech stacks in depth'. I would not argue that. ... Actually I might argue that just to be annoying and play devil's advocate. Only problem- I see this happen with supposedly experienced people. 

If you're given an interview scenario where a user entered their credentials into a phishing page, and then an attacker logged into their account remotely, please, for the love of god, don't say you'll isolate the user's device as remediation. This indicates to me that you're just BSing any remediation action you've heard of that sounds nice. You will not bullshit your way past me. I will stop you like Marty Brodeur. 

Suggest realistic remediation action. Take into account user impact. No, you won't be allowed to isolate the org's ERP. Containment/remediation of critical systems MUST be done in collaboration with the technical owner of the system, and remember that the business owns the risk.

I've found this to be less of an issue, but understand security tool stacks. Know the vendors. Know the use cases. There is also offensive security tooling- you don't need to know everything, but know what the well-known tools are (mimikatz? metasploit? bloodhound?), know what they do, and know what to do to detect & respond to uses of offensive security tooling. If I ask you 'Your SIEM fires an alert that says it discovered bloodhound activity from an uptick in LDAP queries from some IP. What do you do?', your response better not be 'Bloodhound is a breed of dog, silly. And what's LDAP? They didn't cover that in my 90 day SOC analyst bootcamp'.

	
That's not everything in terms of fundamentals, but this post is getting long. Remember that you're not expected to know absolutely everything by heart. But you are expected to have an understanding of how information systems work, and how hackers compromise information systems for their personal gain. If you have no clue about how this works, please consider a different career.

Fuck right off.
