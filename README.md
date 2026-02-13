**View project without downloading ➜** https://annsshanto.github.io/Mr-Robot-Walkthrough/



**📌 Project Overview** 

This project documents a step-by-step penetration testing walkthrough of the Mr Robot vulnerable machine.
The objective is to perform reconnaissance, exploitation, and privilege escalation to obtain three hidden keys.


## The attack methodology follows standard ethical hacking phases:
-Reconnaissance 
-Enumeration 
-Exploitation 
-Privilege Escalation

## 🧰 Tools Used
- Nmap  
- Gobuster  
- Base64 Decoder  
- Netcat  
- LinPEAS  
- GTFOBins


## 🧠 Attack Methodology

### 1. Reconnaissance
- Performed Nmap scan on target IP  
- Discovered port 80 (HTTP) open  

### 2. Enumeration
- Directory brute-forcing using Gobuster  
- Found: /robots.txt  
- WordPress login page (/wp-login.php)  
- First key obtained from robots.txt  
- Found Base64 encoded credentials inside /license  

### 3. Credential Discovery
- Decoded Base64 string  
- Extracted username and password  
- Successfully logged into WordPress admin panel  

### 4. Exploitation
- Identified vulnerable WordPress version  
- Injected PHP reverse shell code into 404 template  
- Started Netcat listener  
- Triggered reverse shell via browser  

### 5. Horizontal Privilege Escalation
- Located MD5 hash password file  
- Cracked hash using online hash cracker  
- Switched to robot user  
- Retrieved second key  

### 6. Vertical Privilege Escalation
- Uploaded and executed LinPEAS
-Found Nmap with SUID permission
-Used GTFOBins technique to exploit Nmap
-Gained root access
-Retrieved third key
