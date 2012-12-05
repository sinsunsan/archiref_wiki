* Reasons why crontab does not work    
http://askubuntu.com/questions/23009/reasons-why-crontab-does-not-work

Could be : 
* The PATH variable isn't correct (and the given executable couldn't be loaded)
* the cron daemon isn't working
* There is no line break at the end of the crontab file (weird error, note sure it's still important)

* Mail the result of the cron    
0 7 * * *  /home/user/backup/travail/synchro.sh | mail 'synchro prod89' mymail@gmail.com


### Tuto

https://help.ubuntu.com/community/CronHowto