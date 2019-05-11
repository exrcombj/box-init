# box-init

## add aws ec2  
* select AMI linux
* security group add http and https protocol

## manual install git
```
mkdir ~/dev
sudo yum update -y
sudo yum install git -y
```

## setup box
```
cd ~/dev
git clone https://github.com/exrcombj/box-init.git
cd box-init && source init_box.sh
## logout and login again
```

## install mediawiki
```
source ~/dev/box-init/install_mediawiki.sh
```
### backup mediawiki xml
* https://www.mediawiki.org/wiki/Manual:DumpBackup.php
```
php dumpBackup.php --full > dump.xml
```
### import backup xml
* https://www.mediawiki.org/wiki/Manual:Importing_XML_dumps

```
php importDump.php --conf ../LocalSettings.php /path_to/dumpfile.xml.gz
# or
php importDump.php < dumpfile.xml
```
access /index.php/Special:AllPages
may need restore /index.php/Main_Page 
