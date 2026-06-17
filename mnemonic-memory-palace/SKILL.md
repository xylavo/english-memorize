---
name: mnemonic-memory-palace
description: Use to organize a group of related English words (a theme/category) by mentally placing each word at a vivid spot along a familiar route or rooms in a house (method of loci). Best for batches of thematically related vocabulary, not single isolated words. Often invoked by vocab-word-memorize when several related words are processed together.
metadata:
  category: education
  technique: method-of-loci
---

# 메모리 팰리스 / 장소법 (Method of Loci)

## 개요

사용자가 아주 익숙한 공간(자기 방, 등굣길, 집 구조 등)의 여러 지점(장소)에 단어 이미지를 하나씩 배치하고, 그 경로를 순서대로 "걸어가며" 단어를 떠올린다. 공간 기억은 매우 강력하고 오래가기 때문에, 특히 **여러 개의 관련 단어를 묶음으로** 외울 때 효과가 크다.

## 적합한 입력

- 같은 주제/카테고리의 단어 묶음 (예: 주방 관련 단어, 여행 관련 단어, 감정 표현 단어 등 3개 이상)
- 순서가 중요한 단어 목록(발표 스크립트 핵심어 등)

부적합: 단어 1개만 단독으로 외울 때는 비효율적 — mnemonic-keyword나 mnemonic-visualization을 우선 사용.

## 절차

1. **경로/장소 설정**: 사용자에게 익숙한 장소(예: "집 현관 → 거실 → 부엌 → 침실 → 화장실" 같은 경로)를 정한다. 사용자가 지정하지 않으면 흔한 동선(현관 → 거실 → 부엌 → 침실)을 기본값으로 제안한다.
2. **단어 배정**: 입력된 단어들을 경로상의 지점에 순서대로 하나씩 배정한다.
3. **장면 생성**: 각 지점에서 단어의 의미(또는 mnemonic-keyword로 만든 키워드 이미지)를 그 장소의 사물과 결합한 과장된 장면을 만든다.
4. **경로 요약**: 전체 경로를 순서대로 나열해 "이 순서대로 걸으면서 떠올리세요"라고 안내한다.

## 출력 형식

```
**메모리 팰리스 (경로: <경로 이름>)**
1. <장소 1> → <단어 1> : <장면 묘사>
2. <장소 2> → <단어 2> : <장면 묘사>
3. <장소 3> → <단어 3> : <장면 묘사>
...
```

## 예시

주제: 주방 관련 단어 (utensil 식기류, simmer 약불로 끓이다, garnish 장식하다)

```
**메모리 팰리스 (경로: 집 현관 → 거실 → 부엌)**
1. 현관 → utensil(도구, 식기) : 현관에 들어서자 신발이 아니라 숟가락·포크 같은 utensil이 잔뜩 널려있다.
2. 거실 → simmer(약불로 끓이다) : 거실 한가운데 작은 냄비가 보글보글 약불로 simmer 되고 있다.
3. 부엌 → garnish(장식하다) : 부엌 식탁 위 요리에 파슬리를 뿌려 garnish하는 장면이 펼쳐진다.
```

## 주의

- 한 경로에 한 번에 너무 많은 단어(7~10개 초과)를 넣지 않는다 — 필요하면 여러 경로로 나눈다.
- 장면은 가능한 한 구체적이고 움직임이 있어야 더 잘 기억된다.
