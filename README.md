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

## Usage
You find Skillet Collections organised per usecase, e.g. a RAN usecase or a ROAMING usecase. Inside each Collection the 3GPP reference point is represented with an individual Skillet. Build your Security Policy by adding together the Skillets you need, each Skillet creates one Rule.
Along that Security Policy Rule, the Skillet might create anything else it requires to activate the Rule in PanOS. This is, at least:
- Security Zones (red=external untrust, blue=own trust, black=own untrust)
- one tag for each Zone (red/blue/black)
- one address object for each end of the Reference Point
Make sure you have the **latest version** of the [Reference Architecture] slideset and related excel sheets with allowed message profiles per Reference Point.
#### Combining Skillets  
To provide better modularity of the loosely related 3GPP Skillets, elements used in a rule (like Vulnerability/Protection Profiles, tags etc) are re-created  with every individual Skillet, even within the same Collection. Eventually this might create errors and require to edit the .meta-cnc.yaml files. This is unfortunate but creation of a common baseline and ensuring high accuracy of the messaging profiles take precedence over comfort in automation for this project.
For the Reference Skillets each possible NIC on a Service Node / Server is created only **ONCE** with an index "--0" at the end of it's unique NIC/Object name. Additional instances --[X] as indicated in the Reference Architecture Slideset can be instanciated. In order to create a larger amount of Address Objects or apply additional XML snippets one could use the unofficial and somewhat crude [SkilletStamper](https://github.com/pennersm/SkilletStamper) . Other means of Object creation automation might be found via Panorama. However, a baseline of mandatory SP settings as well as good general practice are given in the sanctioned and official [MobileSkillet](https://github.com/PaloAltoNetworks/MobileSkillet)



