# Flutter

## 기본 위젯

- `Container`: 가장 기본적인 위젯
  - child: 하위 위젯
  - padding: 여백
    ```dart
    EdgeInsets.all(30) // 모든 방향에 30만큼 여백
    EdgeInsets.fromLTRB(left: , top: , right: , bottom: ) // 상하좌우 여백
    EdgeInsets.only(left: ) // 한 방향만
    EdgeInsets.symmetric(vertical: , horizontal: ) // 세로, 가로방향
    ```
  - width, height: 높이, 너비
- `Center`: 가운데 정렬 위젯
- `Image`: 이미지
  - Image.asset(): 폴더 내 이미지
  - Image.network(): 인터넷 이미지
  - MediaQuery: 화면 정보
    - MediaQuery.of(context).size.width
- `Text`: 텍스트 위젯
  - style: TextStyle
    - fontSize, fontWeight, color 등
- `Column`: 위에서 아래로
- `Row`: 왼쪽에서 오른쪽으로
  - mainAxisAlignment: 메인 방향
    - center, start, spaceAround, spaceEvenly
  - crossAxisAlignment: 수직 방향
- `ListView`: 스크롤 화면 위젯
  - scrollDirection: 스크롤 방향
  - `ListView.builder()`: 리스트 위젯
    - itemCount, itemBuilder
- `Stack`: 위젯 위에 위젯 쌓기
- `Button`
  - TextButton: 기본
  - ElevatedButton: 배경색
  - OutlinedButton: 테두리
  - IconButton: 아이콘

## 화면 전환

### 이동

```dart
Navigator.of(context).push(
  MaterialPageRoute(
    builder: (BuildContext context) => SecondScreen(),
  ),
)
```

### 뒤로 가기

```dart
Navigator.of(context).pop();
```

## 상태

- `StatelessWidget`: 상태가 변하지 않는 위젯
- `StatefulWidget`: 상태를 포함한 위젯. 변화에 대한 이벤트 수행

### Provider

1. Provider(제공): 상위 위젯에서 선언한 객체를 그대로 하위 위젯에서 사용할 수 있도록 제공
2. Cousumer(사용): 하위 위젯에서 상위 위젯의 객체를 받아와 사용
   1. Provider.of(context) 형태로 많이 사용
3. ChangeNotifier: 특정 클래스가 변화할 수 있는 값을 포함할 때 상속받아야 하는 클래스
   1. notifyListeners(): 값이 변했음을 알림
4. ChangeNotifierProvider: ChangeNotifier를 상속한 클래스로 만들어진 객체를 제공해주는 Provider
