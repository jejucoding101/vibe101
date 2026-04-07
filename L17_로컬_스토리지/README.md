# 📌 17강: 로컬 스토리지 — 브라우저에 데이터 기억시키기

> **핵심 포인트**: `localStorage`로 브라우저에 데이터를 영구 저장하여 새로고침해도 유지되게 하기

---

## 📖 이론 (20분)

### 문제: 새로고침하면 다 사라진다!

16강 투두 리스트의 문제점 — 새로고침하면 할일이 전부 사라집니다. 해결책: **localStorage**

### localStorage 핵심 API

```javascript
// 저장
localStorage.setItem('name', '홍길동');

// 읽기
const name = localStorage.getItem('name');

// 삭제
localStorage.removeItem('name');

// 전체 삭제
localStorage.clear();

// 객체/배열 저장 (JSON 변환 필요!)
localStorage.setItem('todos', JSON.stringify(todoList));
const todos = JSON.parse(localStorage.getItem('todos'));
```

### localStorage vs sessionStorage vs Cookie

| | localStorage | sessionStorage | Cookie |
|---|-------------|----------------|--------|
| 만료 | 영구 (직접 삭제까지) | 탭 닫으면 삭제 | 만료일 설정 |
| 용량 | ~5MB | ~5MB | ~4KB |
| 용도 | 설정, 데이터 보관 | 임시 데이터 | 인증, 추적 |

---

## 🔨 가이드 실습 (25분)

### 실습 1: 투두 리스트 업그레이드 (10분)
```
16강 투두 리스트에 localStorage 저장 기능을 추가해줘:
- 할일 추가/삭제/완료 시 자동 저장
- 페이지 새로고침해도 데이터 유지
- 로컬 스토리지 사용량 표시
```

### 실습 2: 메모장 앱 (10분)
```
여러 개의 메모를 관리하는 메모장 앱:
- 메모 작성 + 제목 입력
- 메모 목록 (사이드바)
- 메모 클릭 → 내용 편집
- 메모 삭제
- 모두 localStorage에 저장
```

### 실습 3: 테마 설정 저장 (5분)
```
사용자의 다크모드/라이트모드 선택을 localStorage에 저장하여
다음에 다시 방문해도 마지막 선택한 테마가 적용되게 해줘.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 장바구니 유지, 🟡 학습 진도 추적

---

## ✅ 체크리스트

- [ ] localStorage의 기본 API(setItem, getItem)를 이해했다
- [ ] JSON.stringify/parse로 객체를 저장/불러올 수 있다
- [ ] 새로고침해도 데이터가 유지되는 앱을 만들 수 있다

---

## 🔗 다음 강의: [18강: 애니메이션](../L18_애니메이션/README.md)
