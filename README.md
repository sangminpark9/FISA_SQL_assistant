# 숙소 추천 사이트

## 팀 이름: What should I do (부제: 어떡하조)

### 제작한 사이트: 여행지 숙소 검색기

![Main Image](sandbox:/mnt/data/Untitled.png)

## 기능

여행가는 지역과 원하는 부대시설을 입력하면 숙소를 추천해줍니다.

### Why?

- ‘공용시설’, ‘부대시설’을 하나하나 체크해야 하는데, 리스트가 길고 많습니다.
- 따라서, 원하는 것들만 한 줄로 입력할 수 있게 하면 UX적으로 편리할 것 같습니다.

![Functionality Image](sandbox:/mnt/data/Untitled%201.png)

![Another Feature](sandbox:/mnt/data/Untitled%202.png)

### 데이터 출처

우리문화데이터 > 숙박 정보

## 사이트

[wsid ai](https://wsidsecondproject-ni43f8xuc2jdglmnf9bzsd.streamlit.app/)

## 트러블 슈팅

### 1. ‘제주도’, ‘경기도’와 같이 3글자인 지역명이 입력되는 경우 오류 발생

- **원인**: DB에 ‘제주’, ‘경기’로 저장되어 있었기 때문
- **해결**: 

![Solution Image](sandbox:/mnt/data/Untitled%203.png)

    - assistant라는 파라미터를 추가로 사용했습니다.
    - **assistant란?**
        - 주요 항목은 아니지만 제약 조건 등을 보조적으로 사용하기 위한 장치입니다.
        - 지역명이 3글자로 들어올 경우 앞 2글자만 추출해서 사용합니다.
        - response할 때 자주 생기는 오류들을 ‘절대 조건’으로 처리합니다.
            - 예: 테이블 명 앞에 자꾸 작은따옴표를 넣어서 오류가 발생
            - 테이블 명 앞에 작은따옴표를 절대 넣지 말라는 내용을 assistant에 추가

### 2. git에 .env 파일 업로드 문제

- git에 .env 파일이 올라가서 선생님의 API 사용을 못하게 되는 문제가 발생했습니다.
- .env 파일은 절대 올리지 마세요.

### 3. .env 파일에 있는 User

- Mac에 ‘USER’라는 환경변수가 있어서 에러가 발생했습니다.
- USER → USERNAME으로 변경해서 사용했습니다.

## 추가하고 싶은 기능

### 1. Top 3를 뽑는 조건

- 현재는 특정 조건 없이 top 3만 뽑고 있습니다.
- 정렬하는 조건들도 추가하고 싶습니다.
- 현재 위치를 기준으로 거리순 가까운 추천 등을 넣고 싶습니다.

### 2. 원본 DB에 부족한 정보를 크롤링하여 DB에 추가하기

![Data Crawling Image](sandbox:/mnt/data/Untitled%204.png)

![Additional Feature](sandbox:/mnt/data/Untitled%205.png)

### 3. 실시간 정보

- 실시간으로 남아있는 객실 등의 정보가 있으면 좋을 것 같습니다.
- 빈방이 없는 경우 추천 리스트에서 제외