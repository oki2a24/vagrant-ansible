## Grails 構築注意点
- SDKMAN! を全ユーザが使えるようにインストールする。
- SDKMAN! を使って JDK および Grails をインストールする。
  - [ansible/group_vars/all](ansible/group_vars/all) にてバージョンを指定する。指定無しの場合は最新版をインストールする。
- Grails プロジェクトは未作成の状態。
- [2 Getting Started 3.2.11](http://docs.grails.org/latest/guide/gettingStarted.html) のチュートリアルまで確認した。
- http://xxx.xxx.xxx.xxx:8080 でアプリにアクセスできる。`run-app` を `run-app -host xxx.xxx.xxx.xxx` と host オプションの指定は不要。

## MariaDB 構築注意点
- MariaDB 10.1
- phpMyAdmin をインストールする。
  - http://xxx.xxx.xxx.xxx/phpMyAdmin
  - http://xxx.xxx.xxx.xxx/phpmyadmin
