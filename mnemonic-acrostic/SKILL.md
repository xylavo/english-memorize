---
name: mnemonic-acrostic
description: Use to create an acronym (first letters spell a memorable word) or an acrostic (first letters/words spell a memorable sentence) for memorizing the order of words in a sentence, a list of items, or a set of vocabulary. Often invoked by vocab-sentence-memorize for long sentences, and by vocab-word-memorize when memorizing an ordered word list.
metadata:
  category: education
  technique: acronym-acrostic
---

# 두문자어 / 어크로스틱 (Acronym / Acrostic)

## 개요

여러 항목(단어, 문장 성분)의 첫 글자(또는 첫 음절)를 따서 새로운 단어(두문자어) 또는 기억하기 쉬운 문장(어크로스틱)을 만든다. **순서**가 중요한 정보를 외울 때 특히 유용하다.

## 적합한 입력

- 긴 문장의 단어 순서를 통째로 외우고 싶을 때
- 순서가 있는 단어 목록 (예: 행성 이름, 색깔 순서, 발표 핵심어)
- 문법 규칙(예: 조동사 종류, 전치사 목록)

## 절차

1. **핵심 항목 추출**: 문장이면 핵심 단어(내용어 위주, 관사/전치사 등 기능어는 생략 가능)를 순서대로 나열한다. 단어 목록이면 그대로 사용한다.
2. **두문자 추출**: 각 항목의 첫 글자(영어) 또는 핵심 음절을 뽑는다.
3. **두 가지 방식 중 선택**:
   - **두문자어(Acronym)**: 첫 글자들을 모아 발음 가능한 새 단어를 만든다 (예: HOMES = Huron, Ontario, Michigan, Erie, Superior).
   - **어크로스틱(Acrostic)**: 각 첫 글자로 시작하는 단어들을 엮어 재미있는 한국어/영어 문장을 만든다 (예: "My Very Educated Mother Just Served Us Noodles" = 행성 순서).
4. 만든 두문자어/어크로스틱과 원래 항목을 나란히 제시해 매핑을 명확히 한다.

## 출력 형식

```
**어크로스틱**
원본 순서: <항목1> - <항목2> - <항목3> - ...
두문자: <글자1><글자2><글자3>...
기억 문구: "<두문자로 시작하는 단어들로 구성된 문장>"
```

## 예시

문장: "I Have a Dream that one day this nation will rise up." (핵심어: I, Have, Dream, Nation, Rise)

```
**어크로스틱**
원본 순서: I - Have - Dream - Nation - Rise
두문자: I-H-D-N-R
기억 문구: "I Hate Doing Nothing, Really" → 각 단어의 첫 글자가 원문의 핵심어 순서를 떠올리게 해줌
```

단어 목록: mitigate(완화하다), reluctant(꺼리는), eloquent(웅변적인) — 순서대로 외워야 할 때

```
**어크로스틱**
원본 순서: mitigate - reluctant - eloquent
두문자: M-R-E
기억 문구: "Many Rabbits Eat" → M(완화) R(꺼림) E(웅변) 순서로 연결
```

## 주의

- 만든 어크로스틱 문장이 단어 자체보다 복잡하면 역효과 — 짧고 리듬감 있게 만든다.
- 순서 자체가 중요하지 않은 경우엔 이 기법보다 mnemonic-keyword/mnemonic-storytelling이 더 적합하다.
