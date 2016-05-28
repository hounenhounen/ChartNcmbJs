# ChartNCMBJSについて

このリポジトリは[つっぱり棒 × Raspberry Pi × 3GPI × Nifty Cloud Mobile Backend　ワークショップ・ハッカソン(https://ouch-hack.doorkeeper.jp/events/45161)で使うリポジトリです。

[ChartJS](http://www.chartjs.org/)と[ニフティクラウド mobile backend](http://mb.cloud.nifty.com/)を使ってセンサーデータをグラフ表示します。

![Chartjs]()

index.htmlをブラウザ表示すればグラフが表示されます。

# グラフ表示するために[ニフティクラウド mobile backend](http://mb.cloud.nifty.com/)への保存方法

下記のコードのように書いていただけると、温度センサのデータをグラフ表示できます

```js
var ncmb = new NCMB("YOUR_APPLICATIONKEY","YOUR_CLIENTKEY");
var TemperatureClass = ncmb.DataStore("Temperature");
    var temperatureClass = new TemperatureClass();
    var today = new Date();
    temperatureClass.set("temperature",data.temperature);
    temperatureClass.set("date",today);
    temperatureClass.save()
     .then(function(){
      console.log("message is saved.");
     })
    .catch(function(err){
     console.log(err.text);
    });
```