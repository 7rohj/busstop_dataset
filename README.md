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
## ✔ 유의할 점 </br>
![image](https://user-images.githubusercontent.com/99319638/204231352-fbcaaf42-f469-480b-a55f-fa64cb9f92cb.png) </br>
**같은 300번이라도 노선ID를 한 번 더 봐줘야 한담** </br>
![image](https://user-images.githubusercontent.com/99319638/204231554-6c0644fb-988a-410e-8c92-d15d711cf40b.png) </br>
![image](https://user-images.githubusercontent.com/99319638/204231598-cf14d868-7561-4b25-aca7-6c1f5a9a0c22.png) </br>
got it?! </br>
## ✔ </br>
경기도 + 서울 데이터를 합쳐주고 중복된 데이터를 제거해줘야겠다는 생각을 했음 </br>
일단 웹개발을 하도록 하려고 생각중이며 그 전에 태블로를 통해 대시보드를 만들고 </br>
임베딩을 해볼까 고려중 </br>
</br>
csv 데이터셋이 잘 나타난다면 카카오맵이나 네이버지도 크롤링은 안할것 </br>
역시 새벽이 머리가 잘 돌아감.
2022-11-28 씀 

