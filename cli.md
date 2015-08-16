# Shell Commands
Various commands worth noting.


Find out the amount of data waiting to be 
written to disk. (How much data would I lose if I lost all power right _now_:
`grep ^Dirty /proc/meminfo`


### Display source repository from which the package was installed

 `apt-cache policy packagename`


### Find Ubuntu Version
>ie: If you are on Ubuntu 12.04 then the output should be `precise'

awk '{print }' /etc/*-release |grep -o -e '[[:alpha:]]' |tr . |sed 's/\.//g' |grep -e '[[:graph:]]'
