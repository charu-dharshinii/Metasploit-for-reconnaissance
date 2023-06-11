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

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/1f538f40-f876-4459-8677-8dfbac405ba8)

## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/953379bc-27c4-4e87-9702-3316dfb7c3ef)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/7f276d8f-8564-47aa-be92-6777dd9474db)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/c0cf7ce9-74cc-4c75-8e07-dd3785c52086)

 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/c3e81fb0-1f4d-4243-b8b0-8886a01ee24e)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/99aca0dd-3fd0-4380-904c-773475effa74)

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/0cb3f03c-c4c4-4b80-96b7-fdd4b3645f8b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/616d4518-88b6-4b8f-80eb-c0c6e16df08a)

The info command provides information regarding a module or platform
## OUTPUT:

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/09a5a034-e2b2-4100-a600-2994f2892c99)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/4357ed6f-62a5-4adb-ad5c-fee8dffdfd7b)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/5dd2edca-fd00-45b3-956e-8dd5fe41465a)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/8f9525da-1a5b-4498-8f41-8ef701adb2d9)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/57882379-ea28-4349-a3dc-ecea7bb10dea)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/7234a9cb-8baf-485c-b743-f6c6250dded8)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/gokul-sureshkumar/Metasploit-for-reconnaissance/assets/121148715/752e39b3-a594-4e46-b60e-1bb7a0ff9d5d)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
