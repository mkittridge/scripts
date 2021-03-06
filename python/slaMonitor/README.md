# Monitor Missed SLAs using Python

Warning: this code is provided on a best effort basis and is not in any way officially supported or sanctioned by Cohesity. The code is intentionally kept simple to retain value as example code. The code in this repository is provided as-is and the author accepts no liability for damages resulting from its use.

This python script finds missed SLAs for recent job runs

## Components

* slaMonitor.py: the main python script
* pyhesity.py: the Cohesity REST API helper module

You can download the scripts using the following commands:

```bash
# download commands
curl -O https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/python/slaMonitor/slaMonitor.py
curl -O https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/python/pyhesity.py
chmod +x slaMonitor.py
# end download commands
```

Place both files in a folder together and run the main script like so:

```bash
./slaMonitor.py -v mycluster -u myuser -d mydomain.net
```

## Parameters

* -v, --vip: DNS or IP of the Cohesity cluster to connect to
* -u, --username: username to authenticate to Cohesity cluster
* -d, --domain: (optional) domain of username (default is local)
* -s, --mailserver: SMTP gateway to forward email through
* -p, --mailport: (optional) defaults to 25
* -f, --sendfrom: email address to show in the from field
* -t, --sendto: email addresses to send report to (use repeatedly to add recipients)
* -b, --maxbackuphrs: (optional) defaults to 8
* -r, --maxreplicationhrs: (optional) defaults to 12
* -w, --watch: (optional) all, backup or replication (defaults to all)

## The Python Helper Module - pyhesity.py

The helper module provides functions to simplify operations such as authentication, api calls, storing encrypted passwords, and converting date formats. The module requires the requests python module.

Please see here for more information: <https://github.com/bseltz-cohesity/scripts/tree/master/python#cohesity-rest-api-python-examples>
