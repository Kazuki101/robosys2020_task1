# Robosys2020 課題1
Raspberry Pi4Bを用いてLED2個を点灯や点滅させるデバイスドライバを作成しました。
## 実行環境
|OS|Ubuntu20.04 server|
|:---|:---|
|Raspberry Pi|Raspberry Pi 4 Model B 4GB|
## 実行手順
### ドライバのインストール
    $git clone https://github.com/Kazuki101/robosys2020_task1.git
    $cd robosys2020_task1
### ビルド
    $make
    $sudo insmod myled.ko
    $sudo chmod 666 /dev/myled0
### 実行
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
