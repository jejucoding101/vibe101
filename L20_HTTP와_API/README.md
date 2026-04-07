# 📌 20강: HTTP와 API — 인터넷에서 데이터 가져오기

> **핵심 포인트**: HTTP 요청/응답 구조와 `fetch` API로 외부 데이터를 가져와 활용하기

---

## 📖 이론 (20분)

### 클라이언트-서버 모델

```
[브라우저/프로그램]  →  요청(Request)  →  [서버]
   (클라이언트)      ←  응답(Response)  ←  (서버)
```

### HTTP 요청의 구성요소

| 요소 | 설명 | 예시 |
|------|------|------|
| **URL** | 주소 | `https://api.example.com/weather` |
| **Method** | 행위 | GET(조회), POST(생성), PUT(수정), DELETE(삭제) |
| **Headers** | 부가 정보 | Content-Type, Authorization |
| **Body** | 전송 데이터 | `{"name": "홍길동"}` (POST 시) |

### fetch 사용법

```javascript
// JavaScript
const response = await fetch('https://api.example.com/data');
const data = await response.json();
console.log(data);
```

```python
# Python
import requests
response = requests.get('https://api.example.com/data')
data = response.json()
print(data)
```

### async/await란?

API 호출은 시간이 걸리는 작업입니다. `await`는 "응답 올 때까지 기다려"라는 의미:

```javascript
// ❌ 이렇게 하면 데이터가 아직 안 왔는데 사용하려 함
const data = fetch(url); // Promise 객체가 옴

// ✅ 이렇게 해야 응답을 기다림
const data = await fetch(url).then(r => r.json());
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: 공개 API 호출 (10분)
```
다음 무료 API를 호출하여 데이터를 가져와 보여줘:
1. 랜덤 고양이 사진 API (https://api.thecatapi.com/v1/images/search)
2. 랜덤 joke API (https://official-joke-api.appspot.com/random_joke)
JS(브라우저 fetch)와 Python(requests) 둘 다.
```

### 실습 2: 날씨 정보 대시보드 (10분)
```
무료 날씨 API를 활용하여:
- 도시 이름 입력 → 현재 기온, 날씨 상태, 습도 표시
- 예쁜 카드 UI로 표시
- 날씨에 따라 아이콘(☀️🌧️⛅) 표시
```

### 실습 3: 브라우저 네트워크 탭 (5분)
```
브라우저 개발자 도구(F12)의 Network 탭에서
API 요청/응답을 확인하는 방법을 알려줘.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 포켓몬 API 탐험, 🟡 번역 API 활용

---

## ✅ 체크리스트
- [ ] HTTP 요청/응답의 기본 구조를 이해했다
- [ ] fetch(JS) 또는 requests(Python)로 API를 호출할 수 있다
- [ ] JSON 응답을 파싱하여 원하는 데이터를 추출할 수 있다
- [ ] async/await의 개념을 이해했다

---

## 🔗 다음 강의: [21강: 서버 만들기](../L21_서버_만들기/README.md)
