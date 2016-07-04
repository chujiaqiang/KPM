# 1. shell knowleages

```
#!/usr/bin/bash

if [ $# != 0 ] && [ "$1" != "default" ]; then
        echo -n "$1"
        exit 0
fi

#week number
week_number=$(date +%w)
if [ $week_number -le 4 ]; then
        interval=$(( -1*($week_number+4) ))
else
        interval=$(( -1*($week_number-3) ))
fi

echo -n $(date -d "$interval day" +%Y%m%d)

exit 0

```
