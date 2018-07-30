# Add a VM to a Cohesity Protecvtion Job using Python

Warning: this code is provided on a best effort basis and is not in any way officially supported or sanctioned by Cohesity. The code is intentionally kept simple to retain value as example code. The code in this repository is provided as-is and the author accepts no liability for damages resulting from its use.

This python script adds a VM to an existing protection job.

## Components

* protectVM.sh: the main python script
* pyhesity.py: the Cohesity REST API helper module

Place both files in a folder together and run the main script like so:

```bash
./protectVM.sh -v bseltzve01 -u admin -vm mongodb -job 'vm backup'
Connected!
adding MongoDB to VM Backup job...
```