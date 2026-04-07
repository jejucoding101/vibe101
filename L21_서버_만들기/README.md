# 📌 21강: 서버 만들기 — Express(JS) / Flask(Python) 입문

> **핵심 포인트**: 나만의 서버를 만들어 API 엔드포인트를 생성하고, 데이터를 주고받는 경험

---

## 📖 이론 (20분)

### 서버란?
"요청을 받아서 응답을 돌려주는 프로그램"입니다. 지금까지 우리는 **남이 만든 서버(API)**를 사용했습니다. 이제 **직접** 만듭니다.

### Express (JavaScript) vs Flask (Python)

| | Express | Flask |
|---|---------|-------|
| 언어 | JavaScript (Node.js) | Python |
| 설치 | `npm install express` | `pip install flask` |
| 실행 | `node server.js` | `python app.py` |
| 특징 | 미들웨어 체인 | 데코레이터 기반 |

### 최소 서버 코드

```javascript
// Express (server.js)
const express = require('express');
const app = express();
app.get('/hello', (req, res) => {
    res.json({ message: '안녕하세요!' });
});
app.listen(3000, () => console.log('서버 시작: http://localhost:3000'));
```

```python
# Flask (app.py)
from flask import Flask, jsonify
app = Flask(__name__)

@app.route('/hello')
def hello():
    return jsonify(message='안녕하세요!')

if __name__ == '__main__':
    app.run(port=3000, debug=True)
```

### 라우팅이란?
URL 경로별로 다른 동작을 정의하는 것:
- `/hello` → 인사 메시지 반환
- `/time` → 현재 시간 반환
- `/users` → 사용자 목록 반환

---

## 🔨 가이드 실습 (25분)

### 실습 1: 첫 서버 띄우기 (8분)
```
간단한 웹 서버를 Express와 Flask 두 가지로 만들어줘:
- GET /hello → {"message": "안녕!"}
- GET /time → {"time": "현재 시각"}
- GET /random → {"number": 랜덤 숫자}
브라우저에서 접속해볼 수 있게 해줘.
```

### 실습 2: 정적 파일 서빙 (7분)
```
서버가 HTML/CSS/JS 파일도 제공하게 해줘:
- public/ 폴더에 index.html 넣기
- http://localhost:3000 으로 접속하면 HTML 페이지 표시
```

### 실습 3: JSON API 만들기 (10분)
```
명언 목록 API를 만들어줘:
- GET /quotes → 전체 명언 목록 (10개)
- GET /quotes/random → 랜덤 명언 1개
- 브라우저에서 접속하여 JSON 데이터 확인
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 계산기 API, 🟡 단축 URL 서비스

---

## ✅ 체크리스트
- [ ] 서버의 개념(요청→응답)을 이해했다
- [ ] Express 또는 Flask로 서버를 실행할 수 있다
- [ ] 라우트를 추가하여 API 엔드포인트를 만들 수 있다
- [ ] 브라우저에서 localhost로 접속하여 테스트할 수 있다

---

## 🔗 다음 강의: [22강: REST API 설계](../L22_REST_API_설계/README.md)
