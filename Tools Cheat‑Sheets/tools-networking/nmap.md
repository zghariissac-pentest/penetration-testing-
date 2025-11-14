# host discovery (stealth / accuracy)
 ### basic : 
```
nmap -sn <target>              # Host discovery only (no port scan)
nmap -Pn <target>              # Skip host discovery (treat hosts as online)
```
 ### advanced host discovery : 
 ```
nmap -sn -PS21,22,80,443 <t>   # SYN ping on specific ports
nmap -sn -PA80,443 <t>         # ACK ping (bypasses some filters)
nmap -sn -PU53 <t>             # UDP ping (DNS)
nmap -sn -PR <t>               # ARP ping (LAN only, very accurate)
```

# port scanning :
### core scans : 

```
nmap -sS <t>                   # SYN scan (default, fast, stealthy)
nmap -sT <t>                   # TCP connect scan (useful without raw sockets)
nmap -sU <t>                   # UDP scan
nmap -sSU <t>                  # Hybrid TCP+UDP
nmap -sN <t>                   # Null scan
nmap -sF <t>                   # FIN scan
nmap -sX <t>                   # Xmas scan
```
### performance scans :
```
nmap -T4 <t>                   # Faster (recommended)
nmap -T5 <t>                   # Very fast (aggressive)
nmap --min-rate 500 <t>        # Force minimum packet rate
nmap --max-rate 2000 <t>       # Cap packet rate
nmap --min-parallelism 64      # Increase parallel tasks
```
# port range control 
```
nmap -p- <t>                   # Scan all 65535 TCP ports
nmap -p1-1024 <t>              # Scan specific range
nmap -p80,443,8080 <t>         # Scan specific ports
nmap -pU:53,T:80,443 <t>       # Mixed UDP/TCP
```
# Service and version enumeration
```
nmap -sV <t>                   # Service version detection
nmap -sV --version-intensity 9 <t>   # Maximum version detection
nmap -A <t>                    # Aggressive scan (OS, version, scripts, traceroute)
nmap --allports <t>            # Do not exclude “dangerous” ports
```

# OS fingerprinting :
```
nmap -O <t>                    # OS detection
nmap -O --osscan-guess <t>     # Aggressive guessing
```
# NSE (Nmap Scripting Engine) , Advanced Use
### script categories :
```
auth      brute      broadcast
default   discovery  dos
exploit   external   fuzzer
intrusive malware    safe
version   vuln
```
### run specific scripts : 
```
nmap --script dns-brute <t>
nmap --script ssl-heartbleed <t>
nmap --script http-title <t>
nmap --script vuln <t>         # Broad vulnerability checks (safe subset)
```
### Script arguments :
```
nmap --script ftp-anon --script-args ftp-anon.maxlist=200 <t>
nmap --script http-brute --script-args userdb=users.txt,passdb=pass.txt <t>
```

# Firewall / IDS evasion
```
nmap -f <t>                    # Fragment packets
nmap --mtu 16 <t>              # Custom MTU (divisible by 8)
nmap -D decoy1,decoy2,<yourIP> <t>   # Decoy scanning
nmap -S <spoofed-IP> <t>       # Spoof source IP (requires --ttl / routing setup)
nmap -g 53 <t>                 # Source port spoofing (e.g., DNS)
nmap --data-length 50 <t>      # Random padding
```
# Timing, stability & reliability
```
nmap --defeat-rst-ratelimit <t>
nmap --max-retries 2 <t>
nmap --host-timeout 30m <t>    # Kill slow hosts
nmap --scan-delay 1s <t>       # Bypass rate limits
```
# Output & Reporting 
```
nmap -oN scan.txt <t>          # Normal output
nmap -oX scan.xml <t>          # XML output
nmap -oG scan.grep <t>         # Greppable
nmap -oA scan <t>              # All formats: .nmap .xml .grep
```
### diffing scans over time : 
```
ndiff scan1.xml scan2.xml
```
# Advanced targets and input 
```
nmap -iL targets.txt           # Input list
nmap --exclude host1,host2 <t> # Exclude hosts
nmap --exclude-file skip.txt   # Exclude from file
```
# IPv6 scanning 
```
nmap -6 <target>
nmap -6 -sV -p- <target>
```
# Top Professional Scan Presets
### Full stealth recon : 
```
nmap -sS -sV -O -T4 -p- <t>
```
### Fast + Detailed Versioning
```
nmap -sC -sV -T4 <t>
```
### Maximum Enumeration
```
nmap -A -p- --script=default,vuln,discovery --version-intensity 9 <t>
```
# Useful Environment Flags
```
nmap --disable-arp-ping <t>
nmap --traceroute <t>
nmap --datadir /custom-nse      # Custom script directory
```

i hope this helped you :) 
