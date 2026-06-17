---
name: english-translate-memorize
description: Use when the user gives English sentence(s) or a paragraph and wants both a Korean translation and automatic organization of difficult words/expressions into the vocab-word-memorize / vocab-sentence-memorize mnemonic skills. Translates the full input naturally (sentence by sentence), flags high-school-level-or-above difficult vocabulary and idiomatic/complex-grammar sentences, auto-processes clearly-difficult items and asks the user to pick from ambiguous candidates, then invokes the memorize skills for each chosen item. Examples: "이 문장 번역하고 어려운 거 정리해줘: ...", "이 문단 해석해주고 단어 정리도 해줘", "번역 + 암기 정리".
metadata:
  category: education
  type: composite
---

# 영어 번역 + 암기 정리 스킬

## 개요

영어 문장 또는 문단을 입력받아 **자연스러운 한국어로 번역**하고, 그 안에서 **고등학생 기준으로 어려운 단어/표현 및 문장**을 추려 `vocab-word-memorize`(단어) / `vocab-sentence-memorize`(문장·표현) 스킬로 자동 정리한다. 명확히 어려운 항목은 바로 정리하고, 애매한 항목은 사용자에게 선택받은 뒤 정리한다.

## 기본 설정

- 입력은 영어 문장 1개 또는 여러 문장으로 이루어진 문단 1개를 한 번에 처리한다 (문단 전체 처리).
- 단어/문장 암기 정리 결과 파일은 `vocab-word-memorize`, `vocab-sentence-memorize` 스킬이 각자의 규칙대로 `~/Desktop/memory/`에 저장한다 (이 스킬이 직접 파일을 만들지 않음).

## 절차

### 1단계: 번역

- 입력 문단을 문장 단위로 나누어 **영어 원문 - 한국어 번역**을 짝지어 보여준다.
- 직역과 자연스러운 의역의 차이가 클 경우, 짧게 보충 설명을 덧붙인다.

### 2단계: 어려운 단어/표현 후보 추출

문단 전체를 훑으며 아래 기준으로 후보를 뽑는다.

**단어/구 후보**
- 고등학교 영어 교육과정 어휘 수준을 넘어서는 단어 (추상명사, 전문용어, 저빈도 어휘)
- 다의어인데 이 문맥에서는 기본 의미가 아닌 특이한 의미로 쓰인 경우
- 구동사(phrasal verb)나 자주 헷갈리는 콜로케이션

**문장/표현 후보**
- 관용구, 비유적 표현 (직역으로는 의미가 안 통하는 경우)
- 가정법, 도치, 분사구문, 생략, 강조구문 등 복잡한 구조라서 통째로 익혀야 하는 문장

각 후보를 다음 두 그룹으로 분류한다.

| 분류 | 기준 | 처리 |
|---|---|---|
| 확실히 어려움 | 고등학생이 봤을 때 사전 없이는 의미/구조 파악이 어렵다고 판단되는 항목 | 3단계에서 자동 처리 |
| 애매함 | 학생 수준에 따라 알 수도/모를 수도 있는 항목 (예: 중상위권 어휘, 흔히 쓰이는 숙어) | 4단계에서 사용자 선택 |

후보가 전혀 없으면(문장이 평이한 경우) 그대로 사용자에게 알리고 종료한다.

### 3단계: 확실히 어려운 항목 자동 처리

- "확실히 어려움"으로 분류된 단어 각각에 대해, Skill 도구로 `vocab-word-memorize`를 호출한다 (인자: 해당 단어).
- "확실히 어려움"으로 분류된 문장/표현 각각에 대해, Skill 도구로 `vocab-sentence-memorize`를 호출한다 (인자: 해당 문장).
- 한 번에 단어/문장 1개씩만 처리하는 것이 두 스킬의 규칙이므로, 여러 개면 순서대로 반복 호출한다.

### 4단계: 애매한 항목 사용자 선택

- "애매함"으로 분류된 후보들을 번역 결과 아래에 리스트로 보여준다 (단어/표현 + 간단한 뜻 포함).
- AskUserQuestion으로 사용자가 정리하고 싶은 항목을 선택하게 한다 (다중 선택 가능, "없음" 선택지 포함).
- 선택된 항목에 대해서만 3단계와 동일하게 `vocab-word-memorize` / `vocab-sentence-memorize`를 호출한다.

### 5단계: 결과 요약

아래 내용을 사용자에게 정리해서 보여준다.

```markdown
## 번역
- EN: <원문 문장>
  KO: <번역>
(문장마다 반복)

## 암기 정리 완료
- <단어/문장> → ~/Desktop/memory/<파일명>.md (자동 처리: 확실히 어려움 / 사용자 선택)

## 정리하지 않은 애매한 후보
- <단어/문장> — <간단한 뜻> (선택 안 됨)
```

## 완료 기준

- 입력 문단 전체가 문장 단위로 번역되었다.
- "확실히 어려움" 항목은 모두 자동으로 해당 암기 스킬이 호출되어 파일로 저장되었다.
- "애매함" 항목은 사용자에게 제시되었고, 선택된 항목만 암기 스킬이 호출되어 파일로 저장되었다.
- 최종 요약에 번역, 정리 완료 항목(파일 경로 포함), 정리하지 않은 후보가 모두 포함되었다.
