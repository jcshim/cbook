# 📚 부록

---

## 💻 raylib 설치 가이드 (Visual Studio + NuGet)

**raylib는 C언어로 게임을 쉽게 만들 수 있는 라이브러리예요.**  
아래 단계대로 설치하면 바로 사용 가능합니다!

---

### ✅ 1. Visual Studio 설치

- [https://visualstudio.microsoft.com/ko](https://visualstudio.microsoft.com/ko) 에서  
  **Community 버전**을 다운로드하고 설치해 주세요.
- 설치 중에는 **“C++을 사용한 데스크톱 개발”** 항목을 꼭 선택하세요.

---

### ✅ 2. 빈 프로젝트 만들기

- Visual Studio 실행  
- `파일 > 새로 만들기 > 프로젝트`  
- `빈 프로젝트(Empty Project)` 선택 → 이름 지정 후 만들기

---

### ✅ 3. NuGet으로 raylib 설치

1. 솔루션 탐색기에서 프로젝트를 **오른쪽 클릭**  
2. `NuGet 패키지 관리` 클릭  
3. 상단 `찾아보기` 탭에서 `raylib` 검색  
4. `raylib` 또는 `raylib-cpp` 선택 후 **설치**

🎉 이제 raylib를 코드에서 사용할 수 있어요!

---

## 🧾 완성된 코드 예제 모음

**책 속 모든 예제 코드**는 아래 GitHub 링크에서 확인할 수 있어요:

🔗 [https://github.com/your-username/c-kids-games](https://github.com/your-username/c-kids-games)  
(또는 교재에 인쇄된 QR코드를 스캔해 보세요!)

```text
📁 예제 폴더 구성:
- 01_HelloWorld/
- 02_Variables/
- 03_Graphics_Basics/
- 04_PingPongGame/
- 05_SnakeGame/
```

---

## ⌨️ 키보드 단축키 정리표

| 기능 | 단축키 |
|------|--------|
| 프로젝트 실행 (디버깅 없이) | `Ctrl + F5` |
| 코드 자동 정렬 | `Ctrl + K`, `Ctrl + D` |
| 한 줄 주석 처리 | `Ctrl + K`, `Ctrl + C` |
| 주석 해제 | `Ctrl + K`, `Ctrl + U` |
| 새 파일 만들기 | `Ctrl + N` |
| 찾기 | `Ctrl + F` |
| 전체 찾기 | `Ctrl + Shift + F` |

💡 외워두면 훨씬 빠르게 코딩할 수 있어요!

---

## 📚 C언어 용어 미니 사전

| 용어 | 뜻 |
|------|-----|
| `printf` | 글자나 숫자를 출력하는 함수 |
| `scanf` | 키보드로 입력을 받는 함수 |
| `int` | 정수를 저장하는 자료형 |
| `float` | 소수점을 저장하는 자료형 |
| `char` | 글자 하나를 저장하는 자료형 |
| `if` | 조건에 따라 명령을 선택하는 문장 |
| `for` | 정해진 횟수만큼 반복하는 문장 |
| `while` | 조건이 참일 때 계속 반복하는 문장 |
| `return` | 함수 실행을 종료하고 결과를 돌려주는 키워드 |
| `#include` | 외부 파일이나 기능을 가져오는 명령 |

---
# raylib에서 한글 사용하기

## ✅ 1. 한글이 잘 보이게 소스코드 작성

아래 코드를 그대로 복사해 사용하세요:

```c
#include "raylib.h"

int main() {
    InitWindow(800, 450, "한글 출력");

    // ✅ 한글 폰트 로드 (맑은 고딕, 30pt, 전체 글리프)
    Font font = LoadFontEx("C:\\Windows\\Fonts\\malgun.ttf", 30, NULL, 65535);

    // ✅ UTF-8 문자열로 한글 입력
    const char* text = u8"안녕하세요";

    SetTargetFPS(60);
    while (!WindowShouldClose()) {
        BeginDrawing();
        ClearBackground(RAYWHITE);
        DrawTextEx(font, text, (Vector2){250, 200}, 30, 2, BLACK);
        EndDrawing();
    }

    UnloadFont(font);
    CloseWindow();
    return 0;
}
```

---

## ✅ 2. 소스코드 저장 방법 (UTF-8로 저장해야 한글이 안 깨짐!)

1. `파일 > 다른 이름으로 저장`
2. 저장 버튼 오른쪽의 **▼ (역삼각형)** 클릭
3. `인코딩으로 저장` 선택
4. 아래 항목으로 저장:
   - **인코딩**: `유니코드(서명 있는 UTF-8)` 또는 `UTF-8 with BOM`
   - **줄 끝**: `Windows (CR LF)`

---

## ✅ 3. 프로젝트 설정 (추가로 하면 더 안전)

1. `프로젝트 > 속성 > C/C++ > 명령줄`
2. `추가 옵션`에 아래 추가:

```
/utf-8
```

---

## ✅ 5. 결과

화면 중앙에 **“안녕하세요”** 라는 텍스트가 정확히 출력됩니다!

---

## 🎯 참고

- 폰트 파일은 `C:\Windows\Fonts\malgun.ttf` 외에도 `batang.ttc`, `gulim.ttc` 등 사용 가능
- 반드시 `DrawTextEx()` 함수 사용
- `DrawText()`는 ASCII 전용이라 한글 지원 불가

---


🎯 계속 참고하면서, 헷갈릴 때마다 찾아보세요!  
이 부록은 여러분의 **프로그래밍 길잡이**가 되어줄 거예요. 🧭

