* **Reasons why crontab does not work**    
http://askubuntu.com/questions/23009/reasons-why-crontab-does-not-work

Could be : 
* The PATH variable isn't correct (and the given executable couldn't be loaded)
* the cron daemon isn't working
* There is no line break at the end of the crontab file (weird error, note sure it's still important)

***

* **Mail the result of the cron**  
``` 
0 7 * * *  /home/user/backup/travail/synchro.sh | mail 'synchro prod89' mymail@gmail.com
```


http://stackoverflow.com/questions/1396506/cron-send-email-with-stderr-but-not-stdout
> For cron you don't need to pipe through mail. The cron daemon will automatically mail any output of your command to you. Your crontab entry should look like:

# every minute
* * * * * ./prog >/dev/null
If there is no STDERR output, you won't get any mail.

***

### Tuto

https://help.ubuntu.com/community/CronHowto