## LAMP 構築注意点
- MySQL5.6, 5.7
  - バージョンは、group_vars/all の mysql5_minor_version に設定
  - `/root/.my.conf` に MySQL の root ユーザのパスワードを記載
- Apache 2.4.6 (CentOS)
- PHP 5.6
- SELinux は有効
