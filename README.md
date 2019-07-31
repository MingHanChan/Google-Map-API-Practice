由於最近在練習網頁，剛好碰到朋友問說怎麼在自己的網站上放入客製化的Google Map，想想應該也不難可以來嘗試看看，所以就邊上網找資院看文件，一邊簡單實做出來，並適時做一下紀錄以免日後忘記。

##### 一、使用Google Map API是可能要付費的
根據官網，Google Map API是有使用額度限制的，每月200美元，使用超過額度根據使用量來計費，通常自己測試的話是不太會超過這個額度的，但如果是日後要放網站上就要看流量了，接下來介紹要怎麼在網頁上使用Google Map API來客製化地圖。
##### 二、申請Google API key
首先，要先去[Google Maps Platform](https://cloud.google.com/maps-platform/) 啟用服務並申請一個google api key。
![](https://github.com/MingHanChan/Google-Map-API-Practice/blob/master/Image/1.png)

![](https://github.com/MingHanChan/Google-Map-API-Practice/blob/master/Image/2.png)

![](https://github.com/MingHanChan/Google-Map-API-Practice/blob/master/Image/3.png)
 
有了API key後接下來要去啟用所需要的API，這裡我啟用的主要有Maps JavaScript API，
![](https://github.com/MingHanChan/Google-Map-API-Practice/blob/master/Image/4.png)
 


另外API key就是一組可以存取你API的東西，所以一般建議設置金鑰限制，以防別人拿去偷用，至於要用哪種限制就看怎麼運用了。
![](https://github.com/MingHanChan/Google-Map-API-Practice/blob/master/Image/5.png)

[官方連結文件](https://developers.google.com/maps/documentation/javascript/get-api-key?hl=zh-tw&source=post_page---------------------------)


##### 三、開始使用Maps JavaScript API
新增一個html頁面，引用maps的javascript:   　
```
<script async defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap"</script>
```   

然後也要為地圖設立css樣式的寬跟高，不然不知道要顯示多大的地圖    
```
<style>
		#map {
        height: 70%;
        width:70%;
        }
    </style>
```
     
另外，在html裡<div id="map"></div>是必要的元素!還需要給地圖一組經緯度，以作為地圖的中心　　　　

初始化地圖(initMap)的function，做2件事:   
-建立地圖，設定地圖中心點
-放置標記(marker)
