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

- `site: tesla.com ` (Google search results are just related to the website tesla.com)
- `site: tesla.com filetype:txt ` (Search results will show the text files of tesla.com)
- `inurl:tesla ` (searches for web pages that have "tesla" in their URL.)
- `intitle:index ` (searches for web pages that have "index" in their title.)
- `intitle:index site:tesla.com ` (earches for web pages on the Tesla website that have "index" in their title.)
- `related:hacking` (searches for web pages that are similar to or related to the topic of "hacking.")
Check https://www.exploit-db.com/google-hacking-database for more...

---


**Top 10 hacking tools:**
- `nmap` (Network mapper for discovering hosts and services on a computer network.)
- `aircrack-ng` (A suite for wireless security auditing, focusing on WEP and WPA/WPA2 encryption.)
- `hydra` (A fast and flexible password-cracking tool that supports numerous protocols.)
- `BurpSuite` (An integrated platform for web application security testing.)
- `Metasploit` (A penetration testing framework that helps find and exploit vulnerabilities.)
- `WireShark` (A network protocol analyzer used to capture and inspect data packets in real time.)
- `hashcat` (A powerful password recovery tool that supports various hashing algorithms.)
- `JohnTheRipper` (A fast password-cracking tool that supports many encryption formats.)
- `SQLmap` (An automated tool for detecting and exploiting SQL injection vulnerabilities.)
- `acunetix` (A web application security scanner that detects vulnerabilities like SQL injection and XSS.)

---

**Free VPNs for you:**
- `Proton VPN`
- `Windscribe`
- `surfshark`
- `zsvpn`

---

**Surf anonymously with AnonSurf:**
AnonSurf is a tool used to route internet traffic through the Tor network, providing anonymity to users. It's primarily designed for Linux distributions like Parrot OS and Kali Linux, helping users maintain their privacy while browsing the web.

Built-in Commands for Parrot OS
In Parrot OS, you can use the following commands with AnonSurf:

- `anonsurf start ` Starts the AnonSurf service and routes traffic through Tor.
- `anonsurf stop ` Stops the AnonSurf service and restores normal internet connectivity.
- `anonsurf status ` Displays the current status of the AnonSurf service.
- `anonsurf restart ` Restarts the AnonSurf service.
- `anonsurf menu ` Opens a menu with additional options for managing AnonSurf.

Additional Commands for Kali AnonSurf
In Kali Linux, the commands may be similar, but here are some specific ones:

- `anonsurf start ` Start the AnonSurf service.
- `anonsurf stop ` Stop the AnonSurf service.
- `anonsurf status ` Check the status of AnonSurf.
- `anonsurf restart ` Restart AnonSurf.
- `anonsurf help ` Display help and usage information.

Link - `https://github.com/Und3rf10w/kali-anonsurf`

---


**Surf with proxychains:**
Proxychains is a tool that allows you to force any application to use proxy servers for its network connections. It can route traffic through multiple proxies, which can enhance anonymity and security.

To use **Proxychains** to hide your identity while browsing or using network applications, you can follow these steps:

### Basic Command

1. **Run an Application with Proxychains**:
   ```bash
   proxychains <application>
   ```
   Replace `<application>` with the command for the tool you want to use. For example, to use `curl` to access a website:
   ```bash
   proxychains curl http://example.com
   ```

### Example for Browsing

If you want to use a web browser like Firefox to hide your identity, you can run:
```bash
proxychains firefox
```

### Configuration Steps

1. **Edit the Proxychains Configuration**:
   Open the configuration file:
   ```bash
   sudo nano /etc/proxychains.conf
   ```

2. **Configure Proxies**:
   Add your preferred proxies under the `[ProxyList]` section. For example:
   ```plaintext
   # type   host      port     [user pass]
   socks5  127.0.0.1  9050    # Local Tor SOCKS proxy
   http    192.168.1.1 8080
   ```

3. **Choose a Chaining Method**:
   - **Dynamic Chain**: Automatically skips unavailable proxies.
     ```plaintext
     dynamic_chain
     ```
   - **Strict Chain**: Forces the use of proxies in the order listed.
     ```plaintext
     strict_chain
     ```

### Running Commands

After configuring, you can run any command through Proxychains to hide your identity. For example, to ping a server:
```bash
proxychains ping example.com
```

### Important Note

Make sure to verify that your proxies are working and not leaking your real IP. You can check your IP address before and after using Proxychains to ensure it has changed.


