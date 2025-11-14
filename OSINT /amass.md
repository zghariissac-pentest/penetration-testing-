# 1. Core Modules Overview
Amass has 5 primary functions:

Command	Purpose
amass enum	Subdomain enumeration (active + passive)
amass intel	High‑level intelligence (ASN, CIDR, org discovery)
amass viz	Create data graphs and visualizations
amass db	Query local Amass database
amass track	Compare results across time (monitor drift)

# Passive Enumeration (Stealth, Zero-Touch)
```
amass enum -passive -d example.com
```
### Save Output to File: 
```
amass enum -passive -d example.com -o passive.txt
```
### multiple domains : 
```
amass enum -passive -df domains.txt
```
# active enumeration
```
amass enum -active -d example.com
```
### enable all teckniques :
```
amass enum -brute -active -d example.com
```
### massive brute force with wordlist 
```
amass enum -brute -w wordlist.txt -d example.com
```
### alteration engine (high value)
```
amass enum -active -d example.com -alters -w words.txt
```
# Ultimate Recon Mode (All Engines)
```
amass enum -d example.com -active -brute -alters -w list.txt -src -ip -asn -o results.txt
```
Includes:
DNS queries
recursive brute-force
permutations & mutations
ASN/Netblock pivoting
live host correlations

# Reverse DNS Sweep (Infrastructure Discovery)
### Using IP range : 
```
amass enum -d example.com -cidr 192.168.0.0/16
```
### From ASN : 
```
amass intel -asn <AS_NUMBER> --whois
```

### discover all netbloacks for ASN :
```
amass intel -asn <AS> -o asn_blocks.txt
```
# Organization Discovery (OSINT Intelligence): 
```
amass intel -org "Tesla"
```
### List domains linked to org :
```
amass intel -org "Tesla" -dnet
```

# Discover related domains : 
```
amass intel -d example.com -whois
```
### Pivor using WHOIS connections :
```
amass intel -d example.com -whois -o related.txt
```
# Enumerate Subdomains from Certificates

```
amass enum -passive -d example.com --src --include crtsh
```

# Resolve and identify live hosts 
```
amass enum -d example.com -ipv4 -ipv6 -o resolved.txt
```
### show sources (i recommand this)
```
amass enum -d example.com -src -o detailed.txt
```
# Amass DB (Query Local Recon Database)

### Show all discoverd assests : 
```
amass db -names -d example.com
```
### Show associated IPS :
```
amass db -ip -d example.com
```
### Dump everything : 
```
amass db -show -d example.com
```
### Search for old intel : 
```
amass db -search keyword
```
# Tracking Changes Over Time (Corporate-Grade Monitoring)
```
amass track -d example.com -last
```
### Compare base line vs new scan :
```
amass track -d example.com -df old.txt
```
### Show new attack surface drift : 
```
amass track -d example.com -since 30d
```

# Visualizing Results (Graphs): 
### Make a graph   
```
amass viz -d3 -o graph
```
### Create Graphviz DOT:
```
amass viz -dot -d example.com -o example.dot
```
### Render nodes & edges:
```
amass viz -d3 -config config.ini -o output
```
# Proxying & Tor Support

```
amass enum -d example.com -proxy socks5://127.0.0.1:9050
```
### Proxy list :
```
amass enum -d example.com -rf proxies.txt
```
# API Keys & Config Optimization
Use config.ini to add:
Virustotal
SecurityTrails
Shodan
Censys
CRtSH
Spyse
DNSDB
Max power:
```
amass enum -config config.ini -d example.com
```
# Rate Control & Performance
```
amass enum -d example.com --max-dns-queries 1000
amass enum -timeout 30
```
# Ultimate Corporate Recon Presets
### Stealth Passive Mapping
```
amass enum -passive -d example.com -src -ip -o passive.txt
```
### Deep Active Mapping
```
amass enum -active -brute -alters \
-d example.com \
-src -ip -asn \
-w wordlist.txt \
-o deep.txt
```
### Full Attack Surface OSINT Sweep
```
amass intel -org "Company" --whois -max-dns-queries 10000 -o intel.txt
amass enum -active -brute -alters -d example.com -o enum.txt
amass track -d example.com -since 30d -o drift.txt
```










