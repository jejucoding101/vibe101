# 📌 16강: JavaScript DOM — 웹에 생명 불어넣기

> **핵심 포인트**: DOM(Document Object Model) 개념, `querySelector`, 이벤트 처리를 통해 웹 페이지에 동적 기능 추가하기

---

## 📖 이론 (20분)

### DOM이란?

브라우저가 HTML을 읽으면 **트리 구조의 객체**로 변환합니다. 이것이 DOM입니다. JavaScript로 이 트리를 조작하면 **페이지 내용을 실시간으로 변경**할 수 있습니다.

### 핵심 3가지 동작

```javascript
// 1. 요소 찾기 (Select)
const btn = document.querySelector('#myButton');

// 2. 이벤트 듣기 (Listen)
btn.addEventListener('click', function() {
    // 3. 내용 변경 (Modify)
    document.querySelector('#result').textContent = '클릭됨!';
});
```

### 자주 쓰는 DOM 메서드

| 메서드 | 하는 일 |
|--------|---------|
| `querySelector('#id')` | ID로 요소 찾기 |
| `querySelectorAll('.class')` | 클래스로 여러 요소 찾기 |
| `.textContent = '...'` | 텍스트 변경 |
| `.innerHTML = '<b>...</b>'` | HTML 변경 |
| `.style.color = 'red'` | 스타일 변경 |
| `.classList.add('active')` | 클래스 추가 |
| `.createElement('div')` | 새 요소 생성 |
| `.appendChild(el)` | 자식으로 추가 |

### 주요 이벤트

| 이벤트 | 언제 발생 |
|--------|----------|
| `click` | 클릭 |
| `input` | 입력 중 |
| `submit` | 폼 제출 |
| `keydown` | 키 누름 |
| `mouseover` | 마우스 올림 |

---

## 🔨 가이드 실습 (25분)

### 실습 1: 카운터 만들기 (8분)
```
+1, -1, 초기화 버튼이 있는 카운터를 만들어줘:
- 가운데 큰 숫자 표시
- +1 클릭 시 증가, -1 클릭 시 감소
- 음수가 되면 빨간색으로 표시
- 세련된 CSS 적용
```

### 실습 2: 투두 리스트 (12분)
```
간단한 할일 목록 앱을 만들어줘:
- 입력 필드 + 추가 버튼
- 할일 클릭 시 취소선 (완료 표시)
- 삭제 버튼 (X)
- 남은 할일 개수 표시
- 예쁜 CSS 적용
```

### 실습 3: 다크모드 토글 (5분)
```
버튼 하나로 밝은 테마 ↔ 어두운 테마를 전환하는 기능.
🌙와 ☀️ 아이콘 토글.
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 계산기 UI, 🟡 비밀번호 생성기 UI

---

## ✅ 체크리스트

- [ ] DOM이 무엇인지 이해했다
- [ ] querySelector로 HTML 요소를 찾을 수 있다
- [ ] addEventListener로 클릭/입력 이벤트를 처리할 수 있다
- [ ] JavaScript로 페이지 내용을 동적으로 변경할 수 있다

---

## 🔗 다음 강의: [17강: 로컬 스토리지](../L17_로컬_스토리지/README.md)
