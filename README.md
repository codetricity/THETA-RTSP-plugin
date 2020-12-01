# Overview
This is a Live Streaming Plug-in for the RICOH THETA V and Z1.  It starts an RTSP
server on the THETA.

This software was developed by Science Arts.  The THETA V plug-in is available in the
[plug-in store](https://pluginstore.theta360.com/plugins/com.sciencearts.rtspstreaming/).

## Usage

You can open and play the RTSP Stream from RTSP client tool like VLC.

1. Set RICOH THETA in Wireless LAN client mode.

Video: https://www.youtube.com/watch?v=tkqyBNOWWIY&t=9s
Manual:https://theta360.com/en/support/manual/v/content/prepare/prepare_08.html

2. In the basic app for smartphone, select "Settings" > "Camera settings" and set "THETA RTSP Streaming" in "Plug-in", then tap the icon displayed next to "Starting plug-in".

If the application is launched successfully, video LED on RICOH THETA turns on.

3. Find out and remember the IP Address of RICOH THETA.

i. Open the basic app for smartphone.
ii. select "Setting" > "Camera setting" > "Camera version", then get IP Address.

---

Original readme in Japanese.

# 開発環境
Android Studio

# インストール
Android Studioを使用し、本アプリケーションをビルドしインストールしてください。

# 準備

1. Vyserなどのデスクトップビューツールを使用して、本アプリケーションのPermissionを許可してください。
1. [SmartPhone app > Basic app](https://support.theta360.com/en/download/)をインストールしてください。

# 使い方

1. THETAカメラの電源ボタンを押し、THETAを起動してください。
1. SmartPhon appより、Thetaを[Wireless-LAN　client mode]((https://support.theta360.com/uk/manual/v/content/prepare/prepare_08.html))に設定してください。（wireless-LAN LEDが緑色に点灯）
1. SmartPhon appの設定 > カメラ設定 > プラグイン　より本プラグインを選択してください。
1. THETAカメラのモードボタンを長押しし、プラグインを起動してください。
1. 正常に起動すると、VIDEO LEDが点灯状態、白色のLEDが点灯状態になります。このとき、RTSPサーバーが起動されています。
1. vlcなどお好みのRTSPクライアントツールよりTHETA RTSP Serverにアクセスしてください。
```
rtsp://[TEATA IP ADDRESS]/live?resolution=1920x960
```

THETA IP ADDRESS: THETAカメラのIPアドレス

THETAカメラのIPアドレスはSmartPhon appより確認できます。

resolution パラメータにて解像度の指定ができます。
640x320,1024x512,1920x960,3840x1920のいづれかを設定できます。
ただし、3840x1920は十分なストリーミングスピードが得られません。

# 注意事項
本RTSPサーバーはユニキャストのみ対応となっています。

resolutionパラメータより、解像度を変更する場合は TEARDOWN リクエスト送信後、新しいrtspセッションを開始するようにしてください。（vlcを使用する場合はStop Play Backボタン押下後、新しいセッションを開始してください。）

