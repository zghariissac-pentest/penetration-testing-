# Basic enumeration 
```
subfinder -d example.com
```
### Save output : 
```
subfinder -d example.com -o subs.txt
```
# Use multiple domains 
```
subfinder -dL domains.txt
```
# Enable all sources 
```
subfinder -d example.com -all
```
# Silent mode 
```
subfinder -d example.com -silent
```
### Perfect for chaining 
```
subfinder -d example.com -silent | httpx
```
# Add api keys 
### Use ~/.config/subfinder/provider-config.yaml
Supports:
VirusTotal
SecurityTrails
Shodan
Censys
Spyse
Chaos
GitHub
AlienVault
then run : 
```
subfinder -d example.com -config ~/.config/subfinder/provider-config.yaml
```
# Proxy / tor support 
```
subfinder -d example.com -proxy socks5://127.0.0.1:9050
```
# Rate & Performance Control
```
subfinder -d example.com -timeout 10
subfinder -d example.com -max-time 30
```
# Remove wildcards
```
subfinder -d example.com -nW
```
# OUTPUT AS JSON 

```
subfinder -d example.com -oJ subs.json
```
# Filter By Resolved Only
```
subfinder -d example.com -active
```
# Chaining With Other Tools (Professional Usage)
### Subfinder to DNSX to HTTPX
```
subfinder -d example.com -silent | dnsx -silent -a -resp | httpx -silent
```
# Subfinder to Nmap (deep scan)
```
subfinder -d example.com -silent | xargs -I{} nmap -sV -T4 {}
```
# Recursive Enumeration
```
subfinder -d example.com -recursive
```
# Passive-Only Mode
```
subfinder -d example.com -sources passive
```
# Exclude sources 
```
subfinder -d example.com -exclude shodan,fofa
```

# Ultimate Subfinder Presets
### Max coverage 
```
subfinder -d example.com -all -recursive -o full.txt
```
### Stealth Passive Recon
```
subfinder -d example.com -sources passive -silent -o passive.txt
```
### Live Subdomains Only
```
subfinder -d example.com -active -silent -o alive.txt
```










