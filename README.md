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

Find out the ip address of the attackers system.

## OUTPUT:

![EXPT 5 1 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/e40df7c1-bc88-44d6-bc17-ab4df831e450)

Invoke msfconsole:

## OUTPUT:

![EXPT 5 2 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/d6c4219f-1abf-468e-94fd-33dba9e1a2b4)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![expt 5 3 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/0930ab64-0b0b-4b46-89d9-74851fa25112)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![EXPT 5 4 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/50aa87b5-d5b7-4cec-bdd3-dd42e933929d)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![EXPT 5 5 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/f42404df-bf5c-4bf7-bf84-201e3712afde)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![EXPT 5 6 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/bb4ab4d9-eaf8-4c46-929b-0a860e1feffc)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![EXPT 5 7 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/1d1b1830-2ec9-4b37-a798-5c218c4450e9)

The info command provides information regarding a module or platform.

## OUTPUT:

![EXPT 5 8 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/36ca4681-8947-45b6-bd29-cccbeb3f843b)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

## MYSQL ENUMERATION:

                Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan 
                the MySQL database at 3306 port.

db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:

![EXPT 5 9 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/2e0d0b84-71f7-4905-a42d-d9281adfc3a2)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![EXPT 5 10 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/35bce4cc-660e-473a-96c4-32b46703442d)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![EXPT 5 11 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/5c15b119-a600-4cd1-ad98-81f6ffe5cf66)

Use the set rhosts command to set the parameter and run the module, as follows:

![EXPT 5 12 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/caa4e2f0-21dc-4b0c-84d1-4d1b47a6dd26)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![EXPT 5 13 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/3dbe79aa-f888-4a73-97cb-ede8cb15c012)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![EXPT 5 14 EH](https://github.com/22008686/Metasploit-for-reconnaissance/assets/118916413/119bb7b5-a6f0-443a-aa4f-884fc5796560)

## RESULT:

The Metasploit framework for reconnaissance is examined successfully.







