* -a copy owner -o - permission -p and -g group -rlptgoD
* to juste synchronise files but allow different permission, owner and group set -rltD
* r recursive 
* l  -l, --links                 copy symlinks as symlinks
*  -t, --times                 preserve modification times
*  -D                          same as --devices --specials
* -g, --group
* -o, --owner
* -k transform symlinks in source directory to plain directory in destination (used by drush rsync)

*  so to copy permission but not the owner and group 
Useful when rsyncing from a mac and having different user and group on the local mac, and the remote server
rltDp

* To Exclude a bunch of files, use **exclude-from** directive    

How the order is interpreted   
http://stackoverflow.com/questions/7960669/with-rsync-how-do-includes-and-excludes-combine   
How is the syntax   
http://www.hyperorg.com/blogger/2008/05/10/beginner-to-beginner-rsync-exclude-from/