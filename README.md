Drop this in /usr/local/bin, chmod it 755, make sure your 
/etc/openvpn/vars sets EASY_RSA='/etc/openvpn' instead of 
setting it to the current directory, and you're pretty
much off to the races.

Will create credentials if none exist, or use existing
credentials if a keypair has already been created, and 
drop a single-file client .ovpn including all keys and
certs necessary into /tmp/clientname.ovpn.

create-vpn-creds expects to find a template config file at
/etc/openvpn/templates/client-template.base. Sample config
file included in this repo.

```
root@yourserver:~# create-vpn-creds clientname

Creating credentials for jrs ...
Credentials exported to /tmp/clientname.ovpn.

root@yourserver:~# create-vpn-creds clientname

Existing credentials for clientname found ...
Credentials exported to /tmp/clientname.ovpn.

root@yourserver:~# 
```
