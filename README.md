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

**🔎 파일 구조**

```
...
├── lib/  
│   ├── graph_components/  
│   │   └── graph_page.dart
│   ├── home_components/  
│   │   └── bottom_bar.dart
│   │   └── bottom_button.dart
│   │   └── count_value.dart
│   │   └── custom_form.dart
│   │   └── custom_text_form_field.dart
│   │   └── firebase_option.dart
│   │   └── image_check.dart
│   │   └── top_bar.dart
│   ├── page_components/  
│   │   └── home_page.dart
│   │   └── login_page.dart
│   │   └── register_page.dart
│   ├── setting_components/  
│   │   └── ip_list.dart  
│   │   └── stting_page.dart
│   ├── video_components/  
│   │   └── LiveStreamingVideo.dart 
│   │   └── LiveStreamPage.dart
│   │   └── websockets.dart
│   ├── generated_plugin_registrant.dart
│   ├── main.dart  
│   ├── thme.dart  
│ 
...
```