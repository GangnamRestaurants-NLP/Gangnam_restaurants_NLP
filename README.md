![image](https://user-images.githubusercontent.com/104780664/188345812-37b2958a-58ef-4df3-90b9-783db3a9ca42.png)

------------
## 🍚 Intro
- 신입의 경우 회사 근처 식당을 잘 모르기 때문에 회식장소를 선정해야 할 때 고민이 많을 것이라고 생각됩니다.
그래서 저희는 회식장소를 선정할 때 고려해야 할 사항을 고민해봤습니다.</br></br>

<p align="center"><img src="https://user-images.githubusercontent.com/104750108/188346925-1b770b9e-8f78-4477-910c-fa984c4f79b3.gif"></p> </br>
<p align="left"><img width="450" alt="image" src="https://user-images.githubusercontent.com/104750108/188348582-d80694bc-f418-4958-bc87-c9758d0b2cf7.png"><img width="550" alt="image" src="https://user-images.githubusercontent.com/104750108/188348674-435e5b31-9f33-48e6-ab83-61ce9e249bb1.png"></p> </br>

------------
## 🎯 Result
- 분류 모델 네개를 사용해 본 결과,  logistic regression이 가장 좋은 성능을 보여 본 모델로 선택하고 피쳐별로 값을 다르게 하여 모델의 성능을 개선하고자 하였습니다. </br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350776-d73cfa62-53fd-4cc7-a3ce-0b3b5b1d1d76.png">
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350747-2aea66a2-062e-434b-bd71-35d8193a9fa8.png">
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350584-74934439-e39d-4039-8da1-6964159d4572.png"> </br>

- 모델의 정확도를 확인하기 위해 랜덤하게 고른 새로운 가게 리뷰 158개를 테스트해보았는데 도움이 되는 리뷰 135개를 맞춰 약 85%의 정확도를 보여줬습니다.

------------
## Modeling

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
## 전처리

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





