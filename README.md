# slow
```
mkdir -p /root/slowdns
````

````
wget -O install.sh "raw.githubusercontent.com/kayu55/slow/main/install.sh" &&  chmod +x install.sh
````

````
wget -O slowdns "raw.githubusercontent.com/kayu55/slow/main/slowdns" &&  chmod +x slowdns
````
````
chmod +x /root/install.sh /root/slowdns; sudo bash /root/install.sh install
````

````
sudo bash /root/install.sh install
````

````
journalctl -u slowdns -f
````

````
cat /root/server.pub; echo "---ENV---"; cat /root/slowdns.env.
````

````
systemctl stop slowdns; killall slowdns; killall -9 slowdns; systemctl stop systemd-resolved; systemctl disable systemd-resolved; sed -i 's/#*DNSStubListener=.*/DNSStubListener=no/' /etc/systemd/resolved.conf; echo "nameserver 1.1.1.1" > /etc/resolv.conf; ss -tulpn | grep 53; printf "1\n\n\nnsify.aryablitar.com\n\n" | bash /root/install.sh
````

````
sudo nmap -sU -p53 103.41.204.190
````



