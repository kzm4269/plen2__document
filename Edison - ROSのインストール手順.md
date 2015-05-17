作業環境
================================================================================
- Windows 8.1 Professional Edition.


Edison - ROSのインストール手順
================================================================================

## 1. Edison用ドライバのインストール
[Intelの公式配布ページ](http://www.intel.com/support/edison/sb/CS-035180.htm)から、
ドライバをダウンロードします。(最新版のドライバを入れておく必要があります。)

## 2. Debianイメージの取得
[ubilinuxの公式配布ページ](http://www.emutexlabs.com/ubilinux)から、
Edison用のDebianイメージをダウンロードします。

これを解凍し、任意のフォルダに展開しておきます。

## 3. dfu-utilの取得
[コミュニティサイト](https://community.particle.io/t/latest-2014-dfu-util-for-windows-compiled/5264)から、
イメージの転送ソフトをダウンロードします。

## 4. Debianイメージの書き込み
1. ***toFlash***ディレクトリ内に、3.でダウンロードした***dfu-util.exe***を設置します。
2. ***flashall.bat***内のコメントアウト行を、***cmd.exe***に合わせて**"rem"**に書き換えます。  
   (この作業を行わないと、バッチファイルの実行時にエラーがでます。)
3. ***flashall.bat***を実行したのち、EdisonをPCに接続します。
4. 転送処理の開始に成功すると、プロンプト上にログが表示されます。(そのまま10分ほど待機してください。)

## 5. Edisonとのシリアル接続
FTDI制御マイコンの実装されている側のUSBポートへ、USBケーブルを接続します。
その後、TeraTermなどのターミナルエミュレータを用いて、認識されたCOMポートに**baudrate 115200**で接続します。

```
root [Enter]
edison [Enter]
```

以上のように入力し、rootユーザへログインします。

## 6. ネットワークの設定
初期状態では、**usb0**がデフォルトゲートウェイを握っているため、インターネット接続ができません。
まずはこれを**wlan0**へと変更します。

```
vi /etc/network/interfaces [Enter]
```

以上のように入力し、ネットワークの設定ファイルを開きます。

// fix me.

## 7. ユーザの作成
// fix me.

## 8. sudoのインストール
// fix me.

## 9. ROSのインストール
[解説サイト](http://martinkronberg.com/new-blog/2015/3/18/ros-on-intel-edison-using-ubilinux-and-porting-to-yocto)を参考に、
ROSのインストールを行います。(バックアップを考慮して、日本語で再執筆するかもしれません。)