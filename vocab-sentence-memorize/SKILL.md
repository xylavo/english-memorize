---
name: vocab-sentence-memorize
description: Use when the user gives an English sentence or expression and wants to fully understand and master it like a native speaker — meaning, why an idiom means what it means, why the grammar is structured that way, native nuance/usage situations, and similar expressions — plus optional memorization techniques. Generates a deep-dive analysis first, then ALL applicable mnemonic techniques, ends with a single recommended technique, and saves the result as its own file under ~/Desktop/memory/. Examples: "이 문장 분석해줘: ...", "이 표현 왜 이런 뜻이야?", "이 문장 원어민처럼 쓰려면".
metadata:
  category: education
  type: composite
---

# 영문장 완전정복 스킬 (Sentence Deep-Dive & Memorize)

## 개요

영어 문장/표현 1개를 입력받아, 단순 암기가 아니라 **완전히 이해하고 원어민처럼 쓸 수 있도록** 심층 분석한다. 그 다음 보조적으로 **적용 가능한 모든 암기법**을 생성하고, 마지막에 **가장 추천하는 암기법 1개**를 콕 집어준다. 결과는 문장별로 별도 파일에 저장한다.

## 기본 설정

- **저장 폴더**: `~/Desktop/memory/` (없으면 생성)
- **파일명**: 문장에서 핵심 단어 2~3개를 따서 영문 슬러그로 만든다 (예: "Despite the heavy rain, she decided..." → `despite-heavy-rain-decided.md`). 이미 같은 파일이 있으면 덮어쓰기 전에 사용자에게 확인한다.
- 한 번에 문장/표현 1개씩 처리한다.

## 절차

### 1단계: 심층 분석 (핵심)

다음 항목을 빠짐없이 작성한다. 모르는 부분은 추측임을 밝히고, 불확실하면 사용자에게 확인을 요청한다.

1. **직역 vs 의역**: 단어 그대로 직역한 의미와, 실제로 통하는 자연스러운 한국어 의미를 둘 다 제시한다. 둘이 다르다면 그 간극이 어디서 오는지 설명한다.
2. **문법 구조 분석**: 문장을 구성 요소(주어/동사/목적어/수식어/절)로 나누고, 왜 이런 어순·시제·구문(예: 가정법, 도치, 분사구문, to부정사 등)을 쓰는지 설명한다. 일반적인 어순과 다른 점이 있다면 그 이유를 짚는다.
3. **관용구/숙어 유래(해당 시)**: 비유적 표현이라면, 문자 그대로의 의미(직역)에서 어떻게 현재의 비유적 의미로 발전했는지 — 어원/역사적 배경/유래 가설을 설명한다. 일반 표현이면 이 항목은 생략한다.
4. **원어민 뉘앙스 & 사용 상황**: 이 표현을 누가, 언제, 어떤 어조(격식/비격식, 친밀도)로 쓰는지. 쓰면 어색하거나 부적절한 상황이 있다면 함께 짚는다.
5. **유사 표현과 차이**: 의미가 비슷한 다른 표현 1~2개를 들고, 뉘앙스/격식/구조 차이를 비교한다.
6. **활용 예문**: 같은 패턴/표현을 응용한 새 예문 1~2개를 만들어, 사용자가 직접 쓸 수 있는 형태로 보여준다.

### 2단계: 암기법 (보조)

심층 분석 이후, 아래 표를 기준으로 적용 가능한 모든 `mnemonic-*` 기법을 호출한다. "해당 없음"인 기법은 호출하지 않고 한 줄 사유만 기록한다.

| 기법 | 문장 적용 가능 여부 |
|---|---|
| `mnemonic-chunking` | 항상 적용 (의미 단위 분해) |
| `mnemonic-phonetic-rhythm` | 항상 적용 (강세·연음·섀도잉) |
| `mnemonic-acrostic` | 항상 적용 (어순 암기용 두문자) |
| `mnemonic-storytelling` | 관용구/비유 표현이거나 추상적 의미가 있으면 적용, 평범한 문장이면 "해당 없음" |
| `mnemonic-keyword` | 문장 내 핵심 단어 1~2개에 대해 적용 |
| `mnemonic-visualization` | 문장 전체 상황 또는 핵심 동사에 대해 적용 |
| `mnemonic-etymology` | 문장 내 핵심 단어가 어원 분해 가능하면 적용, 없으면 "해당 없음" |
| `mnemonic-context` | 1단계 심층 분석에서 이미 다뤘으므로 별도 호출 없이 "1단계 참고"로 표시 |
| `mnemonic-memory-palace` | 단일 문장에는 기본적으로 "해당 없음" (여러 문장/표현 묶음 암기용) |

### 3단계: 추천 암기법 선정

적용된 기법들 중, 아래 가이드를 참고해 **이 문장에 가장 효과적인 기법 1개**를 선정하고 이유를 1~2문장으로 설명한다.

| 문장 특성 | 추천 우선순위 |
|---|---|
| 어순/구조가 복잡해 통째로 외워야 함 | `mnemonic-chunking` 또는 `mnemonic-acrostic` |
| 발음/억양이 핵심인 회화 표현 | `mnemonic-phonetic-rhythm` |
| 관용구/비유적 의미가 핵심 | `mnemonic-storytelling` |
| 문장 속 핵심 단어 자체가 암기 난이도의 대부분을 차지 | 그 단어에 적용한 `mnemonic-keyword`/`mnemonic-etymology` |

### 4단계: 복습 스케줄 생성

`mnemonic-spaced-repetition` 스킬을 호출해 오늘 날짜 기준 복습 일정을 생성한다.

### 5단계: 파일 작성

`~/Desktop/memory/<슬러그>.md` 파일을 아래 형식으로 작성한다.

```markdown
# "<문장>"
등록일: <YYYY-MM-DD>

## 1. 직역 vs 의역
- 직역: <직역>
- 의역: <자연스러운 한국어 의미>
- (간극 설명, 필요 시)

## 2. 문법 구조 분석
<구성 요소 분해 + 구문 설명>

## 3. 관용구/숙어 유래
<유래 설명 또는 "해당 없음 — 비유적 표현이 아님">

## 4. 원어민 뉘앙스 & 사용 상황
<설명>

## 5. 유사 표현과 차이
<비교>

## 6. 활용 예문
- <예문 1>
- <예문 2>

---

## 암기법 (보조)

### 청킹
<출력>

### 음성·리듬
<출력>

### 어크로스틱
<출력>

### 스토리텔링
<출력 또는 "해당 없음 — <이유>">

### 키워드 연상법 (핵심 단어: <단어>)
<출력>

### 이미지 연상
<출력>

### 어원 분석 (핵심 단어: <단어>)
<출력 또는 "해당 없음 — <이유>">

### 문맥 학습
1단계 "원어민 뉘앙스 & 사용 상황" 참고

### 메모리 팰리스
해당 없음 — 여러 문장/표현 묶음을 함께 외울 때 사용하는 기법

## 추천 암기법

**<추천 기법 이름>** — <추천 이유 1~2문장>

## 복습 스케줄
<mnemonic-spaced-repetition 출력>
```

### 6단계: 출력

위 파일 내용을 사용자에게도 그대로 보여준다.

## 완료 기준

- 1단계 심층 분석 6개 항목이 모두 작성되었다 (해당 없는 항목은 사유 명시).
- 적용 가능한 모든 암기법이 호출되어 결과가 포함되었다.
- 마지막에 추천 암기법 1개와 이유가 제시되었다.
- `~/Desktop/memory/<슬러그>.md` 파일로 저장되었다.
