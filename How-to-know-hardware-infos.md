http://programmingbulls.com/how-know-your-ram-linux-machine#.UJ4hd2n3tGs

```
cat /proc/meminfo
```

Files in proc are virtual files that show updated infos when we ask it.

-r--r--r--  1 root       root         0 2012-11-10 10:47 buddyinfo
-r--r--r--  1 root       root         0 2012-11-10 10:47 cpuinfo
-r--r--r--  1 root       root         0 2012-11-10 10:47 meminfo
-r--r--r--  1 root       root         0 2012-11-10 10:47 pagetypeinfo
-rw-r--r--  1 root       root         0 2012-11-10 10:47 slabinfo
-r--------  1 root       root         0 2012-11-10 10:47 vmallocinfo
-r--r--r--  1 root       root         0 2012-11-10 10:47 zoneinfo