### Diskutil


* **List all the disk that are plugged to the machine**   
```diskutil list```

* **Force a disk to mount**   
```mount disk1```

* **Check smart status if available**

http://hints.macworld.com/article.php?story=20031122041138373   

diskutil info disk0 | grep SMART

Check the smart status on external drive 
Install
https://github.com/kasbert/OS-X-SAT-SMART-Driver#readme

http://apple.stackexchange.com/questions/52604/can-i-get-s-m-a-r-t-support-on-external-hard-drives


# Disabling spothlight (indexing by mac)   
http://osxdaily.com/2009/09/20/disable-spotlight-in-mac-os-x-10-6-snow-leopard/   
````sudo mdutil -a -i off````

This tells the Spotlight manager to disable all indexing on all volumes, the command will require your administrative password to execute.

Re-enabling Spotlight in Mac OS X 10.6 Snow Leopard is just as easy, just reverse the command to:

````sudo mdutil -a -i on````

Now Spotlight indexing will be back on and work as usual.