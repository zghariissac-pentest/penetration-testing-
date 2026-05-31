# Maigret OSINT Tool Cheat Sheet

## 1 Install

pip install maigret

Or from source:

git clone https://github.com/soxoj/maigret
cd maigret
pip install -r requirements.txt

---

## 2 Basic Scan

maigret username

Example:

maigret johndoe

---

## 3 Output Formats

### HTML Report
maigret username --html

Creates a full visual report in browser format

### JSON Output
maigret username --json

Machine readable results

### CSV Output
maigret username --csv

Spreadsheet compatible results

---

## 4 Target Control

### Limit number of sites
maigret username --max-sites 50

Speeds up scanning by reducing checks

### Scan specific site only
maigret username --site instagram

Focus on one platform

### Skip platforms
maigret username --skip twitter,facebook

Exclude unwanted sites

---

## 5 Performance Options

### Faster scan
maigret username --max-sites 30 --quiet

### Detailed scan
maigret username --verbose

---

## 6 Database Management

Update supported platforms list:

maigret --update

---

## 7 Debug and Help

Show help menu:

maigret --help

---

## 8 Typical Workflow

1 Install tool  
2 Choose username target  
3 Run scan command  
4 Generate HTML report  
5 Review matches manually  
6 Validate results with direct links  

---

## 9 Notes

Results depend on public data availability. Some platforms may block automated checks or return limited information.
