---
theme: "black"
transition: "slide"
title: "shizuoka.php online #0 LT WSL2でPHPを体験してみた話"
---

### WSL2でPHPを体験してみた話

shizuoka.php online #0 LT

佐野浩士

---

### お前誰よ

佐野浩士 twitter@hrs_sano645

- 静岡県富士市在住
- Pythonの勉強会とかによくいます
  - `shizuoka.py
  - Unagi.py
  - Python駿河（結構います）

---

Python駿河/Unagi.py は20日なので、ぜひご参加を！

[Unagi.py 勉強会30枚目～オンラインもくもく読書会～ - connpass](https://unagi-py.connpass.com/event/177428/)

---

もくもく会なのでぶっちゃけPython関係無くてもよいですｗ

もくもくしたい人は、一緒にもくもくしましょう。

---

宣伝終わり🙇‍♂️

---

### 本題

---

年末に 4Kディスプレイを自室(仕事部屋)に導入

---

<4k ディスプレイの画像>

---

MBP2016だと4Kディスプレイでの作業きつすぎる。。

Youtube開くとコマ送りだし。。

MBP 16インチつよつよ構成は高いし。。。
(400k Yen超えるし)

---

そこでWinのデスクマシンを活用！

- CPU: Corei 5 6200ぐらい
- メモリ: 16GB
- GPU: Radeon RX480

---

![< ウィンドウ並べた様子 >](./img/slideimg_1.jpg)

---

とっても快適！4Kディスプレイおススメです！


---

問題として: macOSでやってたUnixな作業がしづらい。。

---

Windows Subsystem for Linu2（WSL2）

正式リリース🎉

---

WSL2が正式版になったので、インストールして使ってみよう

---

shizuoka.phpなのでlaravelのインストールまでやってみよう

---

やった作業

- Windows 10 2004へアップデート
- WSL2のセットアップ
- LEMP, Laravelのセットアップ

---

WSL2のセットアップ:ここ見れば普通にできます。

-> 

今後はカーネルの提供がWindows Update経由になる話があるので、ちょっと変わるかも？

---

OSはUbuntu 20.04を利用

MSストアから手に入ります（MSアカウント必要）

![ubuntu20.04 ms store](./img/slideimg_2.jpg)


---

ディストリビューションのエクスポート/インポートもできる

```cmd
wsl --list # インストール済みのディストリビューション一覧が出てくる
  NAME            STATE           VERSION
* Ubuntu-20.04    Running         2
  Legacy          Stopped         1

wsl --export (ディストリビューション名) [ファイル名]
# tarで固まったファイルができます
# wsl --export Ubuntu-20.04 ub2004-wsl2-20200616

```

---

LEMP（と最近言うらしい） Linux, nginx, mysql, phpセットアップ

[How To Install Linux, Nginx, MySQL, PHP (LEMP stack) on Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04)

Step3まで進めました

---

Laravelのセットアップ -> composerを入れて、Laravelのインストール

[How To Install and Use Composer on Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04)　Step2まで


[How To Install and Configure Laravel with Nginx on Ubuntu 20.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-laravel-with-nginx-on-ubuntu-20-04)

---

### ここまでやってみた結果

---

Linuxマシンとほぼ変わらねえ！


（資料がUbuntuベースを見てましたが、ほぼ同じでした。）

---

### Tips:nginxが動くIP

WSL2のターミナルから探します

ubuntu(debian系)なら `ip a` でeth0がNICっぽいです

```bash
$ ip a
# ～～前略～
5: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:b0:18:d9 brd ff:ff:ff:ff:ff:ff
    inet 172.22.54.15/20 brd 172.22.63.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:feb0:18d9/64 scope link 
       valid_lft forever preferred_lft forever
```


---

### Tips:WSL2のサービス設定

- systemdではないっぽい: systemctlとかjournalctlではない

- init.dっぽい: serviceコマンドが通りました

（ググるとWSLの時代からsystemdは動かない状態らしい -> https://github.com/microsoft/WSL/issues/994）

---

### Tips: Windows Terminalも便利

WSL(2)でインストールしたディストリビューションも一覧で出してくれる

![windows terminal](./img/slideimg_3.jpg)

---

# まとめ

---

WSL2でターミナル環境を作って<br>
快適なUnix生活を送ろう！

---

# 以上

---

### おまけ

もし余ったら / お茶濁し用

---

WSL2 + VSCode の連携もやってみた

---

WSL2と VSCodeの連携は Remote-WSL拡張機能で実現できます

[Remote - WSL - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)

---

![remote-wsl](./img/slideimg_4.png)

---

# まとめ

---

Win10開発環境にがっつり使えると思う！<br>
WSL2とVSCodeで快適開発環境を目指そう！

---

ちなみに、VSCode + Remote-SSHも便利なのでおススメ！

（Remote-Containerも便利だと思われます）

---

終わり