# 📌 23강: 데이터베이스 — 데이터를 영구 저장하기

> **핵심 포인트**: SQLite 데이터베이스와 SQL 기초(SELECT, INSERT, UPDATE, DELETE)

---

## 📖 이론 (20분)

### 왜 데이터베이스가 필요한가?
- JSON 파일: 작은 데이터 OK, 동시 접근 어려움, 검색 느림
- 데이터베이스: 구조적 저장, 빠른 검색, 동시 접근, 관계 표현

### SQLite란?
파일 하나에 전체 DB가 들어있는 **설치 불필요 DB**. 입문에 최적!

### SQL 핵심 4개 명령

```sql
-- 생성 (Create)
INSERT INTO memos (title, content) VALUES ('제목', '내용');

-- 조회 (Read)
SELECT * FROM memos;                          -- 전체
SELECT * FROM memos WHERE id = 1;             -- 조건
SELECT * FROM memos ORDER BY created_at DESC; -- 정렬

-- 수정 (Update)
UPDATE memos SET title='새 제목' WHERE id = 1;

-- 삭제 (Delete)
DELETE FROM memos WHERE id = 1;
```

### 테이블 생성

```sql
CREATE TABLE IF NOT EXISTS memos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content TEXT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: SQLite 데이터베이스 만들기 (10분)
```
메모 앱을 위한 SQLite 데이터베이스를 만들어줘:
- memos 테이블: id, title, content, created_at
- 샘플 데이터 5개 입력
- 전체 조회, 조건 조회, 수정, 삭제 테스트
JS(better-sqlite3)와 Python(sqlite3) 둘 다
```

### 실습 2: 22강 API에 DB 연결 (10분)
```
22강의 메모 REST API를 수정해서:
- 메모리 배열 대신 SQLite에 데이터 저장
- 서버를 재시작해도 데이터가 유지되게
```

### 실습 3: DB 직접 확인 (5분)
```
DB Browser for SQLite 설치 방법과 사용법을 알려줘.
또는 콘솔에서 직접 SQL 쿼리를 실행하는 방법.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 회원 관리 DB, 🟡 게시물+댓글 관계

---

## ✅ 체크리스트
- [ ] 데이터베이스가 필요한 이유를 이해했다
- [ ] SQL CRUD 4가지 명령을 이해했다
- [ ] SQLite로 테이블을 만들고 데이터를 조작할 수 있다
- [ ] API 서버에 DB를 연결할 수 있다

---

## 🔗 다음 강의: [24강: 풀스택 연동](../L24_풀스택_연동/README.md)
