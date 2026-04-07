# 📌 8강: 파일 자동 정리 — 컴퓨터 정리를 자동화하자

> **핵심 포인트**: `fs`(Node.js) / `os`, `shutil`(Python) 모듈로 파일시스템을 프로그래밍으로 조작하기

---

## 📖 이론 (20분)

### 파일시스템 API란?

프로그래밍으로 파일과 폴더를 **생성, 복사, 이동, 삭제, 이름 변경**할 수 있는 기능 모음입니다.

| 작업 | JavaScript (fs) | Python (os/shutil) |
|------|-----------------|-------------------|
| 파일 목록 | `fs.readdirSync()` | `os.listdir()` |
| 파일 복사 | `fs.copyFileSync()` | `shutil.copy2()` |
| 파일 이동 | `fs.renameSync()` | `shutil.move()` |
| 폴더 생성 | `fs.mkdirSync()` | `os.makedirs()` |
| 파일 삭제 | `fs.unlinkSync()` | `os.remove()` |
| 파일 정보 | `fs.statSync()` | `os.stat()` |

### 경로 다루기

```javascript
// JavaScript — path 모듈
const path = require('path');
path.join('folder', 'subfolder', 'file.txt')  // 안전한 경로 결합
path.extname('report.pdf')  // '.pdf' — 확장자 추출
path.basename('/a/b/file.txt')  // 'file.txt' — 파일명만
```

```python
# Python — pathlib (현대적 방식)
from pathlib import Path
p = Path('folder') / 'subfolder' / 'file.txt'
p.suffix   # '.txt'
p.stem     # 'file'
p.name     # 'file.txt'
```

> 💡 파일 정리 작업은 **Python이 특히 편합니다** — `pathlib`이 직관적이에요.

---

## 🔨 가이드 실습 (25분)

### 실습 1: 다운로드 폴더 분류기 (12분)

```
[역할] 파일 관리 자동화 전문가
[목표] 특정 폴더의 파일들을 확장자별로 하위 폴더로 자동 분류하는 프로그램
[규칙]
- 이미지(.jpg, .png, .gif) → images/ 폴더
- 문서(.pdf, .docx, .txt) → documents/ 폴더
- 코드(.js, .py, .html) → code/ 폴더
- 기타 → others/ 폴더
- 분류하기 전에 어떤 파일이 어디로 이동하는지 미리 보여줘 (dry-run)
- JS와 Python 둘 다
```

### 실습 2: 파일명 일괄 변경기 (8분)

```
폴더 안의 파일 이름을 규칙에 따라 일괄 변경하는 도구:
- 공백을 언더스코어(_)로
- 대문자를 소문자로
- 파일명 앞에 오늘 날짜(YYYYMMDD_) 접두사 추가
- 변경 전/후를 미리 보여주는 프리뷰 기능
```

### 실습 3: 오래된 파일 관리 (5분)

```
30일 이상 수정되지 않은 파일을 찾아서 old_files/ 폴더로 이동하는 프로그램.
이동 전에 목록을 보여주고 확인을 받아줘.
```

---

## 🎯 자율 실습 (25분)

[TOPIC_POOL.md](TOPIC_POOL.md)에서 주제를 골라 도전!

**이번 강의 추천 주제**: 🟢 사진 날짜별 정리, 🟡 중복파일 찾기+삭제

---

## ✅ 이번 강의 체크리스트

- [ ] 파일시스템 API(fs/os)로 파일을 프로그래밍으로 다룰 수 있다
- [ ] 경로를 안전하게 조합하는 방법을 안다
- [ ] 파일 분류/이동/이름 변경을 자동화할 수 있다
- [ ] "미리보기(dry-run)" 기능의 중요성을 이해했다

---

## 🔗 다음 강의

[9강: 반복과 조건](../L09_반복과_조건/README.md) — 프로그래밍의 핵심 제어 구조
