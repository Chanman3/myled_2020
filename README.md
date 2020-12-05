# myled_2020


## フルカラーLEDで信号のピカピカを再現してみた
- フルカラーLEDを使用し，緑色の点滅後に赤色に点灯

- フルカラーLEDを使用し，8色を順に点灯(消灯→赤→緑→黄色→青→ピンク→水色→白)

## 使用する部品
- Rasberry PI 4 ModelB x1
- RGBフルカラーLED(型番 OSTTA5131A) x1
- 5mm 赤色LED(型番 OSR5CA5B61P) x1
- LED拡散キャップ 5mm白 x1(フルカラーLEDに使用)
- ブレッドボード x1
- ジャンパー線(オス-メス) x1
- ジャンパー線(オス-オス) x6
- カーボン抵抗器 330Ω ()
- カーボン抵抗器()
- カーボン抵抗器()

## 回路図
回路図は以下のようになります。
<img src = "./images/611D8BD4-2FE3-4AE3-A4A3-4032CC24750F.jpg" width="500">

回路図を貼る


フルカラーLEDの各ピンとGPIOの接続先
- フルカラーLEDの赤ピンと抵抗(330Ω)を接続し，ジャンパー線を用いてGPIO4のピンに接続
- フルカラーLEDの青ピンと抵抗(330Ω)を接続し，ジャンパー線を用いてGPIO22のピンに接続
- フルカラーLEDの緑ピンと抵抗(330Ω)を接続し，ジャンパー線を用いてGPIO23のピンに接続
- フルカラーLEDのカソードピンをジャンパー線を用いてGNDピンに接続

5mm 赤色LEDの各ピンとGPIOの接続先
- 5mm 赤色LEDのアノードと抵抗を接続し，ジャンパー線を用いてGPIO25のピンに接続
- 5mm 赤色LEDのカソードと抵抗を接続し，ジャンパー線を用いてGNDピンに接続



## プログラムの実行方法


## 具体的にどんな動作をするか

'''
make
sudo insmod myled.ko
sudo chmod 666
'''

## 動画説明
フルカラーLEDと5mm 赤色LEDが交互に点滅する．
echo 1 

5mm 赤色LEDが点滅する．
echo 2

信号の緑の点滅後、赤を点灯するイメージで製作した
フルカラーLEDの緑色が点滅し，その後5mm 赤色LEDとともに赤色が点灯する
echo 3

フルカラーLEDを使用し，7色に順に点灯
点灯順は，赤→緑→黄色→青→ピンク→水色→白
LED拡散キャップを装着することで発光が綺麗に見える．
今回使用するフルカラーLEDは、共通カソードのものであるためGPIOがHighの時に点灯する．
echo 4


sudo rmmod myled


## デモ動画
<iframe width="560" height="315" src="https://www.youtube.com/embed/ObT22L09GHY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



