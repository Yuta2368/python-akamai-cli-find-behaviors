# Akamai find-behaviors
This program finds matching behaviors by the given URL path to help identify which behaviors could be applied. It should be useful when working with complex property configurations.  
This program handles two types of behaviors described below.  
#### behavior_name
- cpCode (Content Provider Code)
- caching (Caching)

## Install
akamai install https://github.com/Yuta2368/python-akamai-cli-find-behaviors.git  

## Setup
### Account file
Create "Account file" on your current directory.  
```
vi account.ini
```
```
# account.ini
[account]  
contractId=your_contract_ID  
accountSwitchKey=your_account_switch_key  
```

## Useage
usage: find_behaviors.py [-h] [-a] [-v] url property_name version behavior_name account_file  

This is a program that finds matching behaviors by given URL.  

positional arguments:  
  url            : URL Path  
  property_name  : Property Name  
  group_id       : Group ID
  version        : Property Version  
  behavior_name  : Property Behavior Name  
  account_file   : Path to the file for "contractId and accountSwitchKey"   

options:  
  -h, --help     show this help message and exit  
  -a, --all      show all information  
  -v, --verbose  show debug information  
  -e EDGERC, --edgerc EDGERC Location of the credentials file (default : ~/.edgerc)  
  -s SECTION, --section SECTION Section of the credentials file (default : default)  
> note : GroupID can be obtained from the Property Manager URL  

## Example
#### Command
```
akamai find-behaviors /path/to/matching/index.html property_name group_id property_version behavior_name path_to_account.ini
```
#### Output : cpCode
```
Rule: AAAAA
cpcode: 1111111
---
Rule: BBBBB
cpcode: 2222222
---
Rule: CCCCC
cpcode: 3333333
---
Rule: default
cpcode: 4444444
---
```

## Update
```
akamai update find-behaviors
```