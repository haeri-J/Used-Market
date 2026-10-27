# 🐢 부기마켓 (Boogimarket)

상품을 올리고, 둘러보고, 판매자와 **1:1 채팅**으로 거래하는 중고거래 Android 앱입니다.

<div align="center">
  <img src="https://img.shields.io/badge/Android-3DDC84?style=flat&logo=Android&logoColor=white" />
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat&logo=Kotlin&logoColor=white" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=Firebase&logoColor=black" />
</div>

> 한성대학교 팀 프로젝트 · 3명 (2023.10 ~ 2023.12)

## ✨ 주요 기능

### 회원
- 이메일 회원가입과 로그인 (Firebase Authentication)
- 빈 칸이 있으면 가입·로그인이 안 되도록 입력 검증

### 상품
- 상품 등록: 사진, 제목, 가격, 설명 (사진은 Firebase Storage에 저장)
- 상품 목록: **최신순 정렬**, **판매 중인 상품만 보기** 필터
- 상품 상세 화면, 판매자가 누르는 **거래 완료** 버튼
- 내가 쓴 글 모아보기, 수정(기존 내용이 채워진 상태로 시작), 삭제

### 채팅
- 상품 상세에서 판매자에게 바로 **1:1 채팅** 시작
- Firestore로 메시지를 저장하고 실시간으로 받기
- 대화하는 두 사람에게만 보이는 채팅방, 내 메시지와 상대 메시지를 구분한 말풍선 UI
- 빈 메시지는 전송 불가
- 게시글을 지우면 연결된 **채팅방과 채팅 기록도 함께 삭제**

## 🛠 Tech Stack

| 분류 | 기술 |
|---|---|
| Language | Kotlin |
| Platform | Android (minSdk 26, targetSdk 34) |
| UI | XML 레이아웃, ViewBinding, Fragment + Bottom Navigation |
| Backend (BaaS) | Firebase Authentication, Cloud Firestore, Firebase Storage |

## 🗂 데이터 구조 (Firestore)

| 컬렉션 | 내용 |
|---|---|
| `users` | 회원 정보 |
| `post` | 상품 게시글 (제목, 가격, 설명, 이미지, 판매 여부, 작성 시간) |
| `chats` / `messages` | 채팅방과 그 안의 메시지 |
| `chatlog` / `log` | 채팅 목록 표시용 기록 |

## 📱 화면 구성

| 화면 | 파일 |
|---|---|
| 로그인 · 회원가입 | `LoginActivity`, `RegisterActivity` |
| 홈 (상품 목록) | `HomeFragment` |
| 상품 등록 | `WriteDialog` |
| 상품 상세 · 수정 | `DetailsActivity`, `ModifyActivity` |
| 채팅 목록 · 채팅방 | `ChatFragment`, `ChatActivity` |
| 마이페이지 · 내가 쓴 글 | `MyPageFragment`, `MySellActivity` |

## ▶️ 실행 방법

1. Android Studio에서 `Boogimarket` 폴더를 엽니다.
2. Firebase 콘솔에서 Android 앱을 등록하고, 받은 `google-services.json`을 `Boogimarket/app/`에 넣습니다.
   (보안을 위해 레포에는 포함되어 있지 않습니다.)
3. Firebase 콘솔에서 Authentication(이메일), Firestore, Storage를 활성화합니다.
4. 에뮬레이터나 기기에서 ▶︎ Run 합니다.
