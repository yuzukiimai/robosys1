# LED_Device_Driver
2021年度ロボットシステム学の課題1で作成、改良したデバイスドライバです。

入力数字（0～5）に応じてLEDが点灯、消灯をしたり、電子ブザーが鳴ったりします。

___


## 動作環境

- Raspberry Pi 3 Model B

- OS  :  ubuntu 20.04 server
 
___

## 使用したもの
- Raspberry Pi 3 Model B × 1

- LED × 3

- 抵抗220Ω × 4

- 電子ブザー × 1

- ブレッドボード × 1

- ジャンパー線（オス-メス）× 8

___

## 回路（pin情報）


- 回路図

<img src  = "https://user-images.githubusercontent.com/91650008/144912159-ec126848-0681-443c-99b2-59fa71b34b65.png" width = "720">


- 配線図

<img src = "https://user-images.githubusercontent.com/91650008/144731640-5d044429-6040-48c6-9af8-e005f0324029.JPG" width = "720">


- pin情報
 
<img src="https://user-images.githubusercontent.com/91650008/144731137-d5292cc5-9a97-47b5-8a50-f154af91997f.JPG" width = "720">


- LED1（透明→緑）:  22（GPIO25）

- LED2（黄）:  16（GPIO23）

- LED3（赤）:  18（GPIO24）

- 電子ブザー :  37（GPIO26）

___



## 使用方法

#### 【インストール】
以下のコマンドを実行してください。

```
$ git clone https://github.com/yuzukiimai/robosys1.git

$ cd robosys1

$ make

$ sudo insmod myled.ko

$ sudo chmod 666 /dev/myled0
```
___

#### 【アンインストール】
以下のコマンドを実行してください。

```
$ sudo rmmod myled

$ make clean
```
___

#### 【実行】

 ※ページ下に実行時の動画があります。
 
 インストール後に以下のコマンドを実行してください。
 
 
##### LED1を点灯させる
```
$ echo 1 > /dev/myled0
```


##### LED2を点灯させる
```
$ echo 2 > /dev/myled0
```


##### LED3を点灯させる
```
$ echo 3 > dev/myled0
```


##### 電子ブザーを鳴らす
```
$ echo 4 > dev/myled0
```


##### すべての動作をやめさせる
```
$ echo 0 > dev/myled0
```


##### 信号機のような動作をさせる
```
$ echo 5 > dev/myled0
```
___


## デモ動画

https://youtu.be/fcmh2hfk0dk


___

## ライセンス
  [GNU General Public License v3.0](https://github.com/yuzukiimai/robosys1/blob/master/COPYING)
