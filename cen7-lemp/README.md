## LEMP 構築注意点
- Nginx (http://nginx.org リポジトリの安定版)
- MariaDB 10.1
- `/root/.my.conf` に MariaDB の root ユーザのパスワードを記載
- PHP 7
- php-fpm
- PHP のエラーは、`/var/log/php-fpm/error.log` に出力される。
- SELinux は有効
