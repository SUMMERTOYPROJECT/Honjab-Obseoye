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

**🎮 Firebase 연동**

1. 자신의 OS에 맞게 CLI설치 [
[공식문서](https://firebase.google.com/docs/cli?authuser=1&hl=ko#install_the_firebase_cli)]
- Mac의 경우 터미널에서 다음과 같은 명령어를 수행
    ```shell
    curl -sL https://firebase.tools | bash
    ```
 - 설치가 완료되었다면 터미널에서 firebase 로그인
    ```shell
    firebase login
    ```
- 제대로 로그인 되었는지 확인
    ```shell
    firebase projects:list
    ```

2. 프로젝트 생성 후 Flutter app 추가 후 다음 실행
<img width="562" alt="image" src="https://github.com/TEAMA0520/Honjab-Obseoye/assets/99342700/59b61916-bd1d-4557-938e-75d59e89dd32">

3. 홈 디렉토리에서 다음 명령어 실행
```shell
dart pub global activate flutterfire_cli
```
- 위 명령어를 수행시 환경변수를 설정하라는 문구가 나올 때가 있다.  아래 명령어로 설정 파일 수정
```shell
cd
vi .zshrc
```

-  다음과 같은 코드를 추가하여 환경변수를 추가 해준다. 이 때 터미널을 껐다 켜준다 → 안된다면 재부팅
```shell
export PATH="$PATH":"$HOME/.pub-cache/bin"
```

4. 모두 완료되었다면 프로젝트 디렉토리로 이동한 후 다음 명령어 수행
```shell
flutterfire configure --"자신의 프로젝트"
```
<img width="563" alt="image" src="https://github.com/TEAMA0520/Honjab-Obseoye/assets/99342700/40f55898-73c2-44b3-a330-0cee93e2e5c8">
- 원래는 수동으로 추가했어야하는 부분들이 자동으로 추가되어있다.

5. 플러터 프로젝트를 확인해보면 firebase가 추가되어있다.
    - 자신이 만들고싶은 부분만 체크하고 엔터 후 y
<img width="564" alt="image" src="https://github.com/TEAMA0520/Honjab-Obseoye/assets/99342700/7b0da949-a5c3-4a0c-bcd6-cb7d33a73313">

6. firebase_core 추가
```shell
flutter pub add firebase_core
```
```shell
flutter pub get
// 위 명령어로 firebase 추가
```

7. main에 코드 추가
<img width="561" alt="image" src="https://github.com/TEAMA0520/Honjab-Obseoye/assets/99342700/7a6dd0e2-3bbe-4839-a1d1-6c247d9dbb73">
- 위 코드를 복사하여 main 함수에 붙여넣기 
- main에 WidgetsFlutterBinding.ensureInitialized(); 코드 추가
- awit이 붙어있으므로 main() async 

```shell
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';
import 'firebase_options.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );
  runApp(MyApp());
}
```
- 실행을 눌러서 오류없이 실행이 된다면 firebase추가 완료 

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
/* 데이터스트림을 보며 데이터가 업데이트 될 때 마다 UI를 자동 렌더링 */
StreamBuilder<DocumentSnapshot>(
    /* 데이터베이스의 해당 문서가 변경될 때마다 앱으로 스냅샷이 전송되어 업데이트를 수신 */
    stream: FirebaseFirestore.instance.collection('users').doc('crowd').snapshots(),
    builder: (context, snapshot) {
        if (snapshot.connectionState == ConnectionState.waiting) { // 데이터가 아직 없으면
        return CircularProgressIndicator();                        // 로딩중인 화면을 나타냄
        }
        String imageUrl = snapshot.data['ori_fileUrl'];            // 스냅샷 데이터에서 이미지URL 가져오기 

        return imageUrl.network(imageUrl)                          // 이미지URL 보여주기
    },
),
```