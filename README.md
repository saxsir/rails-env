rails-env
===

railsの開発環境を揃えた仮想環境

## Install
```
$ git clone git@github.com:saxsir/rails-env.git
$ cd rails-env
$ vagrant up
```

## Login
```
$ vagrant ssh                                                                                                                                saxsir-mbp.local
vagrant@127.0.0.1's password:
```

password: `vagrant`

本当は公開鍵でログインしてくれるはずなんだが...

refs. [https://github.com/mitchellh/vagrant/issues/5186](https://github.com/mitchellh/vagrant/issues/5186)

### もしvagrant upで以下のエラーが出たら、

```
The following SSH command responded with a non-zero exit status.
Vagrant assumes that this means the command failed!

ARPCHECK=no /sbin/ifup eth1 2> /dev/null

Stdout from the command:

Device eth1 does not seem to be present, delaying initialization.


Stderr from the command:
```

```
$ vagrant ssh
[vagrant]$ sudo ln -s -f /dev/null /etc/udev/rules.d/70-persistent-net.rules
[vagrant]$ exit
$ vagrant reload
```

すると直る。

refs. [http://qiita.com/tarr1124/items/8276e609c0f7cdec79e7](http://qiita.com/tarr1124/items/8276e609c0f7cdec79e7)

## Sample rails app
```
$ cd rails-sample
$ bin/rails s -b 0.0.0.0
```

Open [http://192.168.33.30:3000](http://192.168.33.30:3000) in your browser.

## Environment
```
$ git --version
git version 2.4.6

$ rbenv --version
rbenv 0.4.0-153-g3b6faa8

$ ruby --version
ruby 2.2.2p95 (2015-04-13 revision 50295) [x86_64-linux]

$ nvm --version
0.25.4

$ node --version
v0.12.7

$ npm --version
2.11.3

$ mysql --version
mysql  Ver 14.14 Distrib 5.6.16, for Linux (x86_64) using  EditLine wrapper

$ httpd -version
Server version: Apache/2.2.15 (Unix)
```

## Memo
- passengerもインストール済み & httpd.confに設定も書いてある（コメントアウトしてある）ので、production環境で試したい場合はhttpd.confのpassengerの設定とDocumentRootの設定部分のコメントアウトを外してhttpdを再起動すればOK.
