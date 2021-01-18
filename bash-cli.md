# navigation

Ctrl + a - Go to the start of the current command
 Ctrl + e - Go the end of the current command
 Ctrl + w - Delete the next item left of the cursor (argument or command)
 Ctrl + u - Cut everything before the cursor
 Ctrl + k - Cut every after the cursor
 Ctrl + y - Paste back whatever you cut with Ctrl +u or Ctrl + y
 Ctrl + p - Scroll through previous commands
 Ctrl + n - Next command
 Ctrl + l - Clear the screen
 

# check ssl certificate
```
openssl s_client -connect url.com:port
```

# check number of cpus

```
lscpu command
cat /proc/cpuinfo
top
htop
nproc
hwinfo
dmidecode -t processor
getconf _NPROCESSORS_ONLN
```

# watch -d -n 5

watch the output of a command.  polling is specified in seconds using the -n switch

# tr

truncate

# ncdu

Useful tool for checking disk usage

# scp files from remote to local

scp betaprodsftp01:/dir/file ~/

scp betaprodsftp01:/sftp/sftp-prod/incoming/SSCS_Extract_Delta_2020-05-15-03-58-26.xml ~/

# count number of lines in file

wc -l file

# encrypt file (multiple files not supported)

gpg -c filename

# XML lint

xmllint --noout filename

# Configure SSH key authentication

ssh-keygen -b 4096 -f output-file -N "passphrase" -C "comment"

ssh-copy-id -i ~/.ssh/id_rsa_identity.pub user@server-ip

Disable password authentication:

sudo nano /etc/ssh/sshd_config

  PasswordAuthentication no
  
# curl

curl --ssl-reqd -k -I -L cts-challenge.prp1.np.immigration-api.homeoffice.gov.uk

curl --ssl-reqd -k -I -L -H 'Host: cts-challenge.prp1.np.immigration-api.homeoffice.gov.uk' 'https://52.209.194.79'

-k : ignore ssl error
-I : headers only
-L : follow redirects
-H : specify host header

# Generate random password / passphrase using openssl

openssl rand -base64 32 | tr -d /=+ | cut -c -25

# multiline file edit from bash cli

touch filename | cat >> filename << EOL
content of file
more text
EOL

# tunnel through a bastion

ssh -L 6432:dbhost.postgres.database.azure.com:5432 devopsbastion

# Check SSL cert

echo | openssl s_client -connect core-infra-idm-idam-prod2.postgres.database.azure.com:443 -servername core-infra-idm-idam-prod2.postgres.database.azure.com 2>/dev/null | openssl x509 -text -noout | egrep -i  'CN|DNS|after|before'

# create self signed ssl

openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout cert.key -out cert.crt -subj "/CN=firstflight.local"

# merge .key and .crt into pfx

openssl pkcs12 -export -out cert.pfx -inkey cert.key -in cert.crt

# view logs with journalctl
https://www.howtogeek.com/499623/how-to-use-journalctl-to-read-linux-system-logs/

time,hostname,process,message

journalctl
journalctl --no-pager  #output to console
journalctl -n 10  #restrict rows
journalctl -f  #follow logs
journalctl -o short/verbose/json/json-pretty/cat  #set output format
journalctl -S "2020-91-12 07:00:00"  #set time period
journalctl -S "2020-91-12 07:00:00" -U "2020-91-12 07:15:00"  #since - until
journalctl -S -1d/1h/today/yesterday  #time period

# view logs

```
dmesg

cat /var/log/syslog

# view tar file

```
tar -ztvf molecule.tar.gz
```

# compress tar.gz file

```
tar -czvf file.tar.gz [ files | directories ]
```

# extract tar.gz file

```
tar -xzvf file.tar.gz [ files | directories ]
```

