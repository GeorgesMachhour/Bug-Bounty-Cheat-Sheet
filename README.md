# Bug-Bounty-Cheat-Sheet
---

**Subdomain Hunting:**

- `sublist3r -d website.com`
- `knock domain.com`
- `crt.sh` (Website)

---

**Learning Hacking:**

- **Resource:** HackThisSite (Website)

---

**Best Vulnerability Scanners for Kali Linux/Parrot OS:**

1. **Nikto:**  
   `nikto -h https://hostname.com`

2. **Uniscan:**  
   - `uniscan -u https://hostname.com`  
   - `uniscan -u https://hostname.com -qweds`

---

**Gathering Emails of a Particular Domain:**

1. **TheHarvester:**  
   - `theharvester -d tesla.com -b all`  
   - `theharvester -d tesla.com -b google`

2. **Hunter.io** (Website)

---

**Exploiting CSRF Vulnerability (Account Takeover):**

- **Resource:** DVWA CSRF Tutorial

---

**Performing Bruteforce Attack using Burpsuite:**

- **Resource:** DVWA Tutorial

---

**Directory and File Hunting:**

1. **Dirb:**  
   `dirb https://www.tesla.com`

2. **FFUF:**  
   ```
   apt-get install golang
   go get github.com/ffuf/ffuf
   cd go/bin
   ls
   ./ffuf -w /root/Tools/dictionaries/starter.txt -u https://www.tesla.com/FUZZ
   ```

3. **Dirbuster**

---

**NMAP Tutorial:**

1. **Find All Devices on a Network:**
   - `nmap -sn 10.0.0.*`
   - `nmap -sn 10.0.0.0/24`
   - `arp-scan -l`

2. **Scan a Specific Machine:**
   - `nmap 10.0.0.4`

3. **Version of Ports:**
   - `nmap -sV 10.0.0.4`
   - `nmap -sV -p21,22 10.0.0.4`
   - `nmap -sV -p- 10.0.0.4`

4. **No Ping for Websites Forbidding Ping Requests:**
   - `nmap -sV -Pn`

5. **Service Scan:**
   - `nmap -sS 10.0.0.4`

6. **Operating System Scan:**
   - `nmap -O 10.0.0.4`

7. **All Scan (Targeting Specific or All Ports):**
   - `nmap -A -p21 10.0.0.4`  
   - `nmap -A -p- 10.0.0.4`

8. **Save Scan Results to a TXT File:**
   - `nmap -A -p21 -oN /root/Desktop/nmap-port21-scan.txt 10.0.0.4`

---

**Creating Password Wordlists:**

1. **Crunch:**
   - `crunch <min> <max> option`
   - `crunch 3 4 abcd -o wordlist-crunch.txt`
   - `crunch 10 10 1234567890 -t georges@@@ -o wordlist-georges.txt`

2. **Cupp (Clone from GitHub):**
   - `./cupp.py -i`  
   - Then follow the prompts...

--- 

**Hydra Bruteforce:**
**Commands:**
   - `hydra -l msfadmin -P password.txt 10.0.2.6 ftp` (Specified username as msfadmin,used 10.0.0.26 as IP address and password.txt as wordlist)
   - `hydra -L users.txt -P password.txt 10.0.2.6 ftp` (Specified wordlists for both username and password)
   (ftp is the selected service of the target open port )
   - `hydra -L users.txt -P password.txt 10.0.2.6 ssh -V` (ssh instead of ftp if the port service is ssh, -V for verbose)
   after intercept on burpsuite:
   - `hydra -L users.txt -P password.txt 10.0.2.6 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed" ` 

---

**Web parameter tampering attack and Reflected XSS attack using Burpsuite:**
You can find online tutorials...

---

**Google Dorking:**

- 'site: tesla.com ' (Google search results are just related to the website tesla.com)
- 'site: tesla.com filetype:txt ' (Search results will show the text files of tesla.com)
- 'inurl:tesla ' (searches for web pages that have "tesla" in their URL.)
- 'intitle:index ' (searches for web pages that have "index" in their title.)
- 'intitle:index site:tesla.com ' (earches for web pages on the Tesla website that have "index" in their title.)
- 'related:hacking' (searches for web pages that are similar to or related to the topic of "hacking.")
Check https://www.exploit-db.com/google-hacking-database for more...

---



