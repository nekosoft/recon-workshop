- finding subdomains (passive and active)
- google dorking
- looking for naming conventions (organise the data)
- create domain permutations - manual + code + use a tool
- requests for domain permutations -> capture result and maybe image
- wordlist for bruteforcing (SecLists)
- can create your own wordlist

- parse a file, read, write
- create file

---

Domain Permutations
Check domain in VirusTotal (can check other places too)

dnstwist
whois

---

Domains
Sub domains
ASN - amass intel -asn
protocol - ? - ssl?
reverse whois

--

sub domains

### subdomain scraping

- more we find, more we have to look at!
- netcraft
- dnsdb search
- wayback machine
- https://github.com/dnsdb/dnsdb-query
- robtex
- dnsdumpster.com
- ptrarchive.com
- passive total

- yahoo
- google
- baidu
- bing
- ask.com
- dogpile

certificate sources
- crt.sh
- sslmate
- certspotter
- certdb

security sources
- hacker target
- security trails
- virustotal
- f-secure riddler
- threatcrowd
- threatminer


google for subdomain

site:twitch.tv -www.twitch.tv -watch.twitch.tv -dev.twitch.tv


tool: amass
- kick them off in a script (2-10 mins)
- table at the end
- what asn they came out of
- overview of cloud and third party services they might be using
- feed asn back into amass intel
amass -rf flag 

`amass enum -brute -d twitch.tv -src`
`amass enum -brute -d twitch.tv -rf resolvers.txt -w bruteforce.list`

tool: subfinder
- projectdiscovery.io

subdomain scraping: github-subdomains.py
repo: github-search
run 5 iterations of this script
4 of them with a six second sleep in between them
last with a 10 second sleep

cat file | grep -v "term here"
sort | uniq

sleeps - want to avoid rate limiting / api restrictions

shosubgo - parser for shodan written in go
- looks specifically for subdomains

`go run main.go -d domain.com -s shodan_key`

---

Tech analysis

builtwith.com
- ad analytics trackers
- technology profile
- relationship profile

Tech profiling: browser extensions
- what runs
- wappalyzer
    - also have command line functions

- webanalyze on command line
    - `webanalyze -host https://www.twitch.tv`
    
---

gau
file types
juicy stuff

appsettings.json and asp.net app - should never be exposed to the internet
- config giles for DB connections
- admin login and routes/endpoints are

---

Domains lead to Content Discovery

### Content Discovery

- based on tech
- cots/paid/oss
- custom
- historical
- recursive
- mobile api's
- change detection

effective content discovery will help you find lucrative content
- all of the endpoints you can possibly find
lots of tools / web fuzzing etc:
- gobuster
- wfuzz
- turbo intruder

the tools are only as good as the lists you feed them

Tip - changes
- change detection for a site
- changedetection.io