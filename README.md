# robosys-ros2

[![test](https://github.com/morita1315/robosys-ros2/actions/workflows/test.yml/badge.svg)](https://github.com/morita1315/robosys-ros2/actions/workflows/test.yml)

## 機能
* talker

1.トーカーノード: 他のノードと通信する役割を担う

2.Int16型のメッセージを「countup」というトピックに発行する

3.０．５秒おきに１ずつ足された結果をメッセージを生成し、countupというトピックに送信する

* listener

1.リスナーノード: 他のノードからメッセージを受信する役割を担う

2.Int16型のメッセージを「countup」というトピックから受け取る

3.受信したメッセージのデータをログに表示する

## 使用方法
以下のように使用する

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
* python　
  * テスト済み: 3.7~3.10

## テスト環境
* Ubuntu22.04.2LTS

## 著作権、ライセンス  
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます
* このパッケージのコマンドとコードは下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
	* (https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* ©　2023 Atsuya Morita
