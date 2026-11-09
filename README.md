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
curl -4 -s ifconfig.me; echo; cat /root/ip
````
### jos
````
rm -f /etc/netplan/60-static.yaml; IFACE=$(ip route | grep default | awk '{print $5}' | head -n1); IP=$(ip -4 addr show $IFACE | grep -oP 'inet \K[0-9./]+' | head -n1); GW=$(ip route | grep default | awk '{print $3}' | head -n1); MAC=$(cat /sys/class/net/$IFACE/address); echo "IFACE: $IFACE | IP: $IP | GW: $GW | MAC: $MAC"; cat > /etc/netplan/60-static.yaml <<EOF
network:
  version: 2
  ethernets:
    $IFACE:
      dhcp4: false
      dhcp6: false
      match:
        macaddress: $MAC
      set-name: $IFACE
      addresses:
        - $IP
      routes:
        - to: default
          via: $GW
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]
EOF
chmod 600 /etc/netplan/60-static.yaml; cat /etc/netplan/60-static.yaml; netplan apply; echo "=== HASIL ==="; curl -4 -s ifconfig.me; echo; cat /root/ip
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



