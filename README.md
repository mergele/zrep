# ZREP overview
ZREP is a ZFS based replication and failover script from bolthole.com

Got ZFS on two systems? Want to have (almost) idiotproof replication and master/servant switching between them?
Install zrep with a single download and you're almost ready to go.

## Super-Quick-and-dirty quickstart

Step 1: wget https://raw.githubusercontent.com/bolthole/zrep/master/zrep (and make it executable of course. Plus copy it to your second host)

Step 2: zrep -i pool1/prodfs host2 destpool/prodfs

Step 3: (put in cron, every minute if you like)  zrep -S pool1/prodfs

And you're done!  At least with a super-simple implementation.
Note that this is a Korn shell script, so you will need /bin/ksh on your system.

On a [truenas](https://www.truenas.com/) system you can replace the first line with 
```console
#!/usr/local/bin/ksh93 -p
```
credits to https://www.truenas.com/community/threads/zrep-replication-and-failover-script.9966/post-213530

## Full documentation
Many, many more options and features are documented, at

 http://www.bolthole.com/solaris/zrep/zrep.documentation.html

Note that to enable bash commandline completion, an additional download is needed;

sudo wget -O /etc/bash_completion.d/zrep https://raw.githubusercontent.com/bolthole/zrep-completion/master/src/zrep
