# Akamai find-behaviors
This program finds matching behaviors by the given URL path to help identify which behaviors could be applied.  
It should be useful when working with complex property configurations.  

## Install
akamai install https://github.com/Yuta2368/python-akamai-cli-find-behaviors.git  

## Useage
find_behaviors.py [-h] [-a] [-v] [-e EDGERC] [-s SECTION] url_path property_name group_id version behavior_name contractId accountSwitchKey  

This is a program that finds matching behaviors by a given URL.  

positional arguments:  
  url_path              : URL Path  
  property_name         : Property Name  
  group_id              : Group ID  
  version               : Property Version  
  behavior_name         : Property Behavior Name  
  contractId            : ContructID  
  accountSwitchKey      : Account Switch Key  

options:  
  -h, --help            show this help message and exit  
  -a, --all             show all information  
  -v, --verbose         show debug information  
  -e EDGERC, --edgerc EDGERC  
                        Location of the credentials file (default : ~/.edgerc)  
  -s SECTION, --section SECTION  
                        Section of the credentials file (default : default)   
> Tips : GroupID can be obtained from the Property Manager URL    

## Example
#### Command
```
akamai find-behaviors '/path/to/matching/index.html' 'property_name' group_id property_version behavior_name 'contractId' 'accountSwitchKey'
```
#### Output : cpCode
```
Rule: Sample Rule - A
cpCode: {
 "value": {
  "id": 1111111,
  "description": "cpcode - 1111111",
  "products": [
   "Fresca"
  ],
  "createdDate": 1655383350000,
  "cpCodeLimits": null,
  "name": "cpcode-1111111"
 }
}
---
Rule: Sample Rule - B
cpCode: {
 "value": {
  "id": 2222222,
  "description": "cpcode - 2222222",
  "products": [
   "Fresca"
  ],
  "createdDate": 1655383350000,
  "cpCodeLimits": null,
  "name": "cpcode-2222222"
 }
}
---
Rule: default
cpCode: {
 "value": {
  "id": 3333333,
  "description": "cpcode - 3333333",
  "products": [
   "Fresca"
  ],
  "createdDate": 1655383350000,
  "cpCodeLimits": null,
  "name": "cpcode-3333333"
 }
}
---
```

## Update
```
akamai update find-behaviors
```