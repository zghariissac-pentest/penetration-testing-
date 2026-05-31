# OSINT Tool Cheat Sheet (theHarvester)

## 1 Install

### Linux (recommended)
git clone https://github.com/laramies/theHarvester
cd theHarvester
pip install -r requirements.txt

### Or via package manager (if available)
pip install theHarvester

---

## 2 Basic Usage

theHarvester -d example.com -b google

---

## 3 Core Command Structure

theHarvester -d TARGET_DOMAIN -b SOURCE

- TARGET_DOMAIN → domain you want to investigate
- SOURCE → data source (search engines, public datasets, etc.)

---

## 4 Real Example

theHarvester -d tesla.com -b bing

---

## 5 Multiple Sources Scan

theHarvester -d example.com -b google,bing,duckduckgo

---

## 6 Limit Results

theHarvester -d example.com -b google -l 50

---

## 7 DNS Brute Force Mode

theHarvester -d example.com -c

---

## 8 Shodan Integration (API required)

theHarvester -d example.com -b shodan

---

## 9 Save Output

### HTML report
theHarvester -d example.com -b google -f report.html

---

## 10 Export Options

theHarvester -d example.com -b google -f results

Creates multiple output formats depending on configuration

---

## 11 Show Help

theHarvester -h

---

## 12 Typical Workflow

1 Choose target domain  
2 Select data source(s)  
3 Run scan command  
4 Collect emails, subdomains, hosts  
5 Cross-check results manually  

---

## 13 Notes

- Results depend on public indexing sources  
- Some APIs (like Shodan) require keys  
- Best used for passive reconnaissance
