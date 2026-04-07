# 📌 25강: 사용자 인증 — 로그인/회원가입

> **핵심 포인트**: 세션/JWT 토큰 기반 인증, 비밀번호 해싱(bcrypt), 보호된 API 라우트

---

## 📖 이론 (20분)

### 인증(Authentication) vs 인가(Authorization)
- **인증**: "당신이 누구인가?" → 로그인
- **인가**: "당신이 이 작업을 할 수 있는가?" → 권한 확인

### 비밀번호 보안
- ❌ 절대 평문 저장 금지!
- ✅ **해싱**: 일방향 변환 (복원 불가)

```javascript
const bcrypt = require('bcrypt');
const hash = await bcrypt.hash('myPassword', 10);  // 해싱
const match = await bcrypt.compare('myPassword', hash);  // 검증
```

### JWT (JSON Web Token)
로그인 성공 시 서버가 발급하는 "입장권":

```
[헤더].[페이로드].[서명]
eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxfQ.abc123...
```

- 클라이언트가 매 요청 시 토큰을 함께 전송
- 서버는 토큰을 검증하여 사용자 확인
- 상태 유지 없음(Stateless) → 확장에 유리

---

## 🔨 가이드 실습 (25분)

### 실습 1: 회원가입 + 로그인 API (12분)
```
사용자 인증 API를 만들어줘:
- POST /api/register — 이메일, 비밀번호로 회원가입 (bcrypt 해싱)
- POST /api/login — 이메일, 비밀번호 검증 → JWT 발급
- GET /api/profile — 토큰으로 사용자 정보 조회 (보호 라우트)
Express(JS)와 Flask(Python) 둘 다.
```

### 실습 2: 로그인 UI (8분)
```
회원가입/로그인 폼 UI를 만들어줘:
- 세련된 카드 형태 폼
- 로그인 성공 → 토큰을 localStorage에 저장
- 로그인 상태에서 프로필 표시
- 로그아웃 버튼 (토큰 삭제)
```

### 실습 3: 메모 앱에 인증 적용 (5분)
```
24강 풀스택 메모 앱에 인증을 추가해줘:
- 로그인한 사용자만 메모 CRUD 가능
- 각 메모에 작성자 정보 포함
- 자기 메모만 수정/삭제 가능
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 프로필 관리, 🟡 권한별 접근 제어

---

## ✅ 체크리스트
- [ ] 인증과 인가의 차이를 안다
- [ ] 비밀번호를 해싱하여 안전하게 저장할 수 있다
- [ ] JWT 토큰 발급/검증 흐름을 이해했다
- [ ] 보호 라우트(로그인 필요)를 구현할 수 있다

---

## 🔗 다음 강의: [26강: 프로젝트 기획](../L26_프로젝트_기획/README.md) — Part 5: 최종 프로젝트!
