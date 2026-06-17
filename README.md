# English Vocab & Sentence Memorize Skills

[Claude Code](https://claude.com/claude-code) 스킬 모음으로, 영어 단어/문장을 입력하면 **적용 가능한 모든 암기법(mnemonic technique)을 동원해 학습 카드를 만들고, 그중 가장 효과적인 기법을 추천**하며, **간격 반복 복습 일정**까지 자동으로 생성해줍니다.

## 빠른 사용법

```
mirage 외워줘
benevolent 단어 암기법 알려줘
이 문장 분석해줘: Despite the heavy rain, she decided to walk to the station.
이 문단 번역하고 어려운 거 정리해줘: <영어 문단>
```

결과는 `~/Desktop/memory/<단어 또는 문장 슬러그>.md` 파일로 저장됩니다.

## 구조

세 개의 **진입점 스킬**과 아홉 개의 **보조 암기법(mnemonic-\*) 스킬**로 구성됩니다. 진입점 스킬이 호출되면, 입력 특성에 맞는 보조 스킬들을 자동으로 골라 호출하고 결과를 하나의 학습 카드로 합칩니다.

```
english-translate-memorize  (번역 + 난이도 판별 → 아래 두 스킬 자동/선택 호출)
        │
        ├─▶ vocab-word-memorize      (단어 1개)
        │         │
        └─▶ vocab-sentence-memorize  (문장/표현 1개)
                  │
                  ▼
        mnemonic-keyword / etymology / visualization / context /
        storytelling / phonetic-rhythm / chunking / acrostic /
        memory-palace  (적용 가능한 것만 선택적으로 호출)
                  │
                  ▼
        mnemonic-spaced-repetition  (복습 일정 생성, 항상 마지막에 호출)
```

### 진입점 스킬

| 스킬 | 입력 | 동작 |
|---|---|---|
| `english-translate-memorize` | 영어 문장/문단 | 문장 단위로 한국어 번역 → 어려운 단어/표현을 "확실히 어려움"/"애매함"으로 분류 → 확실한 것은 자동, 애매한 것은 사용자 선택 후 `vocab-word-memorize`/`vocab-sentence-memorize` 호출 |
| `vocab-word-memorize` | 영단어/숙어/전문용어 1개 | 적용 가능한 모든 mnemonic-\* 기법을 생성하고, 이 단어에 가장 추천하는 기법 1개를 선정. 복습 일정 포함 |
| `vocab-sentence-memorize` | 영어 문장/표현 1개 | 직역·의역, 문법 구조, 관용구 유래, 원어민 뉘앙스, 유사 표현, 활용 예문으로 심층 분석 → 보조적으로 mnemonic-\* 기법 적용 |

### 보조 암기법 스킬 (mnemonic-*)

| 스킬 | 기법 | 가장 잘 맞는 대상 |
|---|---|---|
| `mnemonic-keyword` | 발음 기반 한국어 키워드 연상 | 발음이 독특한 구체 명사·형용사 |
| `mnemonic-etymology` | 접두사/어근/접미사 분해 + 워드 패밀리 | 라틴/그리스 어원 전문용어, 3음절 이상 단어 |
| `mnemonic-visualization` | 이미지·동작 시각화(이중부호화) | 동사, 감각/공간 형용사 |
| `mnemonic-context` | 예문·연어·유의어 비교 | 추상명사, 기능어(however 등) |
| `mnemonic-storytelling` | 짧은 이야기로 단어 엮기 | 추상어, 숙어, 구동사, 관련 단어 묶음 |
| `mnemonic-phonetic-rhythm` | 강세 표시, 리듬, 섀도잉 가이드 | 발음/강세가 까다로운 단어·문장 |
| `mnemonic-chunking` | 형태소 또는 문장성분 단위 분해 | 긴 복합어, 모든 문장 |
| `mnemonic-acrostic` | 두문자어/어크로스틱 | 어순이 중요한 문장, 순서 있는 단어 목록 |
| `mnemonic-memory-palace` | 장소법(경로에 단어 배치) | 같은 주제의 단어 묶음(3개 이상) |
| `mnemonic-spaced-repetition` | 라이트너 간격 반복(1/3/7/14/30일) | 모든 학습 카드의 마지막 단계 |

## 저장 형식

각 학습 카드는 `~/Desktop/memory/`에 단어 또는 문장별로 별도 파일(`mirage.md`, `despite-heavy-rain-decided.md` 등)로 저장되며, 다음을 포함합니다.

- 적용된 모든 암기법의 출력 (해당 없는 기법은 사유 명시)
- 추천 암기법 1개와 이유
- 오늘 날짜 기준 1/3/7/14/30일 후 복습 일정 표

## 설치

```bash
git clone https://github.com/xylavo/english-memorize.git
```

클론한 디렉터리(또는 그 안의 스킬 폴더들)를 Claude Code 스킬 경로(예: 프로젝트 루트의 `skills/` 또는 `~/.claude/skills/`)에 두면 각 하위 폴더의 `SKILL.md`가 자동으로 인식됩니다.

## 라이선스

[MIT](LICENSE)
