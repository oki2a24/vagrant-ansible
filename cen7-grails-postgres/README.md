## Grails PostgreSQL 構築注意点
## Grails
- SDKMAN! を全ユーザが使えるようにインストールする。
- SDKMAN! を使って JDK および Grails をインストールする。
  - [ansible/group_vars/all](ansible/group_vars/all) にてバージョンを指定する。指定無しの場合は最新版をインストールする。
- Grails プロジェクトは未作成の状態。
- [2 Getting Started 3.2.11](http://docs.grails.org/latest/guide/gettingStarted.html) のチュートリアルまで確認した。
- http://ipadress:8080 でアプリにアクセスできる。`run-app -host xxx.xxx.xxx.xxx` というように **`run-app` は host オプションを指定して実行すること。**

## PostgreSQL
- PostgreSQL 9.x をインストールする。
- 9.2 から 9.6
- 例えば `pg_minor_ver_num: 6` と指定すれば 9.6
- phpPgAdmin もインストールする。
  - http://ipadress/phppgadmin/
  - http://ipadress/phpPgAdmin/

## Vim
- プラグインマネージャは、dein.vim を使用する。
- カラースキームとして、altercation/vim-colors-solarized を使用する。
- Vim 設定は、全ユーザに適用する。
- [2 Getting Started 3.3.0](http://docs.grails.org/latest/guide/gettingStarted.html#ide) で紹介されている、[Using VIM as your Grails IDE Part 1: Navigating your project | Object Partners](https://objectpartners.com/2012/02/21/using-vim-as-your-grails-ide-part-1-navigating-your-project/) のページの Vim プラグインを導入する。
