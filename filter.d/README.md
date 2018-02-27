# fail2ban/action.d

This repository contains some Fail2Ban actions and filters that I use on my AWS t2.micro instance running Amazon Linux.  Fail2Ban os an open-source project designed to search log files for Failed (or bad) connection attempts and Ban the source IP.  The ban can be temporary or permanent.

These files are all for Fail2Ban version 8 on Amazon Linux 4.9 (based on CentOS 6).

This is the 'action.d' directory and contins custom actions.

apache-403.conf
	In a properly configured server, critical data
	requires authentication.  Hackers can probe the
	site, looking for possible holes.  They should be
	blocked before they can get very far in the scan.

apache-404.conf
	Many attacks consist of dozens of requests to
	the server for files that can be used as a path
	to compromising the system.  They should be
	blocked before they can get very far in the scan.

apache-masscan.conf
	The Masscan tool is an internet scanner that was
	created by a "security expert" to quickly scan the
	Internet for ports accepting connections.  While
	it was intended to be a security tool, it's a
	hacker's delight.  A scan by this tool can be
	considered to be a precursor to an attack.  When
	received, we block the source IP.

apache-pushdo.conf
	This filter blocks crap from Pushdo clients as
	they try to obfuscate communications with their
	C&C servers, to avoid location of those C&C
	servers by the use of Traffic Analysis.  Blocking
	these requests forces the client to select another
	IP address to use to hide the C&C server, which
	simplifies the process of locating the C&C server.

blacklist.conf
	This file is based on the work of Mitchell Krog
	(https://github.com/mitchellkrogza/), specifically
	his Fail2Ban Blacklist Jail project.  It has been
	updated to work in the above desctibed environment.
