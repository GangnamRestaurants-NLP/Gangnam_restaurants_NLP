![Title](https://user-images.githubusercontent.com/104780664/192462225-cad48241-a823-4229-92f6-7b5ddd89d336.png)

------------
## ๐ฅ Project Goal
- ๋ฆฌ๋ทฐ ๋ฐ์ดํฐ๋ฅผ ์ด์ฉํ ์ข์ ํ์ ์ฅ์ ์ฐพ๊ธฐ ํ๋ก์ ํธ

------------
## ๐ Introduction
- ์ ์์ ํ์ฌ ๊ทผ์ฒ ์๋น์ ์ ๋ชจ๋ฅด๊ธฐ ๋๋ฌธ์, ํ์์ฅ์ ์ฐพ๊ธฐ๊ฐ ์ด๋ ต์ต๋๋ค. 
- ๊ทธ๋์ ๋ณธ ํ๋ก์ ํธ๋ ํ์ ์ฅ์๋ฅผ ์ ์ ํ  ๋ ๊ณ ๋ คํด์ผ ํ  ์ฌํญ์ ์ฐพ์๋ณด๊ณ ์ ์์ํ์ต๋๋ค.
- ๋ฆฌ๋ทฐ ๋ฐ์ดํฐ๋ฅผ ์ด์ฉํ์ฌ ํ์ ์ฅ์ ์ ์ ์ ๋์์ด ๋๋ ๋ฆฌ๋ทฐ์ ๊ทธ๋ ์ง ์์ ๋ฆฌ๋ทฐ๋ฅผ ๋ถ๋ฅํ๋ ํ๋ก์ ํธ์๋๋ค. </br></br>

<p align="center"><img width="25%" src="https://user-images.githubusercontent.com/104780664/188396090-ccd5bd01-c821-4373-ab1f-ef0e59c57e1c.gif"></p> </br>
<p align="center"><img width="350" src="https://user-images.githubusercontent.com/104750108/188348582-d80694bc-f418-4958-bc87-c9758d0b2cf7.png">
<img width="450" src="https://user-images.githubusercontent.com/104750108/188348674-435e5b31-9f33-48e6-ab83-61ce9e249bb1.png"></p>

------------
## ๐ฝ Summary of Findings
- ์ด 4๊ฐ์ง ๋ชจ๋ธ์ ์งํํด ๋ณธ ๊ฒฐ๊ณผ, Logistic Regression์ด ๊ฐ์ฅ ์ข์ ์ฑ๋ฅ์ ๋ณด์
- Feature ์ ํ ์ ๋ฆฌ๋ทฐ, ๋ฆฌ๋ทฐ๊ธธ์ด, ๊ฐ๊ฒ๋ช, ํค์๋๋ฅผ ์ด์ฉํ์ฌ ํ์ต์ ์งํํจ
- ๋๋คํ๊ฒ ์ ํํ ์๋ก์ด ์๋น์ ๋ฆฌ๋ทฐ ํ์คํธ ์ ์ฝ 85%์ ์ ํ๋๋ฅผ ๋ณด์ฌ์ค

------------
## :statue_of_liberty: Data

- ์ ๋ณด ์์ง ์ฌ์ดํธ

  - ์์ (์ฅ์ ์ ์ ) (<a href="https://www.siksinhot.com/" target="_blank">Link</a>)

  - ๋ค์ด๋ฒ ๋ง์ดํ๋ ์ด์ค(๋ฆฌ๋ทฐ ์์ง) (<a href="https://m.place.naver.com/my/5c0ce7d689a470a61057365e/feed" target="_blank">Link</a>)

- ๋ฐ์ดํฐ ์์ง ๊ธฐ๊ฐ  
```
2019๋ 5์ 26์ผ ~ 2022๋ 8์ 19์ผ --> ์ฝ 8000๊ฐ์ ๋ฐ์ดํฐ ์ฌ์ฉ 
```

- ๋ฐ์ดํฐ ์ปฌ๋ผ ์ค๋ช

```
- ๊ฐ๊ฒ ์ด๋ฆ
  - ๋จ/๋ ๋น์จ
  - ์ฐ๋ น๋ณ 1์, 2์
  
- ๋ฆฌ๋ทฐ ๋ ์ง

- ๋ฐฉ๋ฌธ์ ๋ฆฌ๋ทฐ

- helpful(label)
  - ์นดํ๊ณ ๋ฆฌ(menu, mood, service, price,clean, room, parking, photo)์์ 
    3๊ฐ ์ด์ ํด๋น์ด ๋๋ฉด helpful = 1 or helpful = 0
    
- ํค์๋ ๊ด๋ จ ํญ๋ชฉ(๋ง, ๋ง์ง, ๋ฉ๋ด + ์์, ์น์  + ์ง์, ๋, ์์ฝ, ๊ฐ๊ฒฉ, ๋ถ์๊ธฐ, ์ถ์ฒ)
```
- ์ด๊ธฐ ๋ฐ์ดํฐ

![initial form](https://user-images.githubusercontent.com/104780664/192462626-552d1fe8-555b-4e59-8c0b-997017d8e5bc.png)


---------
## ๐ Preprocessing

<details>
<summary>์๋ฏธ ์๋ ๋จ์ด ์ ๊ฑฐ</summary>
<div markdown="1">
  
- ์ด๋ชจํฐ์ฝ/๊ธฐํธ ๋จ์ด๋ก ๋ณ๊ฒฝ ๋ฐ ๋ฌธ๊ตฌ ์ ๊ฑฐ
  
- ์ด๋ชจํฐ์ฝ, ํน์๋ฌธ์๋ ๊ฐ์ ์ ํํํ๋ ํ๋์ ๋ฐฉ์์ด๋ฏ๋ก ํ์คํธ๋ก ๋์นํด์ฃผ๋ ๋ฐฉ์ ์ ์ฉ
  - ์์: โค๏ธ โ ํํธ ,  :blush: /^^ โ ์์
  
- ๋ณ์  ๊ด๋ จ ๋ฌธ๊ตฌ ์ ๊ฑฐ
  
- ์์ ์ด๋ชจํฐ์ฝ์ด ํฌํจ๋์ด์์ผ๋ ์ค์  ๊ธ ๋ด์ฉ์ด ๋ถ์ ์ ์ด๋ฉด ์ ๊ฑฐ
    
- ์๋ฏธ์๋ ์์, ๋ชจ์, ํน์๋ฌธ์ ์ ๊ฑฐ
  
- ๋์ด์ฐ๊ธฐ ๋ฐ ๋ง์ถค๋ฒ ๊ฒ์ฌ
  
- ๊ฐํ ๋ฌธ์ ์ ๊ฑฐ(\n, \r)
</div>
</details>


<details>
<summary>๋ฐ์ดํฐ ์นดํ๊ณ ๋ฆฌํ</summary>
<div markdown="1">
  </br>
<img width="1100" alt="image" src="https://user-images.githubusercontent.com/104750108/188353025-f26e4f11-80a9-46c0-9e55-d96e46bfe35a.png">
  

</div>
</details>


<details>
<summary>ํ ํฐํ(Tag)</summary>
<div markdown="1">
  </br>
<img width="500" alt="image" src="https://user-images.githubusercontent.com/104750108/188353253-5cc8af79-cbce-4a20-9f8e-ac4983f4dfdf.png">

  
</div>
</details>



<details>
<summary>๋ถ์ฉ์ด ์ฒ๋ฆฌ & One-Hot Encoding</summary>
<div markdown="1">
  
- ๋ถ์ฉ์ด
  - ํ์ฐ, ํ, ํฌ์ฅ, ํ์๋๋ฉด, ํ, ํ์ด, ์ ๋ณต, ์ , ์ฌ, ์ฐ๋, ์ค, ๋ค, ๋, ๋๋ผ, ๋ค์ด๋ฒ, ๊ฐ โฆ
  -> ์ด 43๊ฐ์ ๋ถ์ฉ์ด ์ ๊ฑฐ
  
- One-Hot Encoding
  - ๋ํ์ดํ ๊ฐ๋จ์  : 1, ๋ฐฑ์ตํ๋ ๊ฐ๋จ๋ณธ์  : 2, ๋๋ฆฐ๋ง์ ์์กฐ์ฅ: 3 ํ๊ธฐ์ ์  ๊ฐ๋จ์ญ์  : 4 โฆ
  -> ์ด 22๊ฐ์ store_name ๋ณ๊ฒฝ

  
</div>
</details>

<details>
<summary>์ต์ข ๋ฐ์ดํฐ</summary>
<div markdown="1">


<img width="1794" alt="image" src="https://user-images.githubusercontent.com/104750108/188389237-40c76e87-e215-4c86-b81a-7c23e182f23a.png">
  </br>
  </br>
<img width="300" alt="image" src="https://user-images.githubusercontent.com/104750108/188390321-50946981-8780-421a-ba27-eb914e639572.png">

  
  </div>
</details>

---------
## ๐ EDA
<p align="center"><img src="https://user-images.githubusercontent.com/77037338/188400214-cf4e3584-45b2-46e7-b3bc-6638ae2adcf0.png"></p>

<details>
<summary>๊ฐ๊ฒ๋ณ ๋จ๋ ๋น์จ ๋ถํฌ๋ ๊ทธ๋ํ</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354042-09d488bf-16a1-4ecf-ad6b-df45b63112f3.png">
  
  </div>
</details>

<details>
<summary>๋ฆฌ๋ทฐ๊ธธ์ด ๋น๊ต</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354282-0043b736-d9ad-4f1d-b594-053581dc8e6d.png">
  
  </div>
</details>

<details>
<summary>์๋น๋ณ ๋ฆฌ๋ทฐ๊ธธ์ด ๋น๊ต</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/104750108/188354345-07b40ea9-c05d-4105-a2c6-aff84f48e4e2.png">
  
  </div>
</details>

<details>
<summary>๋ ์ง๋ณ ๋ฆฌ๋ทฐ๊ฐฏ์ ์ถ์ธ ํ์ธ</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/77037338/188399828-5809386b-52a4-4f9e-9d22-6ebf48fd82ef.png">
  
  </div>
</details>

<details>
<summary>๋ ์ง๋ณ ๋ฆฌ๋ทฐ ๋น๋์ ๋น๊ต</summary>
<div markdown="1">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/77037338/188400101-14919e82-0373-4223-a767-a932ada99f61.png">

  </div>
</details>






------------
## ๐ฏ Result 
### Model Selection
- ๋ณธ ํ๋ก์ ํธ์์๋ 4๊ฐ์ง ๋ถ๋ฅ ๋ชจ๋ธ ๋น๊ต ๊ฒฐ๊ณผ, ๋ก์ง์คํฑ ํ๊ท ๋ชจ๋ธ์ด ๊ฐ์ฅ ์ข์ ์ฑ๋ฅ์ ๋ณด์์ต๋๋ค. 
- ๋๋ฌธ์ ๋ก์ง์คํฑ ํ๊ท ๋ชจ๋ธ์ ๊ธฐ์ค์ผ๋ก ์ฑ๋ฅ ๊ฐ์ ์ ์๋ํ์ต๋๋ค. </br>
![image](https://user-images.githubusercontent.com/104745357/188358981-295bbca4-9809-445d-bf76-138cbcd2641e.png) </br>
### Feature Selection
- ํผ์ณ๋ณ๋ก ๊ฐ์ ๋ค๋ฅด๊ฒ ํ์ฌ ๋ชจ๋ธ์ ์ฑ๋ฅ์ ๊ฐ์ ํ๊ณ ์ ํ์์ต๋๋ค. 
- ์ต์ข์ ์ผ๋ก Feature5๋ฅผ ์ ์ ํ์ฌ ํ์ต์ ์งํํ์์ต๋๋ค.</br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350747-2aea66a2-062e-434b-bd71-35d8193a9fa8.png">
- ๋ชจ๋ธ ์ ํ๋ ํ์คํธ๋ฅผ ์ํด ๋๋คํ๊ฒ ๋ฝ์ 158๊ฐ์ ๋ฐ์ดํฐ๋ก ๊ฒ์ฆํ ๊ฒฐ๊ณผ, 158๊ฐ ์ค 135๊ฐ๋ฅผ ๋ง์ถฐ ์ฝ 85%์ ์ ํ๋๋ฅผ ๋ณด์ฌ์คฌ์ต๋๋ค. </br>
<img width="1143" alt="image" src="https://user-images.githubusercontent.com/104750108/188350584-74934439-e39d-4039-8da1-6964159d4572.png"> </br>

----------
## :pencil2: Epilogue

### [Human performance]
 < hanspell๋ก ๋ง์ถค๋ฒ ๊ฒ์ฌ -> pycospacing + hanspell ๋ง์ถค๋ฒ ๊ฒ์ฌ></br>
![image (4)](https://user-images.githubusercontent.com/77037338/188397475-946e4af9-6c02-43cf-ba5c-8768d2a92f93.png)</br>
- ๋ง์ถค๋ฒ ํ์ธ ๊ฒฐ๊ณผ, ์ถ๊ฐ ์ค๋ฅ๋ฅผ ๋ฐ๊ฒฌํ์์ต๋๋ค.
- ๋ฐ๋ผ์ ์ ํฌ๊ฐ ์ง์  ๋์ผ๋ก ํ๋์ฉ ๋ณด๋ฉด์ ๊ต์ ํ์ฌ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ์์ต๋๋ค.</br>


### [Machine Learning]
- ๋ฐ์ดํฐ ์์ ๋ดค์ ๋ ๋ฅ๋ฌ๋์ ๋จผ์  ์ฌ์ฉํ๊ธฐ ๋ณด๋ค ๋จธ์ ๋ฌ๋์ ์ฌ์ฉํ์ฌ ๊ฒฐ๊ณผ๋ฅผ ํ์ธํ์๊ณ , ์ฑ๋ฅ์ ๋์ด๊ณ ์ ๋ธ๋ ฅํ์ต๋๋ค.
- ๊ฒฐ๊ณผ๋ ํน์  ํผ์ฒ ๊ฐ์ ์ฌ์ฉํ์์ ๋ 88% ์ด์์ ์ฑ๋ฅ์ด ๋์ ๋ฅ๋ฌ๋์ด ์๋ ๋จธ์ ๋ฌ๋ ๋ง์ผ๋ก๋ ์ถฉ๋ถํ ๋์ ๊ฒฐ๊ณผ๋ฅผ ์ป์ ์ ์์์ต๋๋ค. 
- ์ถํ์ ๋ฐ์ดํฐ๋ฅผ ๋ ๋ง์ด ๋ชจ์ ๋ฅ๋ฌ๋์ ์๋ํด๋ณด๋ ๊ฒ๋ ์ข์ ๊ฒ ๊ฐ์ต๋๋ค.</br>


----------
## ๐ท๏ธ Reference


- [NLP] LDA ํ ํฝ ๋ชจ๋ธ๋ง์ ํ์ฉํ ์ฑ ๋ฆฌ๋ทฐ ๋ถ์ ํ๋ก์ ํธ (<a href="https://heytech.tistory.com/401" target="_blank">Link</a>)

- [ML ๊ณต๋ถ] ๋ง์ง ๋ฆฌ๋ทฐ๋ฅผ ํตํ ๊ฐ์ฑ๋ถ์ (๊ธ์ , ๋ถ์  ์ธ์ด ํ๋ณ) - 210521 (<a href="https://moojuksublime.tistory.com/14" target="_blank">Link</a>)

- [ํ๋ก์ ํธ] ํธํ ๋ฆฌ๋ทฐ ํ์คํธ ๋ถ์ & ๋ถ๋ฅ ๋ชจ๋ธ ์ ์ (<a href="https://hanawithdata.tistory.com/entry/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%98%B8%ED%85%94-%EB%A6%AC%EB%B7%B0-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EB%B6%84%EC%84%9D-%EB%B6%84%EB%A5%98-%EB%AA%A8%EB%8D%B8-%EC%A0%9C%EC%9E%91" target="_blank">Link</a>)

- PyKoSpacing github (<a href="https://github.com/haven-jeon/PyKoSpacing" target="_blank">Link</a>)

- Py-hanspell github (<a href="https://github.com/ssut/py-hanspell" target="_blank">Link</a>)

- ํ๊ตญ์ด ๋ง์ถค๋ฒ/๋ฌธ๋ฒ ๊ฒ์ฌ๊ธฐ (<a href="http://speller.cs.pusan.ac.kr/" target="_blank">Link</a>)

- ์ํค๋์ค - ๋ฅ๋ฌ๋์ ์ด์ฉํ ์์ฐ์ด์ฒ๋ฆฌ ์๋ฌธ (<a href="https://wikidocs.net/book/2155" target="_blank">Link</a>)


