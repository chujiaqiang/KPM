# 1. shell knowleages

```shell
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

# 2. process shell variables
let's assume we have a variable：
var='http://www.baidu.com/data'
```
@zdsuateng02:/home/c/h/chujq/> echo ${var%/*}
http://www.baidu.com
@zdsuateng02:/home/c/h/chujq/> echo ${var%%/*}
http:
@zdsuateng02:/home/c/h/chujq/> echo ${var#.*/}
http://www.baidu.com/data
@zdsuateng02:/home/c/h/chujq/> echo ${var#*/}
/www.baidu.com/data
@zdsuateng02:/home/c/h/chujq/> echo ${var##*/}
data
@zdsuateng02:/home/c/h/chujq/> echo ${var/baidu/sina}
http://www.sina.com/data
@zdsuateng02:/home/c/h/chujq/> echo ${#var}
25
```


