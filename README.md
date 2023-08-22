# 혼잡옵서예

# 공개SW 개발자 대회 


## 📋프로젝트 개요
 IP 카메라를 사용하여 실시간으로 인원을 관리하고 혼잡도를 파악하는 시스템을 개발하는 것입니다. 이를 통해 공공 장소, 상업 시설, 교통 시설 등에서 보다 효율적인 인원 관리와 안전한 환경 조성을 지원하고자 합니다.

**👀 혼잡옵서예(인구 밀집도(혼잡도) 시각화)**


## 🗝️혼잡옵서예 라이브 스트리밍 실행순서

### 가상환경 셋팅 또는 requirements.txt 설치
- source stream/bin/activate
- pip install -r requirements.txt  
둘 중 원하는걸로 

### 라이브 스트리밍 실행

- live_stream/stream.py 자신의 IP주소를 입력
- python stream.py를 이용하여 라이브 스트리밍 실행

### 라이브 영상을 websocket 통신으로 데이터 변환
- stream_to_app.py에 라이브 스트리밍 URL 입력
- python stream_to_app.py 실행
    - IP카메라 스트리밍 -> 스트리밍 데이터를 변환 후 -> 다시 웹 소켓 통신





# Raspberry_monitoring

[🛠 0. 라즈베리파이 초기 셋팅](https://github.com/junyong1111/Raspberry_monitoring/tree/main/rasp_live/setting_0) 

[🛠 1. 라즈베리파이 OpenCV 설치](https://github.com/junyong1111/Raspberry_monitoring/tree/main/rasp_live/setting_1) 

[🛠 2. 실시간 웹캠 스트리밍 with Flask](https://github.com/junyong1111/Raspberry_monitoring/tree/main/rasp_live/live_stream) 

[🛠 3. 포트포워딩을 이용하여 외부 접속](https://github.com/junyong1111/Raspberry_monitoring/tree/main/rasp_live/port_forwarding) 

## 📂브랜치별 개요 및 링크

✨ 브랜치 링크를 누르면 각 브랜치 실행 방법을 확인 할 수 있습니다.


[🛠 main_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye): main  
[🛠 App_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye/tree/App): App  
[🛠 AI_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye/tree/datasicence): AI  
[🛠 Database_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye): DataBase (예정)  



## 🦉 팀 소개 및 역할

1.🧑🏻‍💻 최병우

- Position : 팀장
- Github: <https://github.com/cbw6088>
- Email : khj4186@naver.com
- Role : TeamLeader, App, UI design, Backend

2.👨🏾‍💻 박준용

- Position : 팀원
- Github: <https://github.com/junyong1111>
- Email : jypark93@kookmin.ac.kr
- Role : AI, Backend




### Git Commit Guidline
<img width="535" alt="화면 캡처 2022-11-10 134122" src="https://user-images.githubusercontent.com/85275893/201002326-84ab80ac-af5f-4b58-b216-26341ddd6079.png">
