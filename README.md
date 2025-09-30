# Metasploit-for-reconnaissance
## NAME:DHARUNYADEVI S
## REGISTER NUMBER:212223220018
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

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system
## OUTPUT:

<img width="1062" height="529" alt="Screenshot 2025-09-29 111428" src="https://github.com/user-attachments/assets/d6d32d95-2147-45ec-b105-58d131664c48" />

Invoke msfconsole:
## OUTPUT:

<img width="1048" height="693" alt="Screenshot 2025-09-29 111443" src="https://github.com/user-attachments/assets/d10cc29f-7eda-48b6-b2d8-600bde0b6e7a" />

Type help or a question mark "?" or help to see the list of all available commands you can use inside msfconsole.
## OUTPUT:

<img width="1163" height="833" alt="Screenshot 2025-09-29 111501" src="https://github.com/user-attachments/assets/2a06bdc7-0087-4977-9249-3235dd2bc7e9" />

Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 10.0.2.15/24 -p1-1000

## OUTPUT:

<img width="828" height="214" alt="Screenshot 2025-09-29 111541" src="https://github.com/user-attachments/assets/20ead607-d464-44ee-8322-d8df64f0916e" />

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows.
msf > db_nmap 10.0.2.15/24

## OUTPUT:
<img width="948" height="824" alt="Screenshot 2025-09-29 111756" src="https://github.com/user-attachments/assets/f37e8503-f77c-477a-95f9-76add076a7a9" />

Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
## OUTPUT:
<img width="1164" height="828" alt="Screenshot 2025-09-29 112648" src="https://github.com/user-attachments/assets/9c904b69-6bef-48bf-a889-4eb316f7aee3" />

The info command provides information regarding a module or platform,
## OUTPUT:
<img width="1157" height="831" alt="Screenshot 2025-09-29 112708" src="https://github.com/user-attachments/assets/89785615-33c4-4c54-8973-b9d70ad05bb2" />

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:

<img width="1162" height="322" alt="Screenshot 2025-09-29 112725" src="https://github.com/user-attachments/assets/e09e4ac1-8fc7-4ded-80b9-4f8be02ba32e" />

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database.
search type:auxiliary mysql
## OUTPUT:
<img width="1166" height="834" alt="Screenshot 2025-09-29 112743" src="https://github.com/user-attachments/assets/992692ec-ccdb-4214-8635-657997d2ea7d" />

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details.
use 11
Or:
use auxiliary/scanner/mysql/mysql_version
## OUTPUT:
<img width="722" height="219" alt="image" src="https://github.com/user-attachments/assets/18bf7c6f-9b2f-4b4c-947e-fcfa3b272bac" />

Use the set rhosts command to set the parameter and run the module, as follows:
## OUTPUT:
<img width="724" height="289" alt="image" src="https://github.com/user-attachments/assets/6dc2dad7-2b66-4dfd-a2d0-9e6861984147" />

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT:

<img width="724" height="289" alt="Screenshot 2025-09-30 091328" src="https://github.com/user-attachments/assets/6ff2fe3b-b903-4764-ac04-185d6f08140c" />

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:
set PASS_FILE /usr/share/wordlistss/rockyou.txt
Then, specify the IP address of the target machine with the RHOSTS command.
set RHOSTS <metasploitable-ip-address>
Set BLANK_PASSWORDS to true in case there is no password set for the root account.
set BLANK_PASSWORDS true
## OUTPUT:
<img width="1105" height="307" alt="Screenshot 2025-09-29 113341" src="https://github.com/user-attachments/assets/6f8b6b1f-c868-4f75-b53a-65b0f76b5371" />


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
