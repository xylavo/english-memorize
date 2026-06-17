---
name: mnemonic-confusable-pair
description: Use to contrast a word with its commonly confused counterpart (similar spelling/sound/meaning, e.g. affect/effect, complement/compliment, principle/principal, stationary/stationery) — pinpoints the exact distinguishing feature and gives a memorable trick plus contrasting example sentences for both words. Best when the target word has a well-known confusable pair; goes deeper than mnemonic-context's brief synonym note. Often invoked by vocab-word-memorize and vocab-sentence-memorize when a confusable counterpart exists.
metadata:
  category: education
  technique: confusable-pair-contrast
---

# 혼동어 대조법 (Confusable Pair Contrast)

## 개요

철자나 발음이 비슷해서 자주 헷갈리는 단어 짝(affect/effect, complement/compliment, principle/principal 등)은, 단어 하나만 따로 외우면 오히려 둘을 구분하는 데 실패하기 쉽다. 이 기법은 두 단어를 나란히 놓고 **차이점이 정확히 어디서 오는지**를 짚어준 뒤, 그 차이를 기억하는 트릭과 대조 예문을 함께 제공한다.

## 적합한 입력

- 철자/발음이 비슷해 흔히 혼동되는 단어 짝이 존재하는 단어 (affect/effect, complement/compliment, principle/principal, stationary/stationery, lose/loose, except/accept 등)
- 품사가 같아서 문맥만으로는 구분이 안 되는 경우

부적합: 혼동되는 짝이 따로 없는 단어 — 이 경우 `mnemonic-context`의 일반 유의어 비교를 사용한다.

## 절차

1. **혼동 짝 확인**: 대상 단어와 자주 헷갈리는 짝 단어를 확인한다. 모르면 알고 있는 지식을 활용하고, 확신이 없으면 추측임을 밝힌다.
2. **차이의 근원 짚기**: 두 단어가 왜 헷갈리는지(철자 유사/발음 유사/의미 인접)와, 실제로 구분하는 핵심 기준(품사, 어근, 의미 범위 등)을 한 줄로 짚는다.
3. **구분 트릭 만들기**: 철자의 특정 글자나 어근에 기반한 기억 트릭을 1개 만든다 (예: "effect는 E로 시작 = End result(결과)").
4. **대조 예문**: 두 단어 각각 자연스러운 예문 1개씩 제시해, 같은 문맥에 넣었을 때 의미가 어떻게 달라지는지 보여준다.

## 출력 형식

```
**혼동어 대조**
혼동 짝: <단어 A> vs <단어 B>
헷갈리는 이유: <철자/발음/의미 유사성 한 줄>
구분 기준: <품사/어근/의미 범위 등 핵심 차이>
구분 트릭: <기억 트릭 한 줄>
예문 A: <영어 문장> — <해석>
예문 B: <영어 문장> — <해석>
```

## 예시

- **affect** (동사, 영향을 미치다) vs **effect** (명사, 결과·효과)

```
**혼동어 대조**
혼동 짝: affect vs effect
헷갈리는 이유: 철자 한 글자(a/e) 차이로 거의 동일하게 보임
구분 기준: affect는 거의 항상 동사(영향을 주다), effect는 거의 항상 명사(결과)
구분 트릭: "A는 Action(동작) → affect는 동사", "E는 End result(결과) → effect는 명사"
예문 A: The cold weather will affect the harvest. — 추운 날씨가 수확에 영향을 줄 것이다.
예문 B: The effect of the cold weather was a smaller harvest. — 추운 날씨의 결과는 더 적은 수확이었다.
```

- **complement** (보완하다/보완물) vs **compliment** (칭찬하다/칭찬)

```
**혼동어 대조**
혼동 짝: complement vs compliment
헷갈리는 이유: 발음이 거의 동일(/ˈkɑːmplɪmənt/), 철자도 e/i 한 글자만 다름
구분 기준: complement = 완전하게(complete) 만들어주는 것 / compliment = 칭찬(praise)
구분 트릭: "complEte처럼 e가 있으면 보완, complIment는 I(나)에게 하는 칭찬"
예문 A: The wine complements the dish perfectly. — 그 와인은 요리를 완벽하게 보완해준다.
예문 B: She gave me a nice compliment on my presentation. — 그녀는 내 발표에 좋은 칭찬을 해줬다.
```

## 주의

- 혼동 짝이 불확실하거나 억지로 만든 것이면 표시하고, 더 잘 알려진 다른 짝이 있는지 사용자에게 확인을 유도한다.
- 트릭은 짧고 단순해야 한다 — 트릭 자체가 복잡하면 본래 단어보다 외우기 어려워진다.
