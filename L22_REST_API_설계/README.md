# 📌 22강: REST API 설계 — 데이터를 주고받는 규칙

> **핵심 포인트**: CRUD 패턴(Create/Read/Update/Delete)과 HTTP 메서드(GET/POST/PUT/DELETE) 매핑

---

## 📖 이론 (20분)

### REST API란?
**RE**presentational **S**tate **T**ransfer — 리소스(데이터)를 URL로 표현하고, HTTP 메서드로 행위를 정의하는 규칙입니다.

### CRUD와 HTTP 메서드 매핑

| CRUD | HTTP | URL 예시 | 설명 |
|------|------|----------|------|
| **C**reate | POST | `/memos` | 새 메모 생성 |
| **R**ead | GET | `/memos` 또는 `/memos/1` | 전체/단건 조회 |
| **U**pdate | PUT | `/memos/1` | 메모 수정 |
| **D**elete | DELETE | `/memos/1` | 메모 삭제 |

### HTTP 상태 코드

| 코드 | 의미 | 언제 사용 |
|------|------|----------|
| 200 | OK | 성공 |
| 201 | Created | 생성 성공 |
| 400 | Bad Request | 잘못된 요청 |
| 404 | Not Found | 리소스 없음 |
| 500 | Server Error | 서버 오류 |

---

## 🔨 가이드 실습 (25분)

### 실습 1: 메모 CRUD API (15분)
```
메모장 REST API를 Express와 Flask 둘 다 만들어줘:
- POST /api/memos — 새 메모 생성 (제목, 내용)
- GET /api/memos — 전체 메모 목록
- GET /api/memos/:id — 특정 메모 조회
- PUT /api/memos/:id — 메모 수정
- DELETE /api/memos/:id — 메모 삭제
- 데이터는 일단 메모리(배열)에 저장
- 적절한 상태 코드 반환
```

### 실습 2: API 테스트 (5분)
```
방금 만든 API를 테스트하는 방법을 알려줘:
- 브라우저에서 직접 (GET만 가능)
- curl 명령어로
- REST Client 확장 도구로
```

### 실습 3: 에러 핸들링 (5분)
```
API에 에러 처리를 추가해줘:
- 존재하지 않는 ID 요청 → 404
- 제목이 비어있는 메모 → 400
- 서버 내부 오류 → 500
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 연락처 API, 🟡 게시판 API

---

## ✅ 체크리스트
- [ ] REST API의 CRUD 패턴을 이해했다
- [ ] HTTP 메서드(GET/POST/PUT/DELETE)를 적절히 사용할 수 있다
- [ ] 상태 코드의 의미를 안다
- [ ] 에러 핸들링이 포함된 API를 만들 수 있다

---

## 🔗 다음 강의: [23강: 데이터베이스](../L23_데이터베이스/README.md)
