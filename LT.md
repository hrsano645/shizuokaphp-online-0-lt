---
theme: "black"
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
  - shizuoka.py
  - Unagi.py
  - Python駿河（結構います）

---

Python駿河/Unagi.py は20日なので、ぜひご参加を！

[Unagi.py 勉強会30枚目～オンラインもくもく読書会～ - connpass](https://unagi-py.connpass.com/event/177428/)

---

もくもく会なのでぶっちゃけPython関係無くてもよいですｗ

もくもくしたい人は、一緒にもくもくしましょう。

---

### 本題

---

年末に 4Kディスプレイを自室(仕事部屋)に導入

---

<4k ディスプレイの画像>

---

MBP2016だと4Kディスプレイでの作業きつすぎる。。

Youtube開くとコマ送りだし。。

MBP 16インチつよつよ構成は高いし。。。(400k yen超えるし)

---

そこでWinのデスクマシンを活用！

- CPU: Corei 5 6200ぐらい
- メモリ: 16GB
- GPU: Radeon RX480

---

< ウィンドウ並べた様子 >

---

とっても快適！4Kディスプレイおススメです！

（メモリが気になりだしてるけど）

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

< MSストアの画像 >

MSストアから手に入ります。（確かMSアカウント必要です）

---

ディストリビューションのエクスポート/インポートもできる

```cmd
wsl --list # インストール済みのディストリビューション一覧が出てくる
wsl --export (ディストリビューション名) [ファイル名]
# tarで固まったファイルができます

```

---

LEMP（と最近言うらしい） Linux, nginx, mysql, phpセットアップ

---

Laravelのセットアップ -> composerを入れて、Laravelのインストール

---

Laravelの環境構築

```bash
php artisan ***

```

---

### ここまでやってみた結果

---

Linuxマシンとほぼ変わらねえ！

資料がUbuntuベースを見てましたが、ほぼ同じでした。

---

Tips:nginxが動くIPは WSL2のターミナルから探します

ubuntu(debian系)なら `ip a` でeth0がNICっぽいです

---

Tips:WSL2のサービス設定

systemdではないっぽい: systemctlとかjournalctlではない
init.dっぽい: serviceコマンドが通りました。

（ググるとWSLからsystemdは動かない状態らしいです -> https://github.com/microsoft/WSL/issues/994）

---

Tips: Windows Terminalも便利

WSL(2)でインストールしたディストリビューションも一覧で出してくれる

---

WSL2でターミナル環境を作って快適なUnix生活を送ろう！

---

# 以上

---

### おまけ

もし余ったら / お茶濁し用

---

WSL2 + VSCode の連携もやってみた

---

WSL2と VSCodeの連携は Remote-WSL拡張機能で実現できます

---

ココ

---

まとめ

---

Win10開発環境にがっつり使えると思う！ WSL2とVSCodeで快適開発環境を目指そう！

---

ちなみにVSCode + Remote-SSHも便利なのでおススメ！

（Remote-Containerも便利だと思われます）

---

終わり