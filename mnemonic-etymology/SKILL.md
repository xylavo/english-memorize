---
name: mnemonic-etymology
description: Use to break an English word into prefix/root/suffix (Greek/Latin morphemes), explain the literal meaning derivation, and link it to a family of related words sharing the same root. Best for technical/academic/jargon terms and longer multi-syllable words. Often invoked by vocab-word-memorize.
metadata:
  category: education
  technique: etymology-morpheme-analysis
---

# 어원·어근 분석법 (Etymology / Morpheme Analysis)

## 개요

단어를 의미를 가진 최소 단위(접두사-어근-접미사)로 분해하여, 각 조각의 뜻을 합쳐서 전체 단어의 뜻을 "유도"해낸다. 하나의 어근을 알면 같은 어근을 공유하는 수십 개의 단어로 확장 가능하다. 전문용어(의학·법률·과학 용어 등)는 대부분 그리스/라틴어 어근으로 구성되어 있어 이 기법이 가장 강력하다.

## 적합한 입력

- 전문용어, 학술어 (대부분 라틴/그리스 어근)
- 3음절 이상의 길고 복잡한 단어
- 접두사/접미사가 뚜렷이 구분되는 단어

부적합: 짧은 게르만어 기원 단어(예: dog, run, big)는 분해해도 의미 단위가 거의 없음 → mnemonic-keyword나 mnemonic-context 사용.

## 절차

1. **형태소 분해**: 단어를 접두사(prefix) + 어근(root) + 접미사(suffix)로 나눈다. 모르는 단어라도 알려진 어근 패턴(아래 참고 목록)을 적용해본다.
2. **각 조각의 뜻**: 접두사·어근·접미사 각각의 의미를 한국어로 제시한다.
3. **의미 합성**: 조각들의 뜻을 순서대로 합쳐 "직역" 문구를 만들고, 이것이 어떻게 실제 뜻으로 연결되는지 설명한다.
4. **워드 패밀리 확장**: 같은 어근을 공유하는 단어 2~4개를 예시로 들어 묶음으로 제시한다 (품사 변형 포함 가능).

## 자주 쓰이는 어근/접두사/접미사 (참고)

| 형태소 | 의미 | 예시 단어 |
|---|---|---|
| bene- | 좋은 | benefit, benevolent, benefactor |
| mal- | 나쁜 | malice, malfunction, malevolent |
| -vol- / -vol(unt)- | 의지, 바라다 | volunteer, malevolent, benevolent |
| -spect- | 보다 | inspect, spectator, retrospect |
| -duc(t)- | 이끌다 | introduce, conduct, deduce |
| -port- | 옮기다 | transport, portable, export |
| trans- | 가로질러 | transport, transform, transmit |
| pre- | 앞에, 미리 | predict, prevent, preview |
| post- | 뒤에 | postpone, postscript |
| -graph / -gram | 쓰다, 기록 | biography, telegram, photograph |
| -phobia | 공포 | claustrophobia, arachnophobia |
| -logy | 학문 | biology, psychology |
| sub- | 아래 | submarine, subway, subtract |
| anti- | 반대 | antibody, antisocial |
| -ology / -ician | ~학, ~사람 | technician, biologist |

## 출력 형식

```
**어원 분석**
- 분해: <접두사> + <어근> + <접미사>
- 각 의미: <접두사 뜻> / <어근 뜻> / <접미사 뜻(품사 변화 포함)>
- 직역 → 실제 뜻: "<직역>" → "<실제 뜻>"
- 같은 어근 단어: <단어1>, <단어2>, <단어3>
```

## 예시

- **benevolent** /bəˈnevələnt/ (자비로운, 인자한)
  - 분해: bene- + vol + -ent
  - 각 의미: bene-(좋은) / vol(의지, 바라다) / -ent(형용사형 어미)
  - 직역 → 실제 뜻: "좋은 것을 바라는" → "자비로운"
  - 같은 어근 단어: benefit(이익), benefactor(후원자), malevolent(악의적인, mal=나쁜)

- **postpone** /poʊstˈpoʊn/ (연기하다, 미루다)
  - 분해: post- + pone(< pon, 놓다)
  - 각 의미: post-(뒤에) / pon(놓다)
  - 직역 → 실제 뜻: "뒤로 놓다" → "연기하다"
  - 같은 어근 단어: postscript(추신), component(구성요소, com+pon), opponent(상대, op+pon)

## 주의

- 모르는 단어의 어원이 불확실하면 추측임을 표시하고, 너무 견강부회한 분해는 피한다.
- 워드 패밀리 확장은 사용자의 학습 부담을 늘릴 수 있으므로 2~4개로 제한한다.
