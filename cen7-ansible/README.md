## 注意点
- コントロールノード: Ansible を実行するサーバ
  - `vagrant up` で構築される仮想マシンです。
- ターゲットノード: Ansible によって構築される側のサーバ。別途用意してください。
  - ターゲットノードは 192.168.56.11 とします。
  - ターゲットノードに vagrant ユーザがいるとします。
- Ansible 実行前に、ターゲットノードにコントロールノードから SSH 公開鍵を登録してください。

## SSH 公開鍵の登録手順
`vagrant up` でコントロールノードの仮想マシンを作成したら、コントロールノード上でターゲットノードに対して SSH 公開鍵を登録してください。
```bash
# SSH 公開鍵の作成
# 次を質問される
# Enter file in which to save the key (/home/vagrant/.ssh/id_rsa):
# Enter passphrase (empty for no passphrase):
# Enter same passphrase again:
ssh-keygen -t rsa

# ターゲットノードへの SSH 公開鍵の登録
ssh-copy-id -o StrictHostKeyChecking=no -i $HOME/.ssh/id_rsa.pub vagrant@192.168.56.11
```

## Ansible プレイブックの実行手順
SSH 公開鍵をターゲットノードへ登録したら、次の操作で Ansible の疎通確認が可能です。
```bash
cd ~/playbook/
# プレイブックを使用しないで疎通確認
ansible 192.168.56.11 -m ping
# プレイブックを使用しての疎通確認
ansible-playbook -i hosts test.yml
```
