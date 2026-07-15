# Practice 1: Failed Login
Jul 27 08:10:01 sshd: Failed password for root from 203.0.113.5
Jul 27 08:10:05 sshd: Failed password for root from 203.0.113.5
Jul 27 08:10:10 sshd: Failed password for root from 203.0.113.5

* Questions:
Which IP is suspicious? 203.0.113.5
Which account is being targeted? root
What attack does this resemble? It a brute force attack trying to login into system
What would you investigate next? Check the log activity and the user activity if find something suspicious toward ip would inform the lead and documentation

# Practice 2: Password Spraying
Jul 27 09:00:01 sshd: Failed password for alice from 203.0.113.20
Jul 27 09:00:03 sshd: Failed password for bob from 203.0.113.20
Jul 27 09:00:05 sshd: Failed password for admin from 203.0.113.20
Jul 27 09:00:07 sshd: Failed password for guest from 203.0.113.20

* Questions:
What attack is this? Password spraying where the attacker ip same trying to get into guess password for multiple account if get the chance guessing password 
Why is it different from brute force? In brute force attacker tries to guess one account password where as password spraying tries to get mutliple account tries frome set of password list if get would be jackpot for the attacker and for the system would big comprimse

# Practice 3: DNS Logs
Laptop01 queried google.com
Laptop01 queried microsoft.com
Laptop01 queried abc123-malware.xyz

* Questions:
Which domain is suspicious? Laptop 01 queried abc123-malware.xyz is suspicious domain
What would you check? Check the domain link totalvirus to check if safe or not
Which threat intelligence source could help? Totalvirus tool and unsafe website or page redirected can be comprise the device or the system 

