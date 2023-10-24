<h1 align="center">제목 정하는 중 👍</h1>

<center>
    <img src="./img/test.jpg"  style="zoom:76%;" align="center"/>
</center>

> [한국품질재단] 스마트팩토리SW개발과정 / 4팀

🎬[Demo 시연영상](https://www.youtube.com/watch?v=dhMrKTwNI8U&lc=UgzCJR3WxkvsckRyyO94AaABAg&ab_channel=%EB%94%B0%EB%9D%BC%ED%95%98%EB%A9%B4%EC%84%9C%EB%B0%B0%EC%9A%B0%EB%8A%94IT)  
🎤[발표](https://www.youtube.com/watch?v=dhMrKTwNI8U&lc=UgzCJR3WxkvsckRyyO94AaABAg&ab_channel=%EB%94%B0%EB%9D%BC%ED%95%98%EB%A9%B4%EC%84%9C%EB%B0%B0%EC%9A%B0%EB%8A%94IT)  
📃[프로젝트 회고록](https://joon-coding.tistory.com/)

<br>

## ✨ 프로젝트 설명

```sh
1. 배터리 산업에 필요한 원자재의 가격을 수집하여 그래프로 시각화하여
가격 동향을 쉽게 파악할 수 있습니다

2. 하도급 연동제에 따른 큰 가격의 변동을 예측하도록
AI 모델을 활용해 가격예측을 할 수 있습니다
```

## 🎬 [데모 사이트](http://3.39.23.184/) <- 클릭하면 이동됩니다!

```sh
현재는 AWS 프론트엔드, 백엔드, RDS로 배포한 상태입니다.
```

## 📌 프로젝트 목표

```sh
python을 사용해(원천 데이터 에서) 데이터 크롤링을 하여 DB에 (크롤링 주기) 저장을 하고
WEB으로 차트를 통해 자재정보를 보여주는 서비스를 만들었습니다
```

## 🔍 Overview

### 1. 데이터 크롤링(크롤링 방식 설명)

<center>
    <!-- <img src="./img/pic2.png" /> -->
</center>
python을 사용해 데이터 크롤링을 하고 WAS에 전달하여 데이터 저장

<br>데이터 종류

- 수집할 원자재 정보<br>
- 원자재 가격정보<br>
- 원자재의 해당하는 이슈 정보<br>
  <수집장면 넣을 예정>
  <br>

### 2. 원자재 정보 출력

수집한 데이터를 차트로 표현하여 가격 동향 확인

<center>
    <img src="./img/메인_02.png" />
    <div align="center">메인 페이지</div>
    <img src="./img/메인_01.png" />
    <div align="center">디테일 페이지</div>
</center>

<br>

### 3. kubernetes를 사용한 클라우드 시스템 구축

<center>
    <img src="./img/아키텍쳐 구조도.png" />
    <div align="center">아키텍쳐 구조도</div>
</center><br>
kubernetes를 자원 사용의 효율을 높이고 윤영 관리의 편의성을 높여주었습니다<br>

<br>

### 3-1. kubernetes Blue/Green 배포 설청

Jenkins와 연동해 배포시 Blue/Green 형식으로 무중단 배포를 구현하였습니다<br>
Jenkins의 배포 횟수가 홀수시 최신버전이 A 컨트롤러에 2개의 Pod가 생성되고<br>
이전 버전인 B컨트롤러 Pod가 2개 삭제 되는 방식으로 구현하였습니다<br>
(짝수의 경우 A, B 컨트롤러 반대로 진행)

<center>
    <img src="./img/blue_green_03.png" />
    <div align="center">배포전</div>
    <img src="./img/blue_green_01.png" />
    <div align="center">배포중</div>
    <img src="./img/blue_green_02.png" />
    <div align="center">배포후</div>
</center>
<center>
    
</center>

<br>

### 3-2. kubernetes MySQL 2중화 구축

DB를 master와 slave로 2중화 하여 master의 정보를 slave에 저장하여 데이터 안정성 상승

<center>
    <img src="./img/k8s_db_01.png" />
    <div align="center">master에서 확인한 slave</div>
    <img src="./img/k8s_db_02.png" />
    <div align="center">slave의 master 연결 상태</div>
</center>
<br>
*이슈사항<br>(세부 사항은 하단 아키텍쳐 git 서술)
- mysql Pod 고정해서 지정<br>
- mysql user 보안<br>
- kubernetes 네트워크<br>

<br>

### 4. Jenkins를 사용한 CI/CD

Jenkins를 사용해 AWS와 kubernetes 자동화 배포 실행

<center>
    <img src="./img/Jenkins_1.PNG" />
    <div align="center">Jenkins 작업목록</div>
    <img src="./img/Jenkins_2.png" />
    <div align="center">Jenkins 작업내역</div>
</center>
<center>
    
</center>
 <br>
<br>
## 🔧 각 프로젝트 상세 설명

### [프론트 엔드 github](https://github.com/Resource-Predicters/Front_End) <- 클릭하면 이동됩니다!

### [백 엔드 github](https://github.com/Resource-Predicters/Back_End) <- 클릭하면 이동됩니다!

### [데이터수집 & 인공지능 github](https://github.com/Resource-Predicters/Data) <- 클릭하면 이동됩니다!

### [아키텍쳐 github](https://github.com/Resource-Predicters/Data) <- 클릭하면 이동됩니다!

## 🤼‍♂️팀원

Team Leader : 🐯**이재준**

DataGathering & AI : 🐶 **박선규**

Frontend : 🐺 **이윤정**

CI/CD : 🐱 **홍미지**