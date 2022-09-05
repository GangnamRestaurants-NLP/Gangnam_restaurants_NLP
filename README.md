![image](https://user-images.githubusercontent.com/104780664/188345812-37b2958a-58ef-4df3-90b9-783db3a9ca42.png)

------------
## 🥂 목표
- 머신러닝을 이용한 강남역 회식장소 선정에 도움이 되는 리뷰 분류 프로젝트


## 🍚 Intro
- 신입의 경우 회사 근처 식당을 잘 모르기 때문에 회식장소를 선정해야 할 때 고민이 많을 것이라고 생각됩니다.
그래서 저희는 회식장소를 선정할 때 고려해야 할 사항을 고민해봤습니다.</br></br>

<p align="center"><img src="https://user-images.githubusercontent.com/104750108/188346925-1b770b9e-8f78-4477-910c-fa984c4f79b3.gif"></p> </br>
<p align="center"><img width="350" src="https://user-images.githubusercontent.com/104750108/188348582-d80694bc-f418-4958-bc87-c9758d0b2cf7.png">
<img width="450" src="https://user-images.githubusercontent.com/104750108/188348674-435e5b31-9f33-48e6-ab83-61ce9e249bb1.png"></p>

------------
## 🎯 Result
- 분류 모델 네개를 사용해 본 결과,  logistic regression이 가장 좋은 성능을 보여 본 모델로 선택하고 피쳐별로 값을 다르게 하여 모델의 성능을 개선하고자 하였습니다. </br>
![image](https://user-images.githubusercontent.com/104745357/188358981-295bbca4-9809-445d-bf76-138cbcd2641e.png) </br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350747-2aea66a2-062e-434b-bd71-35d8193a9fa8.png">
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350584-74934439-e39d-4039-8da1-6964159d4572.png"> </br>

- 모델의 정확도를 확인하기 위해 랜덤하게 고른 새로운 가게 리뷰 158개를 테스트해보았는데 도움이 되는 리뷰 135개를 맞춰 약 85%의 정확도를 보여줬습니다.

------------
## :statue_of_liberty: Modeling

- 정보 수집 사이트
```
식신(장소 선정), 네이버 마이플레이스(리뷰 수집)
```
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
<img width="550" alt="image" src="https://user-images.githubusercontent.com/104750108/188353253-5cc8af79-cbce-4a20-9f8e-ac4983f4dfdf.png">

  
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

---------
## 🌟 EDA

<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354042-09d488bf-16a1-4ecf-ad6b-df45b63112f3.png">

<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354282-0043b736-d9ad-4f1d-b594-053581dc8e6d.png">

<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354345-07b40ea9-c05d-4105-a2c6-aff84f48e4e2.png">

----------
## 🤔 한계점

- 한국어 패키지를 사용하더라도 실제로는 맞춤법을 제대로 적용하지 못해 2차 검수를 진행했어야하는 어려움

- 딥러닝을 사용한 자연어처리를 진행하지 못해 데이터에 대한 정확도를 올리기가 어려웠음

- 키워드를 통한 분석의 범위를 넓히면(Ex. 블랙리스트 고객, 재방문율 등) 모델의 정확도를 높일 수 있을 것으로 예상


----------
## 🏷️ Reference


- [NLP] LDA 토픽 모델링을 활용한 앱 리뷰 분석 프로젝트 (<a href="https://heytech.tistory.com/401" target="_blank">Link</a>)

- [ML 공부] 맛집 리뷰를 통한 감성분석 (긍정, 부정 언어 판별) - 210521 (<a href="https://moojuksublime.tistory.com/14" target="_blank">Link</a>)

- [프로젝트] 호텔 리뷰 텍스트 분석 & 분류 모델 제작 (<a href="https://hanawithdata.tistory.com/entry/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%98%B8%ED%85%94-%EB%A6%AC%EB%B7%B0-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EB%B6%84%EC%84%9D-%EB%B6%84%EB%A5%98-%EB%AA%A8%EB%8D%B8-%EC%A0%9C%EC%9E%91" target="_blank">Link</a>)

- PyKoSpacing github (<a href="https://github.com/haven-jeon/PyKoSpacing" target="_blank">Link</a>)

- Py-hanspell github (<a href="https://github.com/ssut/py-hanspell" target="_blank">Link</a>)

- 한국어 맞춤법/문법 검사기 (<a href="http://speller.cs.pusan.ac.kr/" target="_blank">Link</a>)

- 위키독스 - 딥러닝을 이용한 자연어처리 입문 (<a href="https://wikidocs.net/book/2155" target="_blank">Link</a>)


