# Sherlock OSINT Tool Cheat Sheet

## Install
pip install sherlock

## Or from source
python setup.py install

## Basic usage
sherlock username

## Example
sherlock johndoe

## With save output
sherlock username --output results.txt

## JSON output
sherlock username --json

## CSV output
sherlock username --csv

## Folder output (all formats)
sherlock username --folderoutput results

## Timeout control
sherlock username --timeout 30

## Proxy usage
sherlock username --proxy http://127.0.0.1:8080

## Tor usage
sherlock username --tor

## Verbose mode
sherlock username --verbose

## Site specific search
sherlock username --site Instagram

## Limit sites
sherlock username --limit 20

## Skip sites
sherlock username --skip Instagram,Twitter

## Update tool
python sherlock.py --update

## Help
sherlock --help
