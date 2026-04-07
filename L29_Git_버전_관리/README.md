# 📌 29강: Git & 버전 관리 — 코드의 타임머신

> **핵심 포인트**: Git 기본 흐름(init → add → commit → push)과 GitHub 사용법

---

## 📖 이론 (20분)

### 왜 Git이 필요한가?
- ✅ 코드 변경 이력 추적 ("어제 뭘 바꿨더라?")
- ✅ 실수를 되돌리기 ("이전 상태로 복원")
- ✅ 코드를 안전하게 백업 (GitHub)
- ✅ 다른 사람과 협업

### Git 핵심 개념

```
작업 폴더  →  스테이징  →  로컬 저장소  →  원격 저장소(GitHub)
(Working)     (Staging)    (Local Repo)    (Remote Repo)
     git add      git commit       git push
```

### 핵심 명령어 5개

| 명령어 | 의미 |
|--------|------|
| `git init` | 현재 폴더를 Git 저장소로 초기화 |
| `git add .` | 변경 파일을 스테이징에 올리기 |
| `git commit -m "메시지"` | 변경사항을 저장소에 기록 |
| `git push` | 원격 저장소(GitHub)에 업로드 |
| `git log --oneline` | 커밋 이력 확인 |

### .gitignore
Git이 추적하지 않을 파일 목록:

```
node_modules/
__pycache__/
.env
*.db
```

---

## 🔨 가이드 실습 (25분)

### 실습 1: 프로젝트에 Git 적용 (10분)
```
26~28강에서 만든 프로젝트에 Git을 적용해줘:
1. git init
2. .gitignore 생성 (node_modules, .env, *.db 등)
3. 첫 커밋: "Initial commit: 프로젝트 초기 설정"
4. git log로 이력 확인
```

### 실습 2: GitHub에 올리기 (10분)
```
이 프로젝트를 GitHub에 올리는 방법을 알려줘:
1. GitHub에서 새 리포지토리 생성
2. git remote add origin [URL]
3. git push
4. 멋진 README.md 작성
```

### 실습 3: 기능 추가 + 커밋 (5분)
```
프로젝트에 작은 기능 하나를 추가하고:
- 변경 사항 확인 (git diff)
- 커밋하고 (git commit -m "feat: [기능명]")
- GitHub에 푸시
```

---

## 🎯 자율 실습 — [TOPIC_POOL.md](TOPIC_POOL.md)

**추천**: 🟢 README 작성, 🟡 브랜치 실험

---

## ✅ 체크리스트
- [ ] Git의 필요성을 이해했다
- [ ] init → add → commit → push 흐름을 실행할 수 있다
- [ ] GitHub에 코드를 올릴 수 있다
- [ ] .gitignore의 역할을 안다

---

## 🔗 다음 강의: [30강: 졸업 — 자동화 파이프라인](../L30_졸업_자동화_파이프라인/README.md)
