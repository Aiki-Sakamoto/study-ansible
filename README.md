# RailsTutorialの構成をAnsibleで構築させる

## Ansible のインストール
git cloneしたリポジトリで
```
pip install -r requirements.txt
```


## 実行コマンド

ansible-playbookに記述のroleをすべて実行する
```
ansible-playbook -i hosts/production playbook.yml
```

ansible-playbookに記述のroleを指定して実行する(例:nginxのインストール)
```
ansible-playbook -i hosts/production playbook.yml --tags=nginx
```

仮実行コマンド(実際に指定したミドルウェア等はインストールされない。テスト的に実行する際に使用。)
```
ansible-playbook -i hosts/production playbook.yml --check
```

# TODO

* database.ymlやmaster.key等の秘匿ファイルのテンプレート化
* nginx.confのdefault_saverの記述を修正する