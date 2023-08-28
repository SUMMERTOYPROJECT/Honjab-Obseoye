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

**🎤 어플리케이션 이미지**

1. 개인 e-mail을 이용하여 로그인 후 등록된 IP주소의 혼잡도 정보를 전달 받는다.
2. 가장 우선시 보이는 상단부는 실시간 스트리밍으로 전달되는 현장의 이미지 사진이다.
3. 해당 사진은 상단 버튼을 클릭하여 혼잡한 정도를 나타내는 이미지 사진으로 볼 수도 있다.
4. 중간부에서는 이미지에 대한 당시 시간과 인원수를 간편하게 파악하여 확인할 수 있다.
5. 하단부에 있는 '그래프' 버튼을 클릭하면 일정 시간 단위로 해당 위치에 있던 인원 수를 그래프로 파악할 수 있다.
6. 하단부에 있는 '스트리밍' 버튼을 클릭하면 현재 촬영되는 위치의 영상을 실시간으로 확인할 수 있다.

![image](https://github.com/KOBOTBOARD-11/2022ESWContest_mobility_6017/assets/99342700/a97be18b-7f97-4372-a41e-7aa9caf6784d)

**📖 사전에 필요한 코드 지식**

1. Route != Navigation
- Route
    - Flutter에서는 Route / Navigation을 통해 페이지를 이동할 수 있다.
    - Route에는 화면에 대한 설정 정보(표시할 위젯 / 전환 효과)가 있다.
    ```dart
    /* 애플리케이션의 시작 시 초기 Route를 "/login"으로 설정 */
    initialRoute: "/login"

    /* 해당 경로로 접근하면 HomePage 위젯이 생성 */
    routes : {
        "/login" : (context) => LoginPage(),
        "/home" : (context) => HomePage(),
        .
        .
        .
    }
    ```
- Navigation
    - Navigator는 스택 개념으로 작동을 한다. 즉, Last In First Out 특징을 갖고 있다.
    ```dart
    /* 위젯 생성 */
    ElevatedButton(                                 // 사용자와의 상호작용을 위해 클릭 가능한 동작을 수행하는 요소
        onPressed: () {                             // 버튼 클릭 시 실행될 코드
            setState(() {                           // 위젯의 상태를 업데이트
            isButton1Pressed = true;
            });
            Navigator.pushNamed(context, '/graph'); // 경로에 해당하는 새로운 페이지로 이동
        },
    )
    ```

2. Firebase
- Firebase 초기화
```dart
/* Firebase 초기화 */
void main() async {
  WidgetsFlutterBinding.ensureInitialized();            // Flutter 바인딩을 초기화          : 위젯과 그래픽 렌더링을 관리하는 Flutter의 핵심 부분
  await Firebase.initializeApp(                         // 서비스를 초기화하는 비동기 함수  : 사용하기 위해서는 앱을 초기화 해야함
    options: DefaultFirebaseOptions.currentPlatform,    // Firebase 초기화 옵션 설정        : 필요한 정보들을 제공
  );
  return runApp(MyApp ());
}

/* Firebase 앱 초기화에 필요한 여러 정보 */
static const FirebaseOptions android = FirebaseOptions(
    apiKey: 'AIzaSyDCuD25hjKtGylCHi1NtKqPHXjXAcuOEq4',      // API 키 설정          : Firebase서비스와 통신하기 위함
    appId: '1:1047002174264:web:7d8cd8952e557d4b40a7cd',    // 앱 ID 설정           : 특정 앱을 식별하는 역할
    messagingSenderId: '1047002174264',                     // 발신자 ID 설정       : FCM 서비스와 연동하여 푸쉬 알림과 메세지 관리
    projectId: 'honjab-obseoye',                            // 프로젝트 ID 설정     : Firebase프로젝트를 식별
    storageBucket: 'honjab-obseoye.appspot.com',            // 스토리지 버킷 설정   : 앱의 파일 및 미디어 저장 
);

Firebase.initializeApp();                                   // Firebase서비스 초기화 
```
- 실시간 스트리밍
```dart
StreamBuilder<DocumentSnapshot>(
    stream: FirebaseFirestore.instance.collection('users').doc('crowd').snapshots(),
    builder: (context, snapshot) {
        if (snapshot.connectionState == ConnectionState.waiting) {
        return CircularProgressIndicator();
        }

        if (!snapshot.hasData || snapshot.data == null) {
        return Text("No data available");
        }

        String imageUrl = isOn
            ? (snapshot.data?['fidt_fileUrl']) ?? ''
            : (snapshot.data?['ori_fileUrl']) ?? '';

        return imageUrl.isNotEmpty
            ? Image.network(
        imageUrl,
        width: 380,
        height: 220,
        fit: BoxFit.contain,
        )
            : CircularProgressIndicator();
    },
),
```
Test