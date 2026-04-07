# 📌 28강: 프론트엔드 구축 — 세련된 UI 완성

> **핵심 포인트**: SPA(Single Page Application) 개념과 클라이언트 사이드 라우팅

---

## 📖 이론 (20분)

### SPA란?
하나의 HTML 페이지에서 JavaScript가 **화면을 동적으로 교체**하는 방식. 페이지 전환 시 서버에 새 HTML을 요청하지 않음.

### 클라이언트 라우팅

```javascript
// 간단한 라우터
function navigate(path) {
    window.history.pushState(null, '', path);
    const content = document.querySelector('#app');
    
    switch(path) {
        case '/':      content.innerHTML = renderHome(); break;
        case '/list':  content.innerHTML = renderList(); break;
        case '/add':   content.innerHTML = renderForm(); break;
    }
}
```

### 컴포넌트 패턴
Each 페이지/위젯을 독립적인 함수/모듈로 구성:

```
js/
├── router.js          ← 라우팅 관리
├── pages/
│   ├── home.js        ← 홈 페이지
│   ├── list.js        ← 목록 페이지
│   └── detail.js      ← 상세 페이지
└── components/
    ├── header.js       ← 공통 헤더
    └── card.js         ← 재사용 카드
```

---

## 🔨 가이드 실습 (25분)

### Step 1: 전체 UI 페이지 구현 (15분)
```
26강 프로젝트의 프론트엔드를 만들어줘:
- 홈/목록/추가/상세/수정 페이지
- 간이 라우터로 페이지 전환 (새로고침 없이)
- 27강 API와 연동 (fetch)
- 반응형 + 다크모드 + 마이크로 애니메이션
- 세련된 UI (글래스모피즘 또는 미니멀)
```

### Step 2: 폴리싱 (5분)
```
더 세련되게 꾸며줘:
- 로딩 스켈레톤 (데이터 로드 전 placeholder)
- 빈 상태 안내 (데이터가 없을 때)
- 성공/에러 토스트 알림
- 페이지 전환 애니메이션
```

### Step 3: 로그인 연동 (5분)
```
25강의 인증 기능을 UI에 연동:
- 미로그인 시 로그인 페이지로 이동
- 로그인 후 메인 대시보드로 이동
- 네비게이션에 사용자 이름/로그아웃 표시
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

---

## ✅ 체크리스트
- [ ] SPA의 개념을 이해했다
- [ ] 클라이언트 라우팅으로 페이지 전환을 구현할 수 있다
- [ ] 27강 백엔드 API와 프론트엔드가 연동된다
- [ ] 반응형+다크모드+애니메이션이 적용된 완성형 UI

---

## 🔗 다음 강의: [29강: Git & 버전 관리](../L29_Git_버전_관리/README.md)
