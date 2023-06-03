# Akamai find-behaviors
This program finds matching behaviors by given URL path to help identify which behaviors could be applied. It should be useful when working with complex property configs.  
This program takes two kinds of behaviors below.  
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
groupId=your_group_id (starts with "grp_")  
accountSwitchKey=your_account_switch_key  
```

## Useage
usage: find_behaviors.py [-h] [-a] [-v] url property_name version behavior_name account_file  

This is a program that finds matching behaviors by given URL.  

positional arguments:  
  url            : URL Path  
  property_name  : Property Name  
  version        : Property Version  
  behavior_name  : Property Behavior Name  
  account_file   : Path to the file for "contractId / groupId / accountSwitchKey" information   

options:  
  -h, --help     show this help message and exit  
  -a, --all      show all information  
  -v, --verbose  show debug information  

## Example
#### Command
```
akamai find-behaviors /path/to/matching/index.html property_name property_version behavior_name path_to_account.ini
```
#### Output
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