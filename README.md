# sugo-actor-hitoe

Android で動く、hitoe を使った心拍異常検知 module を内蔵した actor。


## イベント

+ [warning](#event/warning)
+ [emergency](#event/emergency)


### warning <a id="event/warning">

異常を検知しユーザーに確認を求めている状態。
データは以下の要素を含む。

|key|value type|description|
|:--|:--|:--|
|heartRate|数値|心拍数|
|location|数値の配列|緯度、経度、高度|
|date|RFC3339 形式の日時|

例えば、

```json
{
  "heartRate": 115,
  "location": [
    35.7014665,
    139.753269,
    0
  ],
  "date": "2016-10-11T19:18:11.131+09:00"
}
```


### emergency <a id="event/emergency">

異常検知の確認に対してユーザーが反応しなかった、または、明示的に救助を要請した。
データは warning と同じ。
