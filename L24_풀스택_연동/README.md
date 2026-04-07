# 📌 24강: 풀스택 연동 — 프론트 ↔ 백 ↔ DB 연결

> **핵심 포인트**: 프론트엔드(HTML/CSS/JS)에서 fetch로 백엔드 API를 호출하고, 백엔드가 SQLite에서 데이터를 가져오는 **풀스택 흐름** 완성

---

## 📖 이론 (20분)

### 풀스택 데이터 흐름

```
[사용자] → 버튼 클릭 → [프론트엔드 JS]
                           ↓ fetch('/api/memos')
                       [백엔드 서버]
                           ↓ SQL 쿼리
                       [SQLite DB]
                           ↑ 결과
                       [백엔드 서버]
                           ↑ JSON 응답
                       [프론트엔드 JS]
                           ↑ DOM 업데이트 → 화면에 표시
```

### CORS란?
브라우저가 다른 주소의 서버에 요청할 때 발생하는 보안 정책. 서버에서 허용 설정 필요:

```javascript
// Express
const cors = require('cors');
app.use(cors());
```

```python
# Flask
from flask_cors import CORS
CORS(app)
```

### async/await 패턴

```javascript
async function loadMemos() {
    try {
        const res = await fetch('/api/memos');
        const memos = await res.json();
        renderMemos(memos);     // DOM에 그려주기
    } catch (error) {
        showError('서버 연결 실패');  // 에러 처리 UI
    }
}
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: 풀스택 메모 앱 결합 (15분)
```
지금까지 만든 것을 합치는 풀스택 메모 앱을 만들어줘:

[백엔드] — 23강의 Express/Flask + SQLite 메모 API
[프론트엔드] — 17강 스타일의 예쁜 메모 앱 UI

기능:
- 메모 작성 폼 → POST /api/memos
- 메모 목록 표시 → GET /api/memos
- 메모 삭제 버튼 → DELETE /api/memos/:id
- 로딩 스피너 표시
- 에러 시 토스트 알림
```

### 실습 2: 검색 기능 (5분)
```
메모 검색 기능을 추가해줘:
- 프론트: 검색 입력 필드
- 백엔드: GET /api/memos?search=키워드
- DB: LIKE 쿼리로 제목+내용 검색
```

### 실습 3: 새로고침해도 최신 (5분)
```
메모를 추가/삭제한 후 자동으로 목록이 갱신되게 해줘.
전체 페이지 새로고침 없이 해당 부분만 업데이트.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟡 투두 풀스택, 🟡 방명록

---

## ✅ 체크리스트
- [ ] 프론트→백→DB 데이터 흐름을 이해했다
- [ ] fetch로 백엔드 API를 호출할 수 있다
- [ ] 응답 데이터를 DOM에 표시할 수 있다
- [ ] 로딩/에러 상태를 UI에 표현할 수 있다

---

## 🔗 다음 강의: [25강: 사용자 인증](../L25_사용자_인증/README.md)
