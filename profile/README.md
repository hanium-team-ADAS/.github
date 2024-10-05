
# 🏥 비대면 진료 서비스 프로젝트

## 1. 프로젝트 개요 - 송희 ✍️
> 비대면 진료 서비스의 필요성은 금년도 의사 파업과 코로나19 재확산으로 인해 더욱 부각되었습니다. 본 프로젝트에서는 열화상 카메라로 수집한 데이터를 AI 기반 알고리즘으로 보정하였으며, **P2P 통신 프로토콜인 WebRTC** 기술을 적용하여 환자와 의료진 간 원활한 소통을 지원하였습니다. 또한, 다양한 환경에서 안정적으로 활용 가능한 **클라우드 기반 시스템**을 구현하여 비대면 진료의 효율성을 극대화하였습니다.

## 2. 역할 분담 👥
- **이송희:** Backend
- **안효원:** AI, Backend
- **한예지:** IoT, Frontend
- **신서영:** Frontend
- **정윤제:** AI

## 3. 기술 스택 💻
- **백엔드:** Spring, WebRTC, MySQL
- **프론트엔드:** React, HTML, CSS
- **AI 모델:** TensorFlow, OpenCV
- **클라우드:** AWS, Docker
- **하드웨어:** Raspberry Pi, 열화상 카메라 모듈

## 4. 설계 📐
### [서비스 구성도]
- 프론트엔드 서버(React), 벡엔드 서버(Spring 서버), IoT Core, AI 서버(FastAPI), 데이터베이스 서버(Amazon RDS)로 구성되어있습니다.
  ![서비스 구성도](https://github.com/user-attachments/assets/fb6a2c87-d3cc-4cf9-bcf5-3ef83ef62019)


### [흐름도]
- 환자가 회원 가입과 로그인 후 진료 예약 및 진료를 진행하는 과정을 수행합니다.
  ![환자흐름도](https://github.com/user-attachments/assets/67d3fa33-5688-46de-9822-5e4815373f02)
- 의사는 회원 가입과 로그인 후 일정 조회 및 진료를 수행하는 과정을 수행합니다.
  ![의사흐름도](https://github.com/user-attachments/assets/bd49723b-7961-48aa-b3dd-749a21953b8a)


### 4.2 모델 설계 - 효원
- 데이터 수집부터 모델 학습 및 예측 과정에 대한 간단한 설명과 모델 구조를 포함합니다.

### 4.3 서버(Spring) 설계 - 송희
- **ERD:** 데이터베이스 구조를 명확하게 시각화합니다.
- **API 명세:** 각 기능에 대한 API 명세를 작성하여 개발 및 테스트에 활용할 수 있습니다.

### 4.4 클라이언트 화면 구성 - 서영
- 각 화면의 주요 기능을 스크린샷과 함께 설명합니다.

### [초기화면]
- 페이지 초기 화면으로 상단바와 중앙 버튼으로 원하는 페이지로의 이동이 가능합니다.

![main](https://github.com/user-attachments/assets/cd74b2a3-aa47-4439-a141-80e4b5091f21)

### [회원가입]
- 필드 입력 후 하단 회원가입 버튼을 눌러 회원가입 가능합니다.
  - 사용자 유형에 따라 다른 페이지를 제공합니다.
    
![doctorSignup](https://github.com/user-attachments/assets/af6f2cc7-f069-4ee5-98ae-0d30726018fa)
![patientSignup](https://github.com/user-attachments/assets/8815a9e8-3543-4eca-8abf-2cefe793868a)

### [로그인]
- 기존 회원의 경우 : 사용자 유형 선택 후 이메일과 비밀번호를 입력하여 로그인 가능합니다.
- 기존 회원이 아닌 경우 : 하단의 사용자 유형에 따른 회원가입 페이지로의 이동을 유도합니다.
  
![login](https://github.com/user-attachments/assets/b91e4004-e3e8-4c12-adcc-d6d2c2285cc6)

### [진료 예약 페이지]
- 예약 메뉴 선택시 일반 회원에게 보여지는 페이지입니다.
  - 예약 가능한 의사 리스트를 조회할 수 있습니다.
  - 필드 입력 후 하단 버튼을 통해 진료 예약이 가능합니다.
  - 우측 달력에서 날짜 선택시 해당 날짜의 예약 내역을 조회 할 수 있습니다.
      - 예약 취소가 가능합니다.
        
![KakaoTalk_20240902_012314761](https://github.com/user-attachments/assets/bb5dbd99-5c8e-4a06-938e-b4b41dc6ecc1)


### [진료 일정 조회 페이지]
- 예약 메뉴 선택시 의사 회원에게 보여지는 페이지입니다.
  - 달력에서 날짜 선택시 해당 날짜에 요청된 진료 예약 내역을 조회 할 수 있습니다.
  - 예약은 3가지 상태로 관리됩니다.
      - 신규 예약 : 체크 박스 클릭시 수락 또는 거절 팝업 생성
      - 수락한 예약
      - 거절한 예약
        
![KakaoTalk_20240902_012314761_01](https://github.com/user-attachments/assets/02bbff30-4456-474f-a615-f9768f3676ec)


### [원격 진료 페이지]
- 화상 통화 기능 제공
  - 화상 통화를 이용한 원격 진료 환경을 제공합니다.
- 체온 측정 및 관리 기능 제공
  - 오른쪽 상단 버튼을 통해 체온 측정이 가능합니다.
  - 측정된 체온은 즉시 확인 할 수 있습니다.
    
![1](https://github.com/user-attachments/assets/cf1eab92-8ea2-480d-aecd-0439e21ae1d9)



### 4.5 하드웨어 설계 - 예지
- 하드웨어/센서 구조도 및 **MQTT Topic Format**을 포함하여 통신 구조를 설명합니다.
### [하드웨어/센서 구조도]
- 라즈베리파이는 연결된 Adafruit AMG8833 IR 열화상 카메라를 통해 실시간으로 8x8 체온 데이터를 수집합니다. 보간법을 사용하여 240x240 형태의 열화상 이미지를 생성합니다. 수집한 열화상 데이터는 S3에 업로드 합니다.
- 업로드한 S3 이미지 파일의 경로, 8x8 체온 데이터를 MQTT 메시지로 Publish하여 EC2에게 알립니다.
  ![설계도](https://github.com/user-attachments/assets/ad3e2a0f-26b2-41ad-98f5-71dc7f10e661)

### [MQTT Topic Format]
- MQTT 메시지를 Topic를 기반으로 구분하여 사진 촬영 요청과 응답을 수행합니다.
  ![Topic](https://github.com/user-attachments/assets/4d510a81-6204-45f4-aba8-0d487db1553e)


## 5. 문제 해결 🚀
- 각 팀원은 프로젝트 진행 중 발생한 문제와 해결 방법을 개인 블로그에 기록하고, 아래 링크를 통해 공유합니다.
  - [효원의 문제 해결 사례](#)
  - [예지의 문제 해결 사례](#)
  - [서영의 문제 해결 사례](#)

## 6. 결과 📊
- 프로젝트의 결과를 보여주는 시연 영상 입니다.
  - [![프로젝트 시연 영상](https://img.youtube.com/vi/6GbMcSn05-M/0.jpg)](https://youtu.be/6GbMcSn05-M?si=EAY_PN3GieGmysrB)

## 7. 성과 🏆
- **수상 내역:** 2024년 한이음 ICT멘토링 공모전 입선
- **논문 발표:** 'AI 기술을 활용한 스마트 의료 시스템 설계' 논문 게재
