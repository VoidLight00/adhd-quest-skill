# 🎮 ADHD Quest — OpenClaw RPG Skill

ADHD 관리를 **RPG 게이미피케이션**으로 만든 [OpenClaw](https://github.com/openclaw/openclaw) 텔레그램 비서 스킬입니다.  
모든 조작은 **텔레그램 인라인 버튼**으로 — 타이핑 최소화, 실행력 최대화.

<p align="center">
  <img src="https://img.shields.io/badge/OpenClaw-Skill-blueviolet?style=flat-square" alt="OpenClaw Skill" />
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Linux-lightgrey?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License" />
</p>

---

## 🧠 왜 만들었나

ADHD는 **"알면서도 못 하는"** 장애입니다.  
할 일을 아는 것과 실행하는 것 사이의 간극 — 이걸 **환경 구조화**와 **외부 보상 시스템**으로 메꿉니다.

> 💡 모든 기능은 [의학적 근거](references/adhd-research.md)에 기반합니다.  
> CBT, 실행기능 연구, ADDA 권장사항 등을 참고했습니다.

---

## ✨ 기능

| 기능 | 설명 |
|------|------|
| 💧 **물 마시기** | 정해진 시간에 수분 섭취 알림 |
| 💊 **약 복용 알림** | 미체크 시 30분 후 재알림 |
| 📝 **할 일 쪼개기** | "방 정리" → 마이크로태스크 자동 분해 (Task Chunking) |
| ⏰ **리마인더/외부화** | 머릿속 할 일을 외부로 꺼내기 |
| 😊 **감정 체크인** | 1~10 온도 + 이모지 → 감정일기 자동 저장 |
| 🧩 **두뇌 덤프** | 긴급/중요 자동 분류 |
| 🌅 **아침 루틴** | 선택한 퀘스트를 매일 아침 버튼으로 발송 |
| 🙏 **감사일기** | 하루 1줄, append 방식으로 축적 |
| 😴 **수면 관리** | 취침 알림 + 수면 기록 |
| 📊 **주간 리포트** | 완료율, 감정 변화, 잘한 점 자동 집계 |
| 🎮 **RPG 시스템** | XP, 레벨, 스트릭, 칭호 |
| 🆘 **위기 대응** | "힘들어" 감지 → 긍정확언 + 호흡가이드 |

---

## 📱 텔레그램 UI 예시

### 아침 퀘스트
```
🌅 좋은 아침! Lv.3 전사 현님
오늘의 퀘스트가 도착했어요 ⚔️

🔥 스트릭: 7일째! (+100 XP 보너스)

┌─────────────────────────┐
│ 💧 물 한 잔  │ 💊 약 복용  │
│─────────────────────────│
│ 📝 오늘 할 일 정리       │
│─────────────────────────│
│ 😴 오늘은 여기까지       │
└─────────────────────────┘
```

### 감정 체크인
```
😊 오늘 하루 어땠어요?
감정 온도를 골라주세요 🌡️

┌───────────────────────────┐
│ 😢 1~2  │ 😕 3~4  │ 😐 5~6 │
│───────────────────────────│
│ 😊 7~8  │ 😄 9~10          │
└───────────────────────────┘
```

### 퀘스트 완료
```
🎉 퀘스트 완료! +15 XP

━━━━━━━━━━━━━━━━ 73%
Lv.3 전사 → Lv.4 까지 27 XP 남음

오늘 완료: 4/6 퀘스트 ✨
```

---

## 📦 설치

### 요구사항

- [OpenClaw](https://github.com/openclaw/openclaw) 설치 및 실행 중
- 텔레그램 연동 완료

### 설치 방법

**방법 1: 링크 던지기 (가장 쉬움) 🔥**

OpenClaw 봇에게 이 메시지를 보내세요:

```
https://github.com/VoidLight00/adhd-quest-skill 이 스킬 설치해줘
```

봇이 알아서 클론 + 스킬 등록 + 온보딩까지 해줍니다!

**방법 2: 수동 설치**

```bash
# 1. 클론
cd ~/projects  # 또는 원하는 경로
git clone https://github.com/VoidLight00/adhd-quest-skill.git

# 2. OpenClaw 스킬 디렉토리에 등록
mkdir -p ~/.openclaw/workspace/skills/adhd-quest
ln -sf $(pwd)/adhd-quest-skill/SKILL.md ~/.openclaw/workspace/skills/adhd-quest/SKILL.md
ln -sf $(pwd)/adhd-quest-skill/references ~/.openclaw/workspace/skills/adhd-quest/references
```

### 첫 실행

설치 후 OpenClaw에게 말하세요:

```
"ADHD 퀘스트 시작해줘"
```

온보딩이 시작되며, **모든 설정은 인라인 버튼으로** 진행됩니다:

```
1️⃣  이름 입력
2️⃣  저장 경로 선택  →  Obsidian Vault / Documents / 직접 입력
3️⃣  퀘스트 선택     →  10개 중 원하는 것만 토글
4️⃣  알림 시간       →  아침 / 저녁
5️⃣  난이도          →  이지 / 노말 / 하드
```

설정이 완료되면 `adhd-config.json`이 생성되고, 크론잡이 자동 등록됩니다.

---

## ⚙️ 설정 파일

온보딩 완료 후 `adhd-config.json`이 생성됩니다.  
예시: [references/adhd-config-example.json](references/adhd-config-example.json)

```json
{
  "name": "현",
  "level": 1,
  "xp": 0,
  "streak": 0,
  "difficulty": "easy",
  "quests": {
    "morning": ["water", "meds", "plan"],
    "evening": ["emotion", "gratitude"]
  },
  "schedule": {
    "morning": "08:00",
    "evening": "21:00"
  }
}
```

---

## 🎮 RPG 시스템

### XP & 레벨

| 항목 | 기본 XP |
|------|---------|
| 퀘스트 완료 (개당) | +10 |
| 올클리어 보너스 | +15 |
| 감정/감사일기 | +10 |
| **하루 올클리어 합계** | **~85** |

### 레벨 & 칭호

> 🎯 **밸런스: 하드 올클 30일 → 마스터 도달**

| 레벨 | 칭호 | 누적 XP | 하드 | 노말 | 이지 |
|------|------|---------|------|------|------|
| 1 | 🌱 견습생 | 0 | 시작 | 시작 | 시작 |
| 2 | 🌿 수련생 | 200 | ~2일 | ~2일 | ~3일 |
| 3 | ⚔️ 전사 | 600 | ~5일 | ~6일 | ~8일 |
| 4 | 🔥 정예 전사 | 1,500 | ~11일 | ~14일 | ~18일 |
| **5** | **🛡️ 마스터** | **3,500** | **~28일** | **~35일** | **~45일** |
| 7 | 🌟 그랜드마스터 | 8,000 | ~60일 | ~75일 | ~100일 |
| 10 | 🏆 전설 | 20,000 | ~150일 | ~190일 | ~240일 |

### 스트릭 보너스

| 연속 일수 | 보너스 XP |
|-----------|-----------|
| 3일 | +30 |
| 7일 | +70 |
| 14일 | +150 |
| 30일 | +500 |

> 💡 **스트릭 유지 조건**: 하루에 퀘스트 1개만 완료해도 유지!

### 난이도 보정

| 난이도 | XP 배율 | 하루 올클 XP |
|--------|---------|-------------|
| 🟢 이지 | ×1.0 | ~85 |
| 🟡 노말 | ×1.3 | ~110 |
| 🔴 하드 | ×1.6 | ~136 |

---

## 📂 자동 저장 일지

```
{savePath}/일지/
├── 감정일기/
│   └── 2026-02-18.md      # 날짜, 이모지, 점수, 메모, 완료 퀘스트, XP
├── 감사일기/
│   └── 2026-02-18.md      # append 방식, 하루 1줄씩 축적
└── 주간리포트/
    └── 2026-W08.md         # 완료율, 감정 변화, 감사 모음, 잘한 점
```

---

## 🔧 커스터마이징

### 퀘스트 추가/제거

OpenClaw에게:
```
"설정 바꿔줘"
```
→ 설정 변경 메뉴가 인라인 버튼으로 표시됩니다.

### 알림 시간 변경

`adhd-config.json`의 `schedule` 필드를 직접 수정하거나, "설정 바꿔줘"로 변경.

### 난이도 변경

언제든 변경 가능. XP 배율이 즉시 적용됩니다.

### 특수 명령어

| 말하기 | 반응 |
|--------|------|
| "힘들어" / "불안해" | 긍정확언 + 호흡가이드 버튼 |
| "할 일 정리" | 퀘스트 보드 (긴급🔴/오늘🟡/여유🟢) |
| "다 했어" | 축하 + XP + 레벨 진행 바 |
| "미루고 있어" | 가장 쉬운 것 1개만 제안 |
| "설정 바꿔줘" | 설정 변경 메뉴 |

---

## 📁 스킬 구조

```
adhd-quest-skill/
├── SKILL.md                            # 메인 스킬 파일
├── README.md                           # 이 파일
├── LICENSE                             # MIT
├── .gitignore
└── references/
    ├── adhd-research.md                # 의학적 근거 & 논문 레퍼런스
    └── adhd-config-example.json        # 설정 파일 예시
```

---

## 📚 의학적 근거

이 스킬의 모든 기능은 ADHD 연구에 기반합니다.  
자세한 내용은 [references/adhd-research.md](references/adhd-research.md)를 참고하세요.

핵심 근거:
- **Task Chunking** — CBT 기반 실행기능 강화
- **외부화(Externalization)** — 작업기억 보완
- **게이미피케이션** — 도파민 보상경로 차이 활용
- **환경 구조화** — 유혹 저항 대신 환경 통제
- **감사 실천** — 긍정심리학 효과 입증

---

## 📜 License

MIT © [VoidLight](https://github.com/VoidLight00)
