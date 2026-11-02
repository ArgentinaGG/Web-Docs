Commands
========
```sh
/usr/local/ispconfig/server/server.sh

service mariadb restart
service httpd restart
service pure-ftpd restart
service postfix restart

git checkout -- file.xxx

echo > ~/.bash_history ; history -c
# delete single line:
history -d 1234 ; history -w

cat /var/log/secure | grep "Accepted password"

* * * * *   root    pgrep httpd > /dev/null || /bin/systemctl start httpd.service
* * * * *   root    pgrep mariadb > /dev/null || /bin/systemctl start mariadb.service
* * * * *   root    pgrep supervisor > /dev/null || /bin/systemctl start supervisor
0 4 * * *   root    /bin/systemctl restart mariadb.service

mysql -V
httpd -v
php -v
cat /etc/*release*

nano /etc/my.cnf
nano /etc/httpd/conf/httpd.conf
nano /etc/php.ini
nano /etc/postfix/main.cf

tail -100 /var/log/mysqld.log
tail -100 /var/log/httpd/error_log
tail -100 /var/log/mariadb/mariadb.log

scp file.tar.gz user@domain.net:/home/user
scp -r plugins user@domain.net:/home/user

scp -r user@your.server.example.com:/path/to/foo /home/user/Desktop/

rsync -ruvt --delete folder user@222.222.222.222:/data

bash-4.2# sudo /sbin/reboot --force
```

FIX BITBUCKET
```sh
sudo -u web115 git pull
sudo echo > /var/www/site.com/.ssh/known_hosts
sudo -u web115 ssh-keygen -R bitbucket.org && curl https://bitbucket.org/site/ssh >> /var/www/site.com/.ssh/known_hosts
```

Git go back to last commit 
```sh
# 1. Discard changes to existing files
git reset --hard HEAD

# 2. Remove any newly created untracked files and folders
git clean -fd
```

Reset file changes
```sh
git checkout -- file.xxx
```

show top 10 biggest subdirs in the current dir

```sh
du -sk * | sort -nr | head -10

df -h
```

Find files with specific size (bytes)
```sh
find /var/www/web.me/web/ -type f -size 85796c -exec ls -lh {} \;
```
```sh
find /var/www/web.me/web/ -type f -size +85550c -size -86000c -exec ls -lh {} \;
```

Find files with specific text within
```sh
grep -rnw '/path/to/somewhere/' -e 'pattern'
```

Bind /etc/fstab (web/wordpress/ispconfig - systemctl daemon-reload if reload needed)
```sh
/var/www/clients/client1/web1/web /var/www/clients/client1/web2/web    none    bind,nobootwait,_netdev    0 0
mount -a
```

Comprimir tar.gz
```sh
tar -zcvf backup_2012.tar.gz directory-name
```

Descomprimir tar.gz
```sh
tar -zxvf  backup_2012.tar.gz
```

Search repo rpm and delete (to solve yum conflicts)
```sh
rpm -qa | grep -i repo-name
rpm -e repo-name
```
