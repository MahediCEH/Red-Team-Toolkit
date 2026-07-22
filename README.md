This repository is designed for students, penetration testers, and cybersecurity enthusiasts who want to learn the most commonly used Red Team tools in a structured order. Each tool includes its primary use case, executable, and a simple example to help you get started.

> **⚠️ Disclaimer**
>
> This repository is intended **for educational purposes only**. Use these tools only in environments where you have explicit authorization, such as labs, Capture The Flag (CTF) challenges, or systems you own. Unauthorized use may violate laws and regulations.

---

# 🎯 Learning Order

The tools in this repository follow a typical Red Team workflow. Starting with foundational utilities and reconnaissance techniques before progressing to exploitation, privilege escalation, and post-exploitation helps build practical skills in a logical order.

Commands & Utilities
        ↓
OSINT & Passive Recon
        ↓
Reconnaissance & Port Scanning
        ↓
Enumeration
        ↓
Web Application Testing
        ↓
Vulnerability Scanning
        ↓
Exploitation
        ↓
Password Attacks
        ↓
Active Directory & Windows Post-Exploitation
        ↓
Privilege Escalation
        ↓
Pivoting & Tunneling
        ↓
Traffic Analysis
        ↓
Supporting & Research
        ↓
Command & Control (C2)

---

# 🖥️ 1. Commands & Utilities

These foundational tools are used throughout almost every penetration test. They help with scripting, automation, networking, downloading files, traffic analysis, and interacting with remote services.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Bash | Linux shell scripting, automation, chaining commands | `bash` | `bash script.sh` |
| Python | Automation, exploit development, custom security scripts | `python3` | `python3 exploit.py` |
| Git | Clone repositories and manage source code | `git` | `git clone https://github.com/project/repo.git` |
| cURL | Manual HTTP requests, API testing, downloading content | `curl` | `curl -I https://target.com` |
| Wget | Download files, tools and wordlists | `wget` | `wget https://example.com/file.txt` |
| OpenSSL | SSL/TLS testing, certificate inspection and encryption utilities | `openssl` | `openssl s_client -connect target.com:443` |
| Netcat (nc) | Reverse shells, bind shells, banner grabbing, file transfer and port listening | `nc` | `nc -lvnp 4444` |
| tcpdump | Command-line packet capture, filtering and traffic analysis | `tcpdump` | `tcpdump -i eth0` |
| smbclient | Browse and connect to SMB/CIFS network shares | `smbclient` | `smbclient -L //10.10.10.10/ -N` |

---

# 🌍 2. OSINT & Passive Recon

Open Source Intelligence (OSINT) gathers publicly available information before directly interacting with the target. This phase helps identify domains, subdomains, exposed services, email addresses, and other valuable information.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| theHarvester | Collect emails, subdomains, hosts and employee names from public sources | `theHarvester` | `theHarvester -d example.com -b all` |
| Amass | Passive and active subdomain enumeration | `amass` | `amass enum -d example.com` |
| Shodan | Search Internet-connected devices, services and exposed systems | `shodan` | `shodan search apache` |
| Censys | Internet-wide host and certificate search | `censys` | `censys search "Apache"` |

---

# 🔍 3. Reconnaissance & Port Scanning

Reconnaissance identifies live hosts, open ports, running services, and operating systems. This information defines the target's attack surface before moving on to deeper enumeration.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Nmap | Network discovery, port scanning, service detection and OS fingerprinting | `nmap` | `nmap -sC -sV 10.10.10.10` |
| RustScan | High-speed port scanner that integrates with Nmap | `rustscan` | `rustscan -a 10.10.10.10 -- -sC -sV` |

---

# 📋 4. Enumeration

Enumeration gathers detailed information from discovered services, web applications, and SMB resources. It helps uncover hidden content, technologies, users, shares, and other valuable information.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| WhatWeb | Identify web technologies, CMS, frameworks and servers | `whatweb` | `whatweb https://target.com` |
| Wappalyzer | Detect website technologies via browser or CLI | `Browser Extension / wappalyzer` | `wappalyzer https://target.com` |
| FFUF | Fast web fuzzing for directories, files, parameters and virtual hosts | `ffuf` | `ffuf -u http://target/FUZZ -w wordlist.txt` |
| Gobuster | Directory, DNS and virtual host brute-force enumeration | `gobuster` | `gobuster dir -u http://target -w wordlist.txt` |
| Dirsearch | Discover hidden directories and files | `dirsearch` | `dirsearch -u http://target` |
| Feroxbuster | Recursive web content discovery | `feroxbuster` | `feroxbuster -u http://target` |
| enum4linux-ng | Enumerate SMB shares, users, groups and domain information | `enum4linux-ng` | `enum4linux-ng -A 10.10.10.10` |

---

# 🌐 5. Web Application Testing

These tools are used to inspect, proxy, and assess web applications for security issues. They support both manual testing and automated vulnerability discovery.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Burp Suite | Intercept, inspect, modify HTTP/HTTPS traffic and perform manual web security testing | `burpsuite` | `burpsuite` |
| OWASP ZAP | Open-source intercepting proxy and automated web vulnerability scanner | `zaproxy` | `zaproxy` |
| SQLMap | Automated detection and exploitation of SQL Injection vulnerabilities | `sqlmap` | `sqlmap -u "http://target/page?id=1" --dbs` |

---

# 🛡️ 6. Vulnerability Scanning

Vulnerability scanners identify known vulnerabilities, misconfigurations, and exposed weaknesses before manual exploitation. They help prioritize targets for further testing.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Nuclei | Fast template-based vulnerability scanning for CVEs, misconfigurations and exposed services | `nuclei` | `nuclei -u https://target.com` |
| Nikto | Scan web servers for dangerous files, outdated software and common misconfigurations | `nikto` | `nikto -h http://target` |
| WPScan | Scan WordPress core, themes, plugins and users for known vulnerabilities | `wpscan` | `wpscan --url https://target.com --api-token YOUR_API_TOKEN` |
| Searchsploit | Search the local Exploit Database for public exploits and proof-of-concepts | `searchsploit` | `searchsploit apache 2.4` |

---

# 💥 7. Exploitation

Exploitation is the process of gaining initial access to a target by leveraging discovered vulnerabilities or security misconfigurations. These tools help security professionals validate findings during authorized penetration tests.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Metasploit Framework | Exploitation framework, payload generation, exploitation and post-exploitation | `msfconsole` | `msfconsole` |

---

# 🔑 8. Password Attacks

Password attacks are performed to evaluate the strength of authentication mechanisms or recover password hashes during authorized security assessments.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Hydra | Online password attacks against network services (SSH, FTP, RDP, HTTP, etc.) | `hydra` | `hydra -l admin -P rockyou.txt ssh://10.10.10.10` |
| Hashcat | High-speed GPU-based password hash cracking | `hashcat` | `hashcat -m 1000 hashes.txt rockyou.txt` |
| John the Ripper | CPU-based password and hash cracking | `john` | `john hashes.txt --wordlist=rockyou.txt` |

---

# 🏢 9. Active Directory & Windows Post-Exploitation

After obtaining an initial foothold, these tools help enumerate Active Directory, validate credentials, move laterally, abuse Kerberos, and assess Windows domain security during authorized engagements.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Impacket | Python toolkit for SMB, NTLM, Kerberos, LDAP and Windows protocol attacks | `impacket-*` | `impacket-secretsdump domain/user:pass@10.10.10.10` |
| NetExec (formerly CrackMapExec) | Active Directory enumeration, credential validation, password spraying and lateral movement | `netexec` | `netexec smb 10.10.10.10 -u user -p pass` |
| BloodHound | Visualize Active Directory attack paths and privilege relationships | `bloodhound` | `bloodhound` |
| Neo4j | Graph database backend required by BloodHound | `neo4j` | `neo4j console` |
| SharpHound | Collect Active Directory data for BloodHound analysis (Windows target) | `SharpHound.exe` | `SharpHound.exe -c All` |
| Evil-WinRM | Remote interactive PowerShell shell over WinRM | `evil-winrm` | `evil-winrm -i 10.10.10.10 -u administrator -p Password123` |
| Responder | Capture NTLM credentials by responding to LLMNR, NBT-NS and mDNS requests | `responder` | `responder -I eth0 -rdwv` |
| Kerbrute | Kerberos username enumeration and password spraying | `kerbrute` | `kerbrute userenum users.txt -d corp.local` |
| Certipy | Enumerate and assess Active Directory Certificate Services (AD CS) | `certipy` | `certipy find -u user -p pass -dc-ip 10.10.10.10` |
| Mimikatz | Extract Windows credentials and Kerberos tickets from memory (Windows target) | `mimikatz.exe` | `privilege::debug` → `sekurlsa::logonpasswords` |
| Rubeus | Kerberos ticket extraction, abuse and delegation testing (Windows target) | `Rubeus.exe` | `Rubeus.exe kerberoast` |

> **📝 Note**
>
> - **SharpHound**, **Mimikatz**, and **Rubeus** run on the compromised **Windows host**, not on the Linux attack machine.
> - **Neo4j** is the graph database backend required by **BloodHound**.

---

# ⬆️ 10. Privilege Escalation

Privilege escalation tools enumerate systems for common misconfigurations and security weaknesses that may allow access to higher privileges after obtaining an initial shell.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| LinPEAS | Enumerate Linux privilege escalation vectors | `linpeas.sh` | `chmod +x linpeas.sh && ./linpeas.sh` |
| WinPEAS | Enumerate Windows privilege escalation vectors (Windows target) | `winPEASx64.exe` | `winPEASx64.exe` |

---

# 🌐 11. Pivoting & Tunneling

Pivoting allows testers to reach internal systems that are not directly accessible. These tools create tunnels, forward ports, and route traffic through compromised hosts.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Chisel | HTTP/HTTPS tunneling and reverse port forwarding | `chisel` | `chisel server -p 8000 --reverse` |
| Ligolo-ng | High-performance network pivoting using a TUN interface | `ligolo-ng` | `ligolo-ng proxy -selfcert` |
| ProxyChains | Route applications through SOCKS4/SOCKS5 proxies | `proxychains` | `proxychains nmap 10.10.10.20` |
| Socat | Advanced TCP/UDP relays, port forwarding and shell redirection | `socat` | `socat TCP-LISTEN:4444,fork TCP:10.10.10.20:80` |

---

# 📡 12. Traffic Analysis

Traffic analysis tools capture and inspect network packets during reconnaissance, exploitation, troubleshooting, or post-exploitation. They help understand network behavior and investigate communication between systems.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Wireshark | GUI-based packet capture and protocol analysis | `wireshark` | `wireshark` |
| TShark | Command-line version of Wireshark for packet capture and analysis | `tshark` | `tshark -i eth0` |

> **📝 Note**
>
> - **Wireshark** and **TShark** use the same packet analysis engine.
> - Use **Wireshark** for interactive analysis and **TShark** for scripting, automation, or remote systems.

---

# 🧰 13. Supporting & Research

These utilities assist throughout reconnaissance, exploitation, post-exploitation, and reporting by transforming, decoding, analyzing, and converting different types of data.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| CyberChef | Data encoding/decoding, hashing, encryption, format conversion, Base64, JWT, XOR, regex and forensic data analysis | Web Application | Open CyberChef in a browser |

> **📝 Note**
>
> **CyberChef** is not an exploitation tool. It is one of the most useful utilities for transforming, decoding, and analyzing data during security assessments.

---

# 🎯 14. Command & Control (C2)

Command and Control (C2) frameworks enable operators to manage compromised hosts, execute commands remotely, deliver payloads, and coordinate post-exploitation activities during authorized adversary simulations.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Sliver | Open-source Command & Control framework for implants, operators, pivoting and post-exploitation | `sliver-server` | `sliver-server` |
| Cobalt Strike | Commercial adversary simulation platform with Beacon payloads and team collaboration | `teamserver` | `./teamserver 10.10.10.5 StrongPassword` |

> **📝 Note**
>
> - **Sliver** is the most popular open-source alternative to **Cobalt Strike**.
> - **Cobalt Strike** is commercial software commonly used by authorized Red Teams and is also frequently abused by threat actors after being obtained illicitly.

---

# 📖 Recommended Learning Resources

- TryHackMe
- Hack The Box
- PortSwigger Web Security Academy
- OWASP Top 10
- OWASP Web Security Testing Guide (WSTG)
- MITRE ATT&CK
- Exploit Database
- GTFOBins
- LOLBAS

---

# 🤝 Contributing

Contributions are welcome! Feel free to submit pull requests, suggest new tools, improve descriptions, or report inaccuracies by opening an issue.

---

# ⚖️ License

This repository is licensed under the **MIT License**.

---

# ⭐ Support

If you find this repository useful, consider giving it a **⭐ Star**. It helps others discover the project and motivates future improvements.

---

## ⚠️ Disclaimer

This repository is provided **for educational and authorized security testing only**. The tools listed here should only be used in environments where you have explicit permission to perform security assessments. The author is not responsible for any misuse of the information contained in this repository.
