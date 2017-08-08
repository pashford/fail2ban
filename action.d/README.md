# fail2ban/action.d

This repository contains some Fail2Ban actions and filters that I use on my AWS t2.micro instance running Amazon Linux.  Fail2Ban os an open-source project designed to search log files for Failed (or bad) connection attempts and Ban the source IP.  The ban can be temporary or permanent.

These files are all for Fail2Ban version 8 on Amazon Linux 4.9 (based on CentOS 6).

This is the 'action.d' directory and contins custom actions.

blacklist.conf
	This file is based on the work of Mitchell Krog
	(https://github.com/mitchellkrogza/), specifically
	his Fail2Ban Blacklist Jail project.

	It has been updated to work in the above desctibed
	environment.  Also, reporting off-site has been
	disabled.