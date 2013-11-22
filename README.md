ruckus-zdroamers
================

zdroamers script:
find top roamers in ruckus syslog info (and more!)

Install this script under the name /var/log/zdroamers on your linux syslog box.
It will tell you what devices are roaming between APs the most

WARNING: This script has many features.
There are probably many ways to break it.
Don't expect perfection.



    /var/log# ./zdroamers --help
    Usage:
    ./zdroamers [OPTIONS] [<var/log/messagefile>]

    Produce a list of client MAC addresses sorted by number of "roaming event" log entries
    (or use options to dump raw log information)
    note: there are 2 log entries per roaming event
    
    OPTIONS:
    --help -? -h
    --controller <controlleraddress> ;# filter on the IP of the specified controller
    --client <mac:ad:dr:es:s>        ;# filter on client mac address
    --highlight           ;# make "--client" option highlight mac addresses, not filter them
    --maxoui <n>          ;# set the number of roam messages that triggers an oui lookup
    --nslookup            ;# if --maxoui was specified, attempt to nslookup the clients
    --ap <mac:ad:dr:es:s> ;# filter on AP mac address
    --detail           ;# output raw (colorized) data instead of counting roaming lines per MAC
    --last <linecount> ;# only use the last "linecount" number of lines from "messages"
    --now   ;# only report on new log entries as they are received. implies "--detail" option
    --debug ;# turn on debugging output
