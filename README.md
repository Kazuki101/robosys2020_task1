# Robosys2020 課題1
Raspberry Pi4Bを用いてLED2個を点灯や点滅させるデバイスドライバを作成しました。
![picture](https://github.com/Kazuki101/robosys2020_task1/blob/main/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%20(912).png)
## 実行環境
|OS|Ubuntu20.04 server|
|:---|:---|
|Raspberry Pi|Raspberry Pi 4 Model B 4GB|
## 回路説明
ピン配置は以下の通りである。また, LED1とLED2のカソードはそれぞれ任意のGNDに挿してください。
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
## 動画のリンク
https://www.youtube.com/watch?v=1G28HtAUfmE&feature=youtu.be
