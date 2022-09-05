![image](https://user-images.githubusercontent.com/104780664/188345812-37b2958a-58ef-4df3-90b9-783db3a9ca42.png)

------------
## 🥂 Project Goal
- 리뷰 데이터를 이용한 좋은 회식 장소 찾기 프로젝트

------------
## 🍚 Introduction
- 신입은 회사 근처 식당을 잘 모르기 때문에, 회식장소 찾기가 어렵습니다. 
- 그래서 본 프로젝트는 회식 장소를 선정할 때 고려해야 할 사항을 찾아보고자 시작했습니다.
- 리뷰 데이터를 이용하여 회식 장소 선정에 도움이 되는 리뷰와 그렇지 않은 리뷰를 분류하는 프로젝트입니다. </br></br>

<p align="center"><img src="https://user-images.githubusercontent.com/104780664/188396090-ccd5bd01-c821-4373-ab1f-ef0e59c57e1c.gif"></p> </br>
<p align="center"><img width="350" src="https://user-images.githubusercontent.com/104750108/188348582-d80694bc-f418-4958-bc87-c9758d0b2cf7.png">
<img width="450" src="https://user-images.githubusercontent.com/104750108/188348674-435e5b31-9f33-48e6-ab83-61ce9e249bb1.png"></p>

------------
## 🍽 Summary of Findings
- 3줄 요약

------------
## :statue_of_liberty: Data

- 정보 수집 사이트

  - 식신(장소 선정) (<a href="https://www.siksinhot.com/" target="_blank">Link</a>)

  - 네이버 마이플레이스(리뷰 수집) (<a href="https://m.place.naver.com/my/5c0ce7d689a470a61057365e/feed" target="_blank">Link</a>)

- 데이터 수집 기간  
```
2019년 5월 26일 ~ 2022년 8월 19일 --> 약 8000개의 데이터 사용 
```

- 데이터 컬럼 설명

```
- 가게 이름
  - 남/녀 비율
  - 연령별 1위, 2위
  
- 리뷰 날짜

- 방문자 리뷰

- helpful(label)
  - 카테고리(menu, mood, service, price,clean, room, parking, photo)에서 
    3개 이상 해당이 되면 helpful = 1 or helpful = 0
    
- 키워드 관련 항목(맛, 맛집, 메뉴 + 음식, 친절 + 직원, 때, 예약, 가격, 분위기, 추천)
```
- 초기 데이터
<img width="800" alt="image" src="https://user-images.githubusercontent.com/104750108/188386156-2e28e388-90d0-4936-af73-afbee6e9d3a8.png">
<img width="400" alt="image" src="https://user-images.githubusercontent.com/104750108/188386611-3b38fd77-f8af-4128-8d1d-772fc9b067e3.png">




---------
## 📙 Preprocessing

<details>
<summary>의미 없는 단어 제거</summary>
<div markdown="1">
  
- 이모티콘/기호 단어로 변경 및 문구 제거
  
- 이모티콘, 특수문자도 감정을 표현하는 하나의 방식이므로 텍스트로 대치해주는 방식 적용
  - 예시: ❤️ → 하트 ,  :blush: /^^ → 웃음
  
- 별점 관련 문구 제거
  
- 웃음 이모티콘이 포함되어있으나 실제 글 내용이 부정적이면 제거
  
- 의미 없는 기호,자음, 모음 제거
  
- 의미없는 자음, 모음, 특수문자 제거
  
- 띄어쓰기 및 맞춤법 검사
  
- 개행 문자 제거(\n, \r)
</div>
</details>


<details>
<summary>데이터 카테고리화</summary>
<div markdown="1">
  </br>
<img width="1100" alt="image" src="https://user-images.githubusercontent.com/104750108/188353025-f26e4f11-80a9-46c0-9e55-d96e46bfe35a.png">
  

</div>
</details>


<details>
<summary>토큰화(Tag)</summary>
<div markdown="1">
  </br>
<img width="500" alt="image" src="https://user-images.githubusercontent.com/104750108/188353253-5cc8af79-cbce-4a20-9f8e-ac4983f4dfdf.png">

  
</div>
</details>



<details>
<summary>불용어 처리 & One-Hot Encoding</summary>
<div markdown="1">
  
- 불용어
  - 한우, 하, 포장, 평양냉면, 탕, 타이, 전복, 전, 재, 우동, 오, 들, 되, 느끼, 네이버, 가 …
  -> 총 43개의 불용어 제거
  
- One-Hot Encoding
  - 딘타이펑 강남점 : 1, 백억하누 강남본점 : 2, 느린마을 양조장: 3 화기애애 강남역점 : 4 …
  -> 총 22개의 store_name 변경

  
</div>
</details>

<details>
<summary>최종 데이터</summary>
<div markdown="1">


<img width="1794" alt="image" src="https://user-images.githubusercontent.com/104750108/188389237-40c76e87-e215-4c86-b81a-7c23e182f23a.png">
  </br>
  </br>
<img width="600" alt="image" src="https://user-images.githubusercontent.com/104750108/188390321-50946981-8780-421a-ba27-eb914e639572.png">

  
  </div>
</details>

---------
## 🌟 EDA
<p align="center"><img src="https://user-images.githubusercontent.com/77037338/188400214-cf4e3584-45b2-46e7-b3bc-6638ae2adcf0.png"></p>

<details>
<summary>가게별 남녀 비율 분포도 그래프</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354042-09d488bf-16a1-4ecf-ad6b-df45b63112f3.png">
  
  </div>
</details>

<details>
<summary>리뷰길이 비교</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354282-0043b736-d9ad-4f1d-b594-053581dc8e6d.png">
  
  </div>
</details>

<details>
<summary>식당별 리뷰길이 비교</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354345-07b40ea9-c05d-4105-a2c6-aff84f48e4e2.png">
  
  </div>
</details>

<details>
<summary>날짜별 리뷰갯수 추세 확인</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/77037338/188399828-5809386b-52a4-4f9e-9d22-6ebf48fd82ef.png">
  
  </div>
</details>

<details>
<summary>날짜별 리뷰 빈도수 비교</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/77037338/188400101-14919e82-0373-4223-a767-a932ada99f61.png">

  </div>
</details>






------------
## 🎯 Result 
### Model Selection
- 본 프로젝트에서는 4가지 분류 모델 비교 결과, 로지스틱 회귀 모델이 가장 좋은 성능을 보였습니다. 
- 때문에 로지스틱 회귀 모델을 기준으로 성능 개선을 시도했습니다. </br>
![image](https://user-images.githubusercontent.com/104745357/188358981-295bbca4-9809-445d-bf76-138cbcd2641e.png) </br>
### Feature Selection
- tf-idf 보다 countvectorizer 를 하고 ...
- 피쳐별로 값을 다르게 하여 모델의 성능을 개선하고자 하였습니다. </br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350747-2aea66a2-062e-434b-bd71-35d8193a9fa8.png">
- 모델 정확도 테스트를 위해 랜덤하게 뽑은 158개의 데이터로 검증한 결과, 158개 중 135개를 맞춰 약 85%의 정확도를 보여줬습니다. </br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350584-74934439-e39d-4039-8da1-6964159d4572.png"> </br>

----------
## :pencil2: Epilogue

### [Human performance]
- hanspell로 맞춤법 검사 -> pycospacing + hanspell 맞춤법 검사</br>
![image (4)](https://user-images.githubusercontent.com/77037338/188397475-946e4af9-6c02-43cf-ba5c-8768d2a92f93.png)</br>
- 맞춤법 확인 결과, 추가 오류를 발견하였습니다.
- 따라서 저희가 직접 눈으로 하나씩 보면서 교정하여 문제를 해결하였습니다.</br>


### [Machine Learning]
- 데이터 양을 봤을 때 딥러닝을 먼저 사용하기 보다 머신러닝을 사용하여 결과를 확인하였고, 성능을 높이고자 노력했습니다.
- 결과는 특정 피처 값을 사용하였을 때 88% 이상의 성능이 나와 딥러닝이 아닌 머신러닝 만으로도 충분히 높은 결과를 얻을 수 있었습니다. 
- 추후에 데이터를 더 많이 모아 딥러닝을 시도해보는 것도 좋을 것 같습니다.</br>


----------
## 🏷️ Reference


- [NLP] LDA 토픽 모델링을 활용한 앱 리뷰 분석 프로젝트 (<a href="https://heytech.tistory.com/401" target="_blank">Link</a>)

- [ML 공부] 맛집 리뷰를 통한 감성분석 (긍정, 부정 언어 판별) - 210521 (<a href="https://moojuksublime.tistory.com/14" target="_blank">Link</a>)

- [프로젝트] 호텔 리뷰 텍스트 분석 & 분류 모델 제작 (<a href="https://hanawithdata.tistory.com/entry/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%98%B8%ED%85%94-%EB%A6%AC%EB%B7%B0-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EB%B6%84%EC%84%9D-%EB%B6%84%EB%A5%98-%EB%AA%A8%EB%8D%B8-%EC%A0%9C%EC%9E%91" target="_blank">Link</a>)

- PyKoSpacing github (<a href="https://github.com/haven-jeon/PyKoSpacing" target="_blank">Link</a>)

- Py-hanspell github (<a href="https://github.com/ssut/py-hanspell" target="_blank">Link</a>)

- 한국어 맞춤법/문법 검사기 (<a href="http://speller.cs.pusan.ac.kr/" target="_blank">Link</a>)

- 위키독스 - 딥러닝을 이용한 자연어처리 입문 (<a href="https://wikidocs.net/book/2155" target="_blank">Link</a>)


