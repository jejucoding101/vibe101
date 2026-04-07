# 📌 27강: 백엔드 구축 — 데이터 모델과 API 완성

> **핵심 포인트**: 관계형 데이터 모델링(1:N, N:M), 전체 CRUD API 구현

---

## 📖 이론 (20분)

### 테이블 간 관계

| 관계 | 설명 | 예시 |
|------|------|------|
| **1:N** | 하나 → 여러 개 | 사용자 1명 → 메모 여러 개 |
| **N:M** | 여러 → 여러 | 글 여러 개 ↔ 태그 여러 개 |

### 외래키(Foreign Key)

```sql
CREATE TABLE habits (
    id INTEGER PRIMARY KEY,
    user_id INTEGER NOT NULL,       -- 어떤 사용자의 습관인지
    title TEXT NOT NULL,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```

### N:M 관계의 중간 테이블

```sql
-- 글-태그 다대다 관계
CREATE TABLE post_tags (
    post_id INTEGER,
    tag_id INTEGER,
    PRIMARY KEY (post_id, tag_id)
);
```

---

## 🔨 가이드 실습 (25분)

### Step 1: DB 테이블 구현 (10분)
```
26강에서 설계한 프로젝트의 DB를 실제로 만들어줘:
- 모든 CREATE TABLE 실행
- 테스트용 샘플 데이터 10~20건 삽입
- 관계가 올바르게 동작하는지 JOIN 쿼리로 확인
```

### Step 2: 전체 API 구현 (10분)
```
프로젝트의 모든 API 엔드포인트를 구현해줘:
- 각 리소스의 CRUD (기획서 기반)
- 인증 미들웨어 적용 (25강 참고)
- 에러 핸들링
- Express 또는 Flask (원하는 언어 선택)
```

### Step 3: API 테스트 (5분)
```
모든 API를 테스트할 수 있는 요청 목록을 만들어줘.
curl 명령어 또는 REST Client 형태로.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

---

## ✅ 체크리스트
- [ ] 테이블 간 관계(1:N, N:M)를 구현할 수 있다
- [ ] JOIN 쿼리의 개념을 이해했다
- [ ] 프로젝트의 전체 CRUD API가 동작한다
- [ ] API 테스트를 통해 모든 엔드포인트를 검증했다

---

## 🔗 다음 강의: [28강: 프론트엔드 구축](../L28_프론트엔드_구축/README.md)
