## MariaDB 構築注意点
- MariaDB 10.1
- `/root/.my.conf` に MariaDB の root ユーザのパスワードを記載



PostgreSQL と異なり、MariaDB はパスワードなしユーザに、パスワードを指定してログインしようとするとエラーとなる。

よって、/root/.my.conf を作成した。これで初回でもそれ以降でも mysql モジュールで login_pass の指定が不要となる。

phpMyAdmin のインストールのために、事前に php-devel のインストールは不要だが、php パッケージのインストールは必要だった。。

phpMyAdmin の httpd 設定ファイルの修正は、patch モジュールを使って施すようにした。
このとき、差分のパッチを作るコマンドは次のようにした。

cd /etc/httpd/conf.d/
diff -up phpMyAdmin.conf.org phpMyAdmin.conf > phpMyAdmin.conf.patch

- <a href="http://qiita.com/astro_super_nova/items/e30dcaf4d106deebc63c" target="_blank">Linuxエンジニアらしいパッチのつくりかた - Qiita</a>

設定ファイルの修正内容は、次のページを参考にした。

- <a href="http://qiita.com/100/items/8e9d9540845cc23e6111" target="_blank">CentOS 7 に PHP 7.1 と phpMyAdmin をインストール - Qiita</a>
