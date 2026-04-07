# 📌 18강: 애니메이션 — 움직이는 UI

> **핵심 포인트**: CSS transition/animation, keyframe, Intersection Observer로 동적인 웹 UI 만들기

---

## 📖 이론 (20분)

### CSS Transition vs Animation

| | Transition | Animation |
|---|-----------|-----------|
| 트리거 | 상태 변화 (hover 등) | 자동 실행 가능 |
| 복잡도 | 단순 (A → B) | 복잡 (여러 단계) |
| 사용법 | `transition: all 0.3s` | `@keyframes` 정의 |

### Transition

```css
.button {
    background: #3498db;
    transition: all 0.3s ease;  /* 0.3초에 걸쳐 부드럽게 */
}
.button:hover {
    background: #2ecc71;
    transform: scale(1.05);    /* 5% 확대 */
}
```

### Animation + Keyframes

```css
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
}
.card { animation: fadeIn 0.5s ease forwards; }
```

### Intersection Observer (스크롤 트리거)

스크롤하여 요소가 화면에 보일 때 애니메이션 실행:

```javascript
const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('visible');
        }
    });
});
document.querySelectorAll('.animate-on-scroll').forEach(el => observer.observe(el));
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: 마이크로 인터랙션 (10분)
```
버튼, 카드, 입력 필드에 미세한 애니메이션을 추가해줘:
- 버튼: 호버 시 약간 커지고 그림자 증가, 클릭 시 눌리는 효과
- 카드: 마우스 올리면 위로 살짝 떠오름
- 입력 필드: 포커스 시 테두리 색상 변경 + 살짝 확대
```

### 실습 2: 스크롤 트리거 애니메이션 (10분)
```
긴 페이지에서 스크롤 시 섹션별로 나타나는 효과:
- 왼쪽에서 슬라이드인
- 아래에서 페이드인
- 순차적 딜레이 (stagger)
Intersection Observer 사용
```

### 실습 3: 로딩 스피너 + 토스트 알림 (5분)
```
1. CSS만으로 로딩 스피너 애니메이션
2. 버튼 클릭 시 아래에서 올라오는 토스트 알림 (3초 후 사라짐)
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 타이핑 이펙트, 🟡 파티클 효과

---

## ✅ 체크리스트

- [ ] CSS transition과 animation의 차이를 안다
- [ ] @keyframes로 커스텀 애니메이션을 만들 수 있다
- [ ] Intersection Observer로 스크롤 트리거 구현 가능
- [ ] 마이크로 인터랙션의 가치를 이해했다

---

## 🔗 다음 강의: [19강: 종합 대시보드](../L19_종합_대시보드/README.md)
