# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system


## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/ed385681-96e5-4c9c-bdc6-146f5cb2a629)


## Invoke msfconsole:
## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/ffc1072b-7dda-4fc7-9c40-ca50d93e9ca1)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/8c8327ac-42f5-4752-9fe9-dec15e604a01)


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/2faf3802-3df7-4e46-bb5d-246d0465f378)


 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/83de43b7-09c7-43a8-8332-6f0b0cea0c46)


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/d6df6d38-1548-4eb1-9820-bda25c59dd1d)

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/8909e9e6-a9eb-4347-8ea4-c8b1da7122eb)


Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/89880f7b-01d3-46fa-88a2-cbfc5e9dcc5c)


The info command provides information regarding a module or platform

## OUTPUT:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/6138c0c3-cbd5-4054-a871-66d56fc3e54c)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/70839068-4079-4dac-a4c0-df075e2625d8)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/fd3c4cf5-9f9e-40ef-a6a1-a0e5e0a6e4d1)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/d0e072b9-6019-468f-9174-cb641311642b)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/425ec3fd-7813-447d-9199-3256bf516afd)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/aa3be0b6-ff53-4399-be8f-24577edc5452)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/charu-dharshinii/Metasploit-for-reconnaissance/assets/130828943/238526b9-73b6-4c77-b607-ae5917149220)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
