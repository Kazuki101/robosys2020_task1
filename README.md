# Robosys2020 課題1
Raspberry Pi4Bを用いてLED2個を点灯や点滅させるデバイスドライバを作成しました。
## 実行環境
|OS|Ubuntu20.04 server|
|:---|:---|
|Raspberry Pi|Raspberry Pi 4 Model B 4GB|
## 回路説明
ピン配置は以下の通りである。また, GNDは任意のところで使用できます。
|LED1 アノード|GPIO 25|
|:---|:---|
|LED2 アノード|GPIO 24|
## 実行手順
### ドライバのインストール
    $git clone https://github.com/Kazuki101/robosys2020_task1.git
    $cd robosys2020_task1
### ビルド
    $make
    $sudo insmod myled.ko
    $sudo chmod 666 /dev/myled0
### 実行
myled.c内のfor文の上限数を変えることでecho1～3のそれぞれで点滅する回数を任意に変更することが可能です。  
※ここで無限ループにしてしまうとechoを送った場合に点滅を無限に繰り返して操作を受け付けなくなってしまうので, もしやってしまった場合はmake cleanで一度消してビルドの段階からやり直してください。
#### LED1 点滅
`$echo 1 > /dev/myled0`
#### LED2 点滅
`$echo 2 > /dev/myled0`
#### LED1とLED2を同時に点滅
`$echo 3 > /dev/myled0`
#### LED1 点灯
`$echo 4 > /dev/myled0`
#### LED2 点灯
`$echo 5 > /dev/myled0`
#### LED1とLED2を同時に点灯
`$echo 6 > /dev/myled0`
#### LED1とLED2を同時に消灯
`$echo 0 > /dev/myled0`
### モジュールのアンロード
`$sudo rmmod myled`
