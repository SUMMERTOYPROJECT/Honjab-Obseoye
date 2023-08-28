# 혼잡옵서예

# 공개SW 개발자 대회 


## 📋프로젝트 개요
 IP 카메라를 사용하여 실시간으로 인원을 관리하고 혼잡도를 파악하는 시스템을 개발하는 것입니다. 이를 통해 공공 장소, 상업 시설, 교통 시설 등에서 보다 효율적인 인원 관리와 안전한 환경 조성을 지원하고자 합니다.

**👀 혼잡옵서예(인구 밀집도(혼잡도) 시각화)**

**💻 개발 배경**

- 현대 사회에서는 공공 장소, 상업 시설, 교통 시설 등 다양한 장소에서 인원 관리와 혼잡도 파악이 매우 중요합니다. 특히, 인구 밀집 지역이나 이벤트 장소에서는 인원이 과도하게 몰리면 안전상의 이유로 인한 문제가 발생할 수 있습니다. 이에 따라 인원 관리를 효과적으로 수행하고 혼잡도를 실시간으로 파악할 수 있는 시스템이 필요해졌습니다.

**📌 개발 목적**

- 기존의 수동적이고 주관적인 인원 관리 방식에서 벗어나, 자동화된 시스템을 통해 효율적으로 인원을 관리할 수 있습니다. 영상 분석과 인공지능 기술을 활용하여 정확한 인원 식별과 카운팅을 수행하고, 실시간으로 인원 정보를 제공합니다.

- 현장의 혼잡도를 실시간으로 파악함으로써, 인원이 과도하게 몰리는 상황을 미리 예측하고 대응할 수 있습니다. 이를 통해 인원이 안전하고 편안한 환경에서 이동하고 대기할 수 있도록 도움을 줍니다.

- 시스템은 잠재적인 위험 상황을 빠르게 감지하고 관련된 알림을 제공합니다. 예를 들어, 인원이 너무 많이 몰려 혼잡도가 위험 수준에 도달하거나, 출입 제한 구역에 불법적인 침입이 발생하는 경우 등을 탐지하여 조기 대응 조치를 취할 수 있습니다.

- IP 카메라를 통해 제공되는 고화질 영상과 영상 분석 결과를 통해 정확한 데이터와 실시간 정보를 제공합니다. 이는 의사 결정에 필요한 정보를 제공하고, 관리자와 관련자들이 실시간으로 상황을 모니터링하고 대응할 수 있도록 돕습니다


## 🎬프로젝트 시연 동영상

 <div align="center">


</div>

## 📲 혼잡옵서예 Crowd Counting 사용 설명서
0. 기본 라이브러리 설치 
```
pip install -r requirements.txt
```

```bash
#-- requirements.txt
python==3.8 
pytorch==2.0.1
opencv-python==4.8.0.76
scipy==1.10.1
h5py==3.9.0
Pillow==9.4.0
imageio==2.31.1
nni==2.10.1
yacs==0.1.8
Pyrebase4==4.7.1
firebase-admin==5.3.0
```
1. git clone 명령어를 통해 해당 repository 다운로드
```
git clone https://github.com/Winter-Toy-Project/Honjab-Obseoye.git
```

2. 아래 명령어를 통해 pre-trained model 다운로드 
- gdown 명령어가 없을 경우 설치 후 진행
```
gdown https://drive.google.com/uc?id=1TBZXWB00mqkZnKzRvWDzR35kgKuW7nP_
unzip /content/bestmodel.zip
```

3. 파이어베이스 연동을 위한 서비스키를 다운로드 같은 경로에 삽입

```
myfirebaseservicyKey
```
4. 다음 명령어를 통해 Crod Counting 시작
```
python people_counting.py --pre ./model_best_nwpu.pth  --video_path "IP카메라 URL"
```

![counting2](https://github.com/Winter-Toy-Project/Honjab-Obseoye/assets/79856225/37d96356-8ba5-4d8d-9e01-a7c89333e3c3)

![fidt2](https://github.com/Winter-Toy-Project/Honjab-Obseoye/assets/79856225/d7e48a26-c13b-4245-b954-2c0eed249354)

#-- 참고 링크 : https://github.com/dk-liang/FIDTM.git 
</div>

## 🔎 파일 구조

```
...
|-- images
|-- Networks
    └── HR_NEt/...
|-- config.py
|-- dataset.py
|-- image.py
|-- myfirebaseservicyKey
|-- LICENSE
|-- model_best_nwpu.pth 
|-- people_counting.py
|-- README.md
|-- requirements.txt
|-- utils.py

...
```

## 📂브랜치별 개요 및 링크

✨ 브랜치 링크를 누르면 각 브랜치 실행 방법을 확인 할 수 있습니다.


[🛠 main_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye): main  
[🛠 App_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye/tree/App): App  
[🛠 AI_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye/tree/datasicence): AI  
[🛠 Database_dev](https://github.com/Winter-Toy-Project/Honjab-Obseoye): DataBase (예정)  


## 🗝️혼잡옵서예 실행순서

- 작성

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
