# ロボットシステム学 − 救済措置課題
鷲尾弘希
## 概要
LEDが2回光るプログラムで、入力する数字(1~9)によってLEDの点灯時間が変わる
設定した数字の秒数だけ光る。
例）3を設定するとLEDが3秒光った後に一回消えてもう3秒光るということ。
pinコードはGPIO25とGNDを使用しています。
## 動画
- URL − 
## 使用するもの
- Raspberry Pi 4 Model B
  - ubuntu 18.04 LTS
- LED
- 抵抗：220[Ω]
## 使い方
1. リポジトリをクローンしてローカルリポジトリの作成
   ```
   $ git clone https://github.com/nyannkoww/robosys_2020_LED2.git
   $ cd myled2
   ```
2. コンパイル、インストール
   ```
   $ make
   $ sudo insmod myled.ko
   $ sudo chmod 666 /dev/myled0
   ```
3. 秒数の設定(「echo」の後の数字で秒数が変わる）    
   ```
   2秒光らせたいとき
   $ echo 2　> /dev/myled0
   ```
   8秒光らせたいとき
    $ echo 8　> /dev/myled0
4. 後始末
   ```
   $ sudo rm /dev/myled0
   $ sudo rmmod myled
   ```
