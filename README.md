## GreenSnow   
  http://blocklist.greensnow.co/greensnow.txt
### Overview
GreenSnow is a team consisting of the best specialists in computer security, we harvest a large number of IPs from different computers located around the world.
GreenSnow is comparable with SpamHaus.org for attacks of any kind except for spam 

#### GreenSnow IP feeds
 Attacks / bruteforce that are monitored are  
  -  Scan Port
  -  FTP
  -  POP3
  -  mod_security
  -  IMAP
  -  SMTP
  -  SSH
  -  cPanel 

### PRE-REQUISITES to use GreenSnow IP feeds and DNIF  
Outbound access required to request GreenSnow IP feeds API

| Protocol   | Source IP  | Source Port  | Direction	 | Destination Domain | Destination Port  |  
|:------------- |:-------------|:-------------|:-------------|:-------------|:-------------|  
| TCP | AD,A10 | Any | Egress	| github.com | 443 |
| TCP | AD,A10 | Any | Egress	| greensnow.co | 80 | 


### Using the GreenSnow feed API
 The GreenSnow feed API is found on github at

https://github.com/dnif/enrich-greensnow

#### Getting started with Bambenek Consulting feeds API

1. #####    Login to your AD, A10 containers  
   ACCESS DNIF CONTAINER VIA SSH : [Click To Know How](https://dnif.it/docs/guides/tutorials/access-dnif-container-via-ssh.html)
2. #####    Move to the ‘/dnif/<Deployment-key/enrichment_plugins’ folder path.
```
$cd /dnif/CnxxxxxxxxxxxxV8/enrichment_plugins/
```
3. #####   Clone using the following command  
```  
git clone https://github.com/dnif/enrich-greensnow.git greensnow
```
### API feed output structure
  | Fields        | Description  |
| ------------- |:-------------:|
| EvtType      | An IP/Domain |
| EvtName      | The IOC      |
| IntelRef | Feed Name      |
| IntelRefURL | Feed URL      |
| ThreatType | DNIF Feed Identification Name |      

An example of API feed output
```
{'EvtType': 'IPv4', 
'EvtName': '106.111.55.173', 
'AddFields': {
'IntelRef': ['GREENSNOW'],
'IntelRefURL': ['http://blocklist.greensnow.co/greensnow.txt'], 
'ThreatType': ['blacklist'] }}
```
