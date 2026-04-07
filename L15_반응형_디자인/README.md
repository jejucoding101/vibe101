# 📌 15강: 반응형 디자인 — 모바일에서도 예쁘게

> **핵심 포인트**: 미디어 쿼리(Media Query), CSS Grid, 모바일 퍼스트 디자인

---

## 📖 이론 (20분)

### 반응형 디자인이란?

**하나의 웹 페이지**가 PC, 태블릿, 스마트폰 등 다양한 화면 크기에 맞춰 자동으로 레이아웃을 변경하는 기법입니다.

### 미디어 쿼리

```css
/* 기본: 모바일 스타일 (모바일 퍼스트) */
.grid { display: flex; flex-direction: column; }

/* 768px 이상: 태블릿 */
@media (min-width: 768px) {
    .grid { flex-direction: row; flex-wrap: wrap; }
    .card { width: 50%; }
}

/* 1024px 이상: PC */
@media (min-width: 1024px) {
    .card { width: 33.33%; }
}
```

### CSS Grid: 2차원 레이아웃

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}
```

> `auto-fit` + `minmax` 조합 하나로 반응형 그리드 완성!

### 뷰포트 메타 태그 (필수!)

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: 반응형 카드 그리드 (10분)
```
6개의 카드를 반응형 그리드로 배치해줘:
- PC: 3열, 태블릿: 2열, 모바일: 1열
- CSS Grid 사용
- 각 카드에 이미지, 제목, 설명 포함
```

### 실습 2: 네비게이션 + 햄버거 메뉴 (10분)
```
반응형 네비게이션 바를 만들어줘:
- PC: 로고 왼쪽, 메뉴 항목 가로 배치
- 모바일: 햄버거 아이콘 클릭 시 메뉴 펼치기
- CSS + 약간의 JS 사용
```

### 실습 3: 브라우저 개발자 도구 체험 (5분)
```
브라우저 개발자 도구(F12)를 여는 방법과
디바이스 모드(모바일 시뮬레이션)를 사용하는 방법을 알려줘.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 포트폴리오 레이아웃, 🟡 대시보드 그리드

---

## ✅ 체크리스트

- [ ] 미디어 쿼리의 역할을 이해했다
- [ ] CSS Grid 기본 사용법을 안다
- [ ] 브라우저 개발자 도구로 반응형 테스트할 수 있다
- [ ] 모바일/태블릿/PC에서 다르게 보이는 페이지를 만들 수 있다

---

## 🔗 다음 강의: [16강: JavaScript DOM](../L16_JavaScript_DOM/README.md)
