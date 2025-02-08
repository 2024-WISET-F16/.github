# ☀️ 자연광 유입 환경에서 최소 조도 센서 기반<br/>조도맵을 생성하는 딥러닝 모델
> **2024년 WISET 여대학원생 공학연구팀제 지원사업 심화과정**<br/>
> **전산·컴퓨터 분과 2위**<br/><br/>
> 연구과제명 : 자연광 유입 환경에서 최소 조도 센서 기반 조도맵을 생성하는 딥러닝 모델<br/>
> 연구개발기간 : 2024.04.01 ~ 2024.10.31<br/>
> 주관부처 : 과학기술정보통신부<br/>
> 주관기관 : 한국여성과학기술인육성재단<br/>

<br/>

## 💪 Team
|<img src="https://avatars.githubusercontent.com/u/91596873?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/99874673?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/100507512?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/105366292?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|이유빈<br/>[@youbbin](https://github.com/youbbin)|장현희<br/>[@hh830](https://github.com/hh830)|곽민정<br/>[@kwakminjung](https://github.com/kwakminjung)|김유진<br/>[@yujinkimkimkim](https://github.com/yujinkimkimkim)|  

<br/>

## 👩‍💻 R&R
| 파트 | 이름 | 역할 |
| ------------ | -------------------------------------------------------------- | ----------------------------------------------------- |
| Data, AI, BE | 이유빈(팀장) | 실내 조도 데이터 전처리 및 분석 <br/> 실내 조도 데이터베이스 구축 <br/> Pytorch 딥러닝 모델 설계 및 성능 최적화 <br/> | 
| BE, AI | 장현희 | Pytorch 딥러닝 모델 설계 <br/> Fast API로 모델 서빙 <br/> Spring Boot로 서버 실시간 데이터 전송 개발 <br/> | 
| BE, AI | 곽민정 | Pytorch 딥러닝 모델 설계 <br/> Spring Boot 서버와 일출, 일몰 API 연동 <br/> 서버 배포 <br/> | 
| FE | 김유진 | Flutter를 사용한 모니터링 어플 디자인, 구현 |

<br/>

## 📋 About The Project
<p align="middle" >
  <img src="https://github.com/user-attachments/assets/39376d7f-5f12-4e37-a2c7-57936568043a"/>
</p>

**센서의 최소화** 또는 **센서리스 기술** 도입을 위해 창 측 최소의 센서를 활용하여 **실내 거리별 상세한 조도맵**을 생성하는 딥러닝 모델 개발 프로젝트입니다. 실내 조도 산출 결과를 모니터링 어플을 통해 실시간으로 확인할 수 있습니다.

<br/>

## 👀 시연 영상
https://github.com/user-attachments/assets/e7f23256-6229-40f8-9512-c6af8109bf6c

<br/>

## 🔎 개발 동기
자연광 연계 제어 시스템에는 실내 조도 분포를 정확하게 파악하는 것이 필수적으로 필요 <br/>
기존에는 다수의 센서를 실내 지점마다 설치하여 조도를 측정했지만, 이는 네트워크 과부하로 인한 에너지 과소비, 측정 데이터 처리 및 분석 비용 증가 등의 문제를 유발한다. <br/>
따라서 센서 개수의 최소화를 통해 에너지 절약, 시스템 간소화, 최소한의 데이터 활용, 자유로운 공간 활용 등의 효과를 얻고자 한다. <br/>

<br/>

## ⚒️ 기술 스택
Java, Spring Boot, FastAPI, Pytorch, MongoDB, Flutter, AWS, Docker, Nginx

<br/>

## 🖥️ 학습 데이터셋 구축
<img src="https://github.com/user-attachments/assets/2d52a012-5d5a-4200-aef1-db39d25fa2ea"/> <br/>
- RGB 센서 기반 조도 센싱 디바이스 제작 <br/>
- 공주대학교 실험실에 지점별 조도 데이터 수집 환경 설계 후 지점별 조도, 태양 위치 정보 수집 <br/>
- MongoDB 기반의 실내 조도 데이터베이스 구축 <br/>
- 약 100만 개의 훈련 데이터 구축 <br/>
  
<br/>

## 📌 DNN 모델 개발
![image](https://github.com/user-attachments/assets/0fd4e555-a339-471c-a8d6-57719aefc0c6)
<br/>
- 최소 조도 센서 데이터 및 태양의 위치와 거리별 조도 간의 관계를 학습하여 실내 상세 조도맵을 생성하는 딥러닝 모델 설계 <br/>
- 실내 조도 데이터셋을 사용하여 모델 훈련 <br/>
- 조기종료 기법을 적용하여 160 에포크에서 종료 <br/>
- 은닉층은 5개의 완전연결층(Fully Connected Layer)으로 구성하였으며 각 층은 128개의 노드로 이루어짐 <br/>

<br/>

<img src="https://github.com/user-attachments/assets/b17626f7-ab5f-4979-9cc5-8f406c163f98" width="400">
<img src="https://github.com/user-attachments/assets/07e547db-d1e7-4214-a737-d350e4a25122" width="400">

<br/>

- 조도 산출 성능 최적화를 위해 하이퍼파라미터 튜닝 수행
- 배치 크기, 은닉층의 노드 수, 학습률을 다양하게 조합하여 실험
- 각 조합별 에포크 수는 10회, 손실함수는 평균절대오차(MAE)로 설정
- 배치 크기 64, 은닉층의 노드 수 64, 학습률 0.001일 때 최적의 성능을 보임


→ 최종 결과 Train Loss 18Lux, Test Loss 19Lux 달성 <br/>

