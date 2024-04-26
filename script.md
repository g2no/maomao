#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

#!/bin/bash

nc localhost 30002 
i=0
until [ $i -gt 9999 ]
 do
 printf "%04d\n" $i
 let i++
 done


pw=/etc/bandit_pass/bandit24
until [ $i -gt 9999 ]
 do
 printf "%s %04d\n" $pw $i
 let i++
 done

