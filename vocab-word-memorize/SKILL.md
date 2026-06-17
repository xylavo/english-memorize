---
name: vocab-word-memorize
description: Use when the user gives a single English word, idiom, or technical term and wants to memorize it. Generates ALL applicable mnemonic techniques by invoking every relevant mnemonic-* skill (keyword, etymology, visualization, context, storytelling, phonetic-rhythm, chunking when relevant), ends with a single recommended technique, schedules spaced-repetition reviews, and saves the result as its own file under ~/Desktop/memory/. Examples: "mirage 외워줘", "benevolent 단어 암기법 알려줘", "claustrophobia 외우는 법".
metadata:
  category: education
  type: composite
---

# 영단어 암기 스킬 (Word Memorize)

## 개요

영단어/숙어/전문용어 1개를 입력받아, **적용 가능한 모든 암기법**을 생성해 보여주고, 마지막에 **이 단어에 가장 추천하는 암기법 1개**를 콕 집어준다. 결과는 단어별로 별도 파일에 저장한다.

## 기본 설정

- **저장 폴더**: `~/Desktop/memory/` (없으면 생성)
- **파일명**: `<단어>.md` (예: `mirage.md`, `benevolent.md`). 단어마다 새 파일을 만든다 (한 파일에 누적하지 않음). 이미 같은 파일이 있으면 덮어쓰기 전에 사용자에게 확인한다.
- 한 번에 단어/문장 1개씩 처리한다.

## 절차

### 1. 단어 정보 확인

- 입력된 단어의 **뜻, 품사, 발음(IPA 또는 한글 표기)**을 파악한다. 모르면 알고 있는 지식을 활용하고, 불확실하면 사용자에게 확인을 요청한다.
- 단어가 영어 사전에 없는 고유명사/브랜드명 등이면 사용자에게 알리고 어떻게 처리할지 확인한다.

### 2. 적용 가능 여부 판단

아래 표를 기준으로 각 `mnemonic-*` 기법의 적용 가능 여부를 판단한다.

| 기법 | 단일 단어 적용 가능 여부 |
|---|---|
| `mnemonic-keyword` | 항상 적용 |
| `mnemonic-etymology` | 식별 가능한 접두사/어근/접미사가 있으면 적용. 짧은 게르만어 기원 단어 등 분해 의미가 없으면 "해당 없음"으로 표시하고 이유 설명 |
| `mnemonic-visualization` | 항상 적용 |
| `mnemonic-context` | 항상 적용 |
| `mnemonic-storytelling` | 항상 적용 |
| `mnemonic-phonetic-rhythm` | 항상 적용 |
| `mnemonic-chunking` | 3음절 이상이거나 복합어/긴 단어면 적용, 짧은 단어면 "해당 없음" |
| `mnemonic-acrostic` | 단일 단어에는 기본적으로 "해당 없음" (여러 단어/철자 순서 암기용) — 단, 철자가 매우 길고 복잡해 철자 순서 자체를 암기해야 하는 경우만 적용 |
| `mnemonic-memory-palace` | 단일 단어에는 "해당 없음" (관련 단어 묶음 암기용) |

### 3. 적용 가능한 기법 모두 실행

"적용 가능"으로 판단된 모든 기법에 대해 Skill 도구로 해당 `mnemonic-*` 스킬을 호출한다 (인자: 단어, 뜻, 품사, 발음). "해당 없음"인 기법은 호출하지 않고 한 줄 사유만 기록한다.

### 4. 추천 암기법 선정

적용된 기법들 중, 아래 우선순위 가이드를 참고해 **이 단어에 가장 효과적인 기법 1개**를 선정하고 이유를 1~2문장으로 설명한다.

| 단어 특성 | 추천 우선순위 |
|---|---|
| 전문용어 / 그리스·라틴 어근이 뚜렷함 | `mnemonic-etymology` |
| 발음이 한국어와 자연스럽게 매칭되는 구체 명사·형용사 | `mnemonic-keyword` |
| 동작을 그릴 수 있는 동사 | `mnemonic-visualization` |
| 추상 명사 / 기능어 / 뉘앙스가 중요한 유의어 | `mnemonic-context` |
| 숙어·관용구 | `mnemonic-storytelling` |
| 강세/발음이 특히 까다로움 | `mnemonic-phonetic-rhythm` |

### 5. 복습 스케줄 생성

`mnemonic-spaced-repetition` 스킬을 호출해 오늘 날짜 기준 복습 일정을 생성한다.

### 6. 파일 작성

`~/Desktop/memory/<단어>.md` 파일을 아래 형식으로 작성한다.

```markdown
# <단어> /<발음>/ — <품사> <뜻>
등록일: <YYYY-MM-DD>

## 적용 가능한 모든 암기법

### 1. 키워드 연상법
<mnemonic-keyword 출력>

### 2. 어원 분석
<mnemonic-etymology 출력 또는 "해당 없음 — <이유>">

### 3. 이미지 연상
<mnemonic-visualization 출력>

### 4. 문맥 학습
<mnemonic-context 출력>

### 5. 스토리텔링
<mnemonic-storytelling 출력>

### 6. 음성·리듬
<mnemonic-phonetic-rhythm 출력>

### 7. 청킹
<mnemonic-chunking 출력 또는 "해당 없음 — <이유>">

### 8. 어크로스틱
해당 없음 — 단일 단어 철자/순서 암기용 기법으로, 이 단어에는 불필요

### 9. 메모리 팰리스
해당 없음 — 여러 단어 묶음을 함께 외울 때 사용하는 기법

## 추천 암기법

**<추천 기법 이름>** — <추천 이유 1~2문장>

## 복습 스케줄
<mnemonic-spaced-repetition 출력>
```

### 7. 출력

위 파일 내용을 사용자에게도 그대로 보여준다.

## 완료 기준

- 적용 가능한 모든 기법이 실제로 호출되어 결과가 포함되었다.
- 해당 없는 기법은 이유와 함께 명시되었다.
- 마지막에 추천 암기법 1개와 이유가 제시되었다.
- `~/Desktop/memory/<단어>.md` 파일로 저장되었다.
