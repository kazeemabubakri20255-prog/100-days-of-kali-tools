\# Nmap Command Cheatsheet



\## Basic Scans



| Command | Purpose |

|---------|---------|

| `nmap <target>` | Basic scan of top 1000 ports |

| `nmap -sS <target>` | SYN stealth scan (root) |

| `nmap -sT <target>` | TCP connect scan (no root) |

| `nmap -sU <target>` | UDP scan |

| `nmap -sn <target>` | Ping scan (host discovery) |



\## Port Selection



| Command | Purpose |

|---------|---------|

| `nmap -p 80,443 <target>` | Scan specific ports |

| `nmap -p 1-1000 <target>` | Scan port range |

| `nmap -p- <target>` | Scan all 65535 ports |

| `nmap --top-ports 100 <target>` | Scan top 100 ports |



\## Service \& OS Detection



| Command | Purpose |

|---------|---------|

| `nmap -sV <target>` | Service version detection |

| `nmap -O <target>` | OS detection |

| `nmap -A <target>` | Aggressive scan |

| `nmap -sC <target>` | Default scripts |



\## Timing \& Performance



| Command | Purpose |

|---------|---------|

| `nmap -T0 <target>` | Paranoid (slowest) |

| `nmap -T4 <target>` | Aggressive |

| `nmap -T5 <target>` | Insane (fastest) |



\## Output



| Command | Purpose |

|---------|---------|

| `nmap -oN output.txt <target>` | Normal output |

| `nmap -oX output.xml <target>` | XML output |

| `nmap -oA output <target>` | All formats |



\## NSE Scripts



| Command | Purpose |

|---------|---------|

| `nmap --script vuln <target>` | Vulnerability scan |

| `nmap --script smb-vuln\* <target>` | SMB vulnerabilities |

| `nmap --script http-enum <target>` | HTTP enumeration |



\## Common Combos



\### Full recon on Metasploitable

```bash

sudo nmap -sS -sV -p- -T4 -n 192.168.56.101 -oA metasploitable\_scan



Quick scan on Windows 10

bash

sudo nmap -sS -sV -p 135,139,445,3389,5985 -n 192.168.56.106



Vulnerability scan

bash

sudo nmap --script vuln -n 192.168.56.101

