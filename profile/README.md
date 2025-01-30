# 자연광 유입 환경에서 최소 조도 센서 기반<br/>조도맵을 생성하는 딥러닝 모델
> **2024년 WISET 여대학원생 공학연구팀제 지원사업 심화과정**<br/>
> **전산·컴퓨터 분과 2위**<br/><br/>
> 연구과제명 : 자연광 유입 환경에서 최소 조도 센서 기반 조도맵을 생성하는 딥러닝 모델<br/>
> 연구개발기간 : 2024.04.01 ~ 2024.10.31<br/>
> 주관부처 : 과학기술정보통신부<br/>
> 주관기관 : 한국여성과학기술인육성재단<br/>

<br/>

## About The Project
<p align="middle" >
  <img src="https://github.com/user-attachments/assets/39376d7f-5f12-4e37-a2c7-57936568043a"/>
</p>

**센서의 최소화** 또는 **센서리스 기술** 도입을 위해 창 측 최소의 센서를 활용하여 **실내 거리별 상세한 조도맵**을 생성하는 딥러닝 모델 개발 프로젝트입니다. 실내 조도 산출 결과를 모니터링 어플을 통해 실시간으로 확인할 수 있습니다.

<br/>

## Team
|<img src="https://avatars.githubusercontent.com/u/91596873?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/99874673?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/100507512?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/105366292?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|이유빈<br/>[@youbbin](https://github.com/youbbin)|장현희<br/>[@hh830](https://github.com/hh830)|곽민정<br/>[@kwakminjung](https://github.com/kwakminjung)|김유진<br/>[@yujinkimkimkim](https://github.com/yujinkimkimkim)|  

<br/>

## 시연 영상
https://github.com/user-attachments/assets/e7f23256-6229-40f8-9512-c6af8109bf6c

<br/>

## DNN 모델 개발
![image](https://github.com/user-attachments/assets/0fd4e555-a339-471c-a8d6-57719aefc0c6)
<br/>
최소 조도 센서 데이터 및 태양의 위치와 거리별 조도 간의 관계를 학습하여 실내 상세 조도맵을 생성하는 딥러닝 모델 설계 <br/>
실내 조도 데이터셋을 사용하여 모델 훈련 <br/>
조기종료 기법을 적용하여 160 에포크에서 종료 <br/>
은닉층은 5개의 완전연결층(Fully Connected Layer)으로 구성하였으며 각 층은 128개의 노드로 이루어짐 <br/>
Train Loss 18Lux, Test Loss 19Lux 달성 <br/>

<br/>

![image](https://github.com/user-attachments/assets/b17626f7-ab5f-4979-9cc5-8f406c163f98)
![image](https://github.com/user-attachments/assets/07e547db-d1e7-4214-a737-d350e4a25122)
<br/>
조도 산출 성능 최적화를 위해 하이퍼파라미터 튜닝 수행 <br/>
배치 크기, 은닉층의 노드 수, 학습률을 다양하게 조합하여 실험 <br/>
각 조합별 에포크 수는 10회, 손실함수는 평균절대오차(MAE)로 설정 <br/>
배치 크기 64, 은닉층의 노드 수 64, 학습률 0.001일 때 최적의 성능을 보임 <br/>


## 실시간 데이터 조회, SSE

## 
