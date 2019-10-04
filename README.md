# Suricata_Ubuntu18_LTS
Intrution Detection Prevention System Suricata

A. Install and Config:

1. Add repository stable version: 
> sudo add-apt-repository ppa:oisf/suricata-stable

2. Update:
> sudo apt-get update

3. Install support engine:
> sudo apt-get -y installlibpcre3 libpcre3-dbg libpcre3-dev \build-essential autoconf automake libtool libpcap-dev libnet1-dev \libyaml-0-2 libyaml-dev zlib1g zlib1g-dev libcap-ng-dev libcap-ng0\make libmagic-dev libjansson-dev libjansson4 pkg-config

4. Install Suricata:
> sudo apt-get install suricata 

5. Install IPS mode:
> sudo apt-get -y install libnetfilter-queue-dev libnetfilter-queue1 libnfnetlink-dev libnfnetlink0

6. Config Address Group:
> address-groups:HOME_NET: "[192.168.100.0/24]" 
#HOME_NET: "[192.168.0.0/16,10.0.0.0/8,172.16.0.0/12]"
#HOME_NET: "[192.168.0.0/16]"
#HOME_NET: "[10.0.0.0/8]"

7. Config Suricata Active rules:
> default-rule-path: /etc/suricata/rules
rule-files:
-emerging-clabs_dos.rules
-emerging-clabs_metasploit.rules
-emerging-clabs_nmap.rules


B. Testing:

1. Start Engine:
  <img src="https://raw.githubusercontent.com/fredriclesomar/Suricata_Ubuntu18_LTS/master/img/Start_Engine.png" width="750" title="Engine Started">
</p>

Realtime monitoring, follow the command:
> sudo tail -f /var/log/suricata/fast.log

2. Scanning TCP report:
  <img src="https://raw.githubusercontent.com/fredriclesomar/Suricata_Ubuntu18_LTS/master/img/nmap_TCPscanning_report.png" width="750" title="Engine Started">
</p>

3. Scanning UDP report:
  <img src="https://raw.githubusercontent.com/fredriclesomar/Suricata_Ubuntu18_LTS/master/img/nmap_UDPscanning_report.png" width="750" title="Engine Started">
</p>

4. DOS report:
  <img src="https://raw.githubusercontent.com/fredriclesomar/Suricata_Ubuntu18_LTS/master/img/Hping3_DOS_report.png" width="750" title="Engine Started">
</p>

4. Exploit report:
  <img src="https://raw.githubusercontent.com/fredriclesomar/Suricata_Ubuntu18_LTS/master/img/ELF_Metasploit_report.png" width="750" title="Engine Started">
</p>








