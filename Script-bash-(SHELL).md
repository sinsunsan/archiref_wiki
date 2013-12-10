### Defining a variable and using it 

When defining there is no $, when using prefixed with $
```
file=$DATE'_bak_log'
filetar $dir $file '/var/log' $DATE
```

### Date variable 

We save the current date in a variable
```SHELL
DATE=`date +%Y_%m_%d_%Hh%M`
```

### Passing argument to a function 
$1 $2 $3 are argument passed in that order
```SHELL
filemanip(){
  #$1 Le repertoire de sauvegarde $dir
  #$2 Le nom du fichier de sauvegarde $file
  #$3 La variable $DATE qui sert à horodater les fichiers
  date=$3
  bkfile=$1'/'$2
  bkdir=$1
  #Fait un checksum du fichier et l'ajoute à un fichier des checksums
  md5sum $bkfile >> $bkdir/$date'_bak_md5checksum.txt'
  #On écrit d'autres infos dans un fichier txt
  #Le nom du fichier qui vient d'être backupé
  echo $bkfile'  '  >> $bkdir/$date'_bak_backup_report.txt'
  #La taille de ce fichier
  du -sh $bkfile >>  $bkdir/$date'_bak_backup_report.txt'
  #Saut de ligne existe peut etre plus simple
  echo " " >>   $bkdir/$date'_bak_backup_report.txt'
}
```

### Small backup script

All bash files start with #! /bin/sh

```
#! /bin/sh

# On stocke la date dans la variable DATE
date1=`date +%Y_%m_%d_%Hh%M`
disk1=/Volumes/SEB_BACKUP1
disk2=/Volumes/SEB_BACKUP2


# que 00_backup et BIBLIO
 touch $disk2/log/$date1
 rsync -av --force --delete --exclude * --include BIBLIO --include 00_backup /Volumes/SEB_WORK/ $disk2/SEB_WORK

# Sauvegarde du MAC
```

### Test if a file exist and load it 

```
if [ -f ~/.bash/bashrc.local ]; then
    source ~/.bash/bashrc.local
fi
```

# Debug a script in verbose mode 
http://stackoverflow.com/questions/956213/verbose-output-of-shell-script
```
sh -x script_name
```
