# busstop_dataset
## ✔ 태블로퍼블릭 ver1 </br>
``` 
경기도 및 서울 버스정류장 맵으로 확인
(계속 추가될 예정)
🔽🔽🔽🔽🔽🔽🔽
```
https://public.tableau.com/app/profile/.45122939/viz/routeid/1_1 </br>

## ✔ 정리 </br>
국토교통부_(TAGO)_버스정류소정보 는 사용하지 않음. 데이터 누락이 너무 많음 </br>
</br>
처음에는 open api 를 사용했다가 그냥 csv 파일 이용.. 덜 피곤... </br>
`경기버스정보` https://www.gbis.go.kr/ </br>
오른쪽 하단에 있는 `정류소정보, 노선경유정보, 버스노선정보` 다운 </br>
`서울버스정보` https://data.seoul.go.kr/dataList/OA-1095/L/1/datasetView.do </br>
</br>
![image](https://user-images.githubusercontent.com/99319638/204149907-7b3d1791-44e9-447d-8b68-5df5f3bcc0cf.png) </br>
태블로 이용, 데이터 확인 (원래 태블로 잘 사용했었는데 왜 굳이 굳이 파이썬만 사용했었을까..) </br>
그리고 전처리를 통해 해당 정류장에 어느 버스노선이 지나가는지 확인.. (제일 중요한 이 절차도 빼먹었음.. 😥)
</br>
## ✔ 정보확인 </br>
아무 지점 `한솔테크노타운`을 찍고 확인해본 결과, 카카오맵에서는 </br>
`'502,900,441,1-2,10,22,301,5,60-1,64,65,777,300'` 번이 지나가는데 </br>
해당 경기도 데이터에서는 **441, 502** 번이 확인되지 않았다. (간선버스) </br>
진짜 찾고 찾고 찾다보니 서울데이터에서 이 버스들을 확인할 수 있었다 ^^ ㅅ </br>
(+) </br>
간선버스 이외에도 지선버스나 마을버스도 빠진 것을 확인할 수 있음 </br>
원인 찾아보기............. 🤯 </br>
</br>
## ⭕ 답변 </br>
공공데이터 포털에서 답변을 받았다!
```
안녕하세요? 경기도 버스정보 운영팀입니다. 경기도에서 OpenAPI 로 제공하고 있는 노선의 범위에는
마을버스 정보, 서울 인천 노선정보가 포함되어 있지 않습니다. 경기도 일반 노선의 경우 경기도가 
정보수집 업체와의 계약을 통해 데이터를 수집하는 반면, 마을버스는 경기도 내 31개 지방자치단체 (예, 수원시, 화성시 등) 가 
정보수집업체와의 계약을 통해 데이터를 수집하므로 경기버스정보앱, 경기버스정보 홈페이지에서 표출하는 것 이외에 
`경기도가 마을버스 정보를 OpenAPI 형태로 제공하지 않고있습니다.` (민간에서 `유료 서비스`로 제공중) 🥲
네이버지도, 카카오맵은 각각 업체와의 계약을 통해서 데이터를 제공 받는 것으로 알고 있습니다. 
같은 이유로 인면허기관이 서울특별시 또는 인천광역시인 노선들도 경기도 OpenAPI 에서 제외되었습니다. 
서울 노선의 경우 공공데이터포털 > 서울특별시_버스도착정보조회 서비스 를 통해 정보 제공을 받으실 수 있습니다. 감사합니다.
```
친절한 답변 감사드립니다.. </br>
그럼 크롤링밖에 답이 없는건가... </br> 
</br>
## ✔ 유의할 점 </br>
- 같은 300번이라도 노선ID를 한 번 더 봐줘야 함 </br>
route id & station id </br>
- 서울시_버스노선별정류소정보 테이블에서 경기도 테이블과의 정류소명이 일치하는 것들 </br>
X, Y좌표 경기도 좌표로 수정하기 (정류소명이 완전히 일치하지 않을 수 있음)</br>
## ✔ </br>
경기도 + 서울 데이터를 합쳐주고 중복된 데이터를 제거해줘야겠다는 생각을 했음 </br>
일단 웹개발을 하도록 하려고 생각중이며 그 전에 태블로를 통해 대시보드를 만들고 </br>
임베딩을 해볼까 고려중 </br>
</br>
csv 데이터셋이 잘 나타난다면 카카오맵이나 네이버지도 크롤링은 안할것 </br>
역시 새벽이 머리가 잘 돌아감.
## ✔ </br>
31개 지방자치단체 마을버스 데이터를 네이버를 통해 내가 수집해서 정리해볼까 싶음 </br>
- 실시간으로 크롤링하여 정보를 불러와 화면에 띄울 것이냐
- 데이터셋을 만들어 그 정보 안에서 필요한 정보들을 추출해 화면에 띄울 것이냐
- 🙊 
## ✔ ODsay </br>
`네이버 마을버스 정보제공처` https://lab.odsay.com/ 및 https://lab.odsay.com/community/boardListView?type=forum
![image](https://user-images.githubusercontent.com/99319638/205530800-8025a7d3-2eef-4f11-9ead-cadc37570f5f.png) </br>
`버스노선조회` https://lab.odsay.com/guide/console#searchBusLane 겨우 찾았군
## ✔ Tmoney </br>
![image](https://user-images.githubusercontent.com/99319638/205550113-3017fd04-f0f5-416a-b861-cbfed16b1c95.png) </br>
`Tmoney API` https://apiportal.tmoney.co.kr:18443/apiPackage/apiPackage.do


</br>

|시/군|순번|비고|
|:---:|:---:|:---:|
|고양|1||
|과천|2||
|광명|3||
|광주|4||
|구리|5||
|군포|6||
|김포|7||
|남양주|8||
|동두천|9||
|부천|10||
|성남|11||
|수원|12||
|시흥|13||
|안산|14||
|안성|15||
|안양|16||
|양주|17||
|여주|18||
|오산|19||
|용인|20||
|의왕|21||
|의정부|22||
|이천|23||
|파주|24||
|평택|25||
|포천|26||
|하남|27||
|화성|28||
|가평군|29||
|연천군|30||
|양평군|31||
</br>
2022-11-28 씀 2022-12-05 마지막 수정

