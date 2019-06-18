# 3GPP Reference Architectures
PAN-OS Skillets for Palo Alto Networks NGFW configuration along the 3GPP Reference Points.

## Installation
- Use this repo along with Panhandler. To fetch the latest update of Panhadler from docker, run
```bash
 docker pull  paloaltonetworks/panhandler
 ```
 - then start your container with 
```bash
docker run -t -p 7777:80  paloaltonetworks/panhandler
```
- Full documentation for Panhandler is available in its [repo](https://github.com/PaloAltoNetworks/panhandler)
Connect to Panhandler with your browser and import this repo using the link provided in github.

##Usage
You find one Skillet Collection per usecase. Inside each Collection the 3GPP reference point is represented with an individual Skillet. Build your Security Policy by adding together the Skillets you need, each Skillet creates one Rule.
Along that Security Policy Rule, the Skillet might create anything else it requires to activate the Rule in PanOS. This is, at least:
- Security Zones (red=external untrust, blue=own trust, black=own untrust)
- one tag for each Zone (red/blue/black)
- one address object for each end of the Reference Point
Make sure you have the **latest version** of the [Reference Architecture] slideset and related excel sheets with allowed message profiles per Reference Point. 


