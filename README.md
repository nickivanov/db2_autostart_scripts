% DB2 init.d scripts for Linux
% Nick Ivanov
% 1 Sep. 2013

## DB2 init.d scripts for Linux

Unlike the IBM "standard" method of relying on the DB2 Fault Monitor to start
(and restart) DB2 instances, these scripts obtain the list of instances, along
with their "start at boot" flags, from the DB2 global registry file. 

The registry is updated by the DB2 install scripts and the instance creation
utility, **db2icrt**. By default all instances are set to start at boot time, 
you can disable them selectively by running the **db2greg** utility:

    db2greg -updinstrec instancename=db2inst1!startatboot=0
    
Currently only these commands are supported: start, stop, status.

Two flavours are available: one for the SuSE Linux, another for Red Hat
Enterprise Linux.
