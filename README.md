# Some Of Drink
## 題目發想緣起
#### The spirit of Maker
* 「Maker」中文稱作「創客」，被視為是啟動未來創新的重要角色

* 從「想」到「做」的展現成為影響未來競爭力的關鍵

### Just for fun !!!
目標 : 做出一個猜拳小遊戲，透過雙方互動，勝利方可以控制水管方向、朝向失敗方的臉噴水。
---
## 構想草稿
![pic](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/sketch.jpg)
---
## 實作所需材料（取得來源、價位）
| 材料名稱            | 數量   | 單價    |總價       |材料來源|
| :----------------  | :----- | :------ | :------- | :----------- |
| Raspberry Pi       | 1       |0       |0         |課堂提供       |
| 繼電器(2路5V)       | 1       |NT $70  |NT $70    |元華電子(陣亡) |
| 繼電器(單路5V)      | 1       |0       |0         |MOLi提供      |
| 微型無刷馬達(小水沯) | 1       |NT $196 |NT $196   |露天          |
| 水管                | 4 (呎)  |NT $30  |NT $120   |露天          |
| 水管套頭            | 2       |NT $15  |NT $30    |露天          |
| 變壓器(12V 2mA)     | 1       |NT $290 |NT $290   |元華電子      |
| 變壓器轉接頭        | 1       |NT $20   |NT $20   |元華電子       |
| 伺服馬達(MG90S)     | 1       |NT $180  |NT $180  |元華電子(陣亡) |
| 伺服馬達(SG90)      | 1       |0        |0        |榮賦提供      |
| 公母杜邦線          | 1 (組)  |NT $70   |NT $70   |元華電子      |
| 母母杜邦線          | 1 (組)  |NT $50   |NT $50   |元華電子      |
| 鐵絲               | 1 (包)   |NT $10   |NT $10  |永聯社五金行   |
| LED燈              | 2       |0        |0        |榮賦提供      |
| 奶茶盒             | 1       |0        |0        |智鈞提供      |
| 樂事盒             | 1       |0        |0        |智鈞提供      |
| 水瓶               | 1       |0        |0        |智鈞提供      |
| 竹筷               | 2       |0        |0        |系辦提供       |
|                    |         |總花費   |NT $1,036  |           ||
---
## 使用的現有軟體與來源
* PuTTy : [PuTTy官網](http://www.chiark.greenend.org.uk/~sgtatham/putty/)

* python-RPi.GPIO

---
## 實作過程（碰到哪些問題、如何解決）
1.  開機時自動啟動Game.py，跑到一半會自動結束：在要使用者輸入時(raw_input)，會發生不明錯誤，疑似是無法讀取stdin

2. 買來的繼電器好像掛掉，浪費很多時間在測試，最後換一個新的就行了

3. 花了一點時間學習操作伺服馬達，控制水管方向

---
## 運用與課程內容中相關的技巧
1. 寫Script(Python)

2. Github操作

3. Linux操作(vim, ssh...等)


---
## 組裝過程及製作教學
* Raspberry pi 接腳示意圖

  ![GPIO](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/RaspberryPi-GPIO.png)

* 將12V變壓器接上插座，透過轉接頭，變壓器之正極接到小水沯之正極，變壓器之負極接到繼電器之共用端，則繼電器之常開端接到小水沯之負極，藉此形成一個可控制開關的迴路。將繼電器S端接到Pi之22接腳(控制訊號)，正端接到Pi之4接腳(5V供電)，負端接到Pi之14接腳(接地)。

  ![Model](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/model.jpg)

* 將伺服馬達固定於盒子上

  ![motor](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/motor.jpg)

* 伺服馬達接線 : 咖啡線接到Pi之6接腳(接地)，紅線Pi之2接腳(5V供電)，橘線接到12接腳(控制訊號)

  ![motor2](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/motor2.jpg)

* 利用竹筷固定水管，最後將水管接設伺服馬達

  ![pipe](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/pipe.jpg)

* 利用麵包版、LED燈製作勝負判定燈號

  ![light](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/light.jpg)

* 最終成品

  ![finish](https://github.com/NCNU-OpenSource/Some-Of-Drink/blob/master/image/finush.jpg)


---
## 操作教學
----遊戲開始----

A方選擇要出的拳(剪刀:w, 石頭:d, 布:x)

B方選出要出的拳(剪刀:u, 石頭:k , 布:m)


----選出優勝者----

控制水管方向(v向右, b向左)

A獲勝控制馬達(a噴水, s停止)

B獲勝控制馬達(h噴水, j停止)

---
## 工作分配
* 創意發想：蔡智鈞、鄭暉盛、鍾定諺
* 材料採買：蔡智鈞、鄭暉盛、鍾定諺
* 設備組裝：蔡智鈞、鍾定諺
* 程式設計：蔡智鈞、鄭暉盛

---
## 參考資料
伺服馬達教學
* http://razzpisampler.oreilly.com/ch05.html</br>
* http://www.toptechboy.com/raspberry-pi/raspberry-pi-lesson-28-controlling-a-servo-on-raspberry-pi-with-python/

繼電器教學</br>
* https://webduino.io/tutorials/tutorial-14-relay.html

GPIO控制教學</br>
* http://www.bitwizard.nl/wiki/index.php/Raspberry_Relay
