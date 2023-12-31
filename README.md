# mypkg

[![test](https://github.com/morita1315/robosys-ros2/actions/workflows/test.yml/badge.svg)](https://github.com/morita1315/robosys-ros2/actions/workflows/test.yml)

ROS2で動くパッケージです

## リポジトリの説明

talkerが0.5秒おきに足された結果をcountupというトピックとして送信しlistenerがcountupというトピックを受け取り受信したデータをログに表示する

## 機能
* talker

0.5秒おきに1ずつ足された結果をメッセージを生成し、countupというトピックに送信する

* listener

受信したメッセージのデータをログに表示する

## ノード
### talker

1.トーカーノード: 他のノードと通信する役割を担う

2.Int16型のメッセージを「countup」というトピックに発行する

### listener

1.リスナーノード: 他のノードからメッセージを受信する役割を担う

2.Int16型のメッセージを「countup」というトピックから受け取る

## 使用方法
以下のように使用する
* talker

```bash
$ros2 run mypkg talker
```

別端末でros2を使用しサブスクライブする
```bash
$ ros2 topic echo /countup
data: 126
---
data: 127
---
data: 128
---
data: 129
---
data: 130
---
data: 131
---
data: 132
---
data: 133
---
```

* listener

```bash
$ros2 run mypkg talker
```

別端末でros2を使用し
```bash
$ ros2 run mypkg listener
[INFO] [1703695526.602248244] [listener]: Listen: 57
[INFO] [1703695527.082681603] [listener]: Listen: 58
[INFO] [1703695527.582128404] [listener]: Listen: 59
[INFO] [1703695528.082385889] [listener]: Listen: 60
[INFO] [1703695528.582362048] [listener]: Listen: 61
[INFO] [1703695529.082470773] [listener]: Listen: 62
[INFO] [1703695529.582465365] [listener]: Listen: 63
[INFO] [1703695530.082641807] [listener]: Listen: 64
[INFO] [1703695530.582202083] [listener]: Listen: 65
[INFO] [1703695531.082325690] [listener]: Listen: 66
[INFO] [1703695531.582330376] [listener]: Listen: 67
```

* launch

```bash
$ ros2 launch mypkg talk_listen.launch.py
[INFO] [launch]: All log files can be found below /home/mossan/.ros/log/2023-12-27-23-46-34-961548-mossan-7710
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [7711]
[INFO] [listener-2]: process started with pid [7713]
[listener-2] [INFO] [1703688395.776988760] [listener]: Listen: 0
[listener-2] [INFO] [1703688396.259830351] [listener]: Listen: 1
[listener-2] [INFO] [1703688396.759054748] [listener]: Listen: 2
[listener-2] [INFO] [1703688397.259389848] [listener]: Listen: 3
[listener-2] [INFO] [1703688397.759385358] [listener]: Listen: 4
[listener-2] [INFO] [1703688398.259221387] [listener]: Listen: 5
[listener-2] [INFO] [1703688398.759257693] [listener]: Listen: 6
[listener-2] [INFO] [1703688399.259480169] [listener]: Listen: 7
[listener-2] [INFO] [1703688399.759263218] [listener]: Listen: 8
[listener-2] [INFO] [1703688400.259024180] [listener]: Listen: 9
[listener-2] [INFO] [1703688400.759212219] [listener]: Listen: 10
```

## 必要なソフトウェア
* Python　
  * テスト済み: 3.10
* ROS2

## テスト環境
* Ubuntu22.04.2LTS

## 著作権、ライセンス  
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます
* このパッケージのコマンドとコードは下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
	* (https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* ©　2023 Atsuya Morita
