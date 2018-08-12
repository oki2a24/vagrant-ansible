## LEMP 構築注意点
- Nginx (http://nginx.org リポジトリの安定版)
- MariaDB 10.1
- `/root/.my.conf` に MariaDB の root ユーザのパスワードを記載
- PHP 7
- php-fpm
- PHP のエラーは、`/var/log/php-fpm/error.log` に出力される。
- SELinux は有効

yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm

yum repolist all | grep mysql
yum install yum-utils
yum-config-manager --disable mysql80-community
yum install mysql-community-server --enablerepo=mysql57-community

root パスワードはインストール時にランダム文字列が設定され、それの変更は Ansible mysql_user モジュールではできなかった。また、ランダム文字列のパスワードをそのままルートパスワードとしても設定できなかった。
結局、次のページのやり方で、shell を使用して設定した。
- <a href="https://qiita.com/da-sugi/items/03cf3a1bc434137f4c30" target="_blank">【Ansible】Mysql5.7でrootユーザのパスワードを再設定etc... - Qiita</a>
