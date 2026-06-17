---
name: mnemonic-chunking
description: Use to break a long word, idiom, or sentence into smaller meaningful chunks (morphemes for words; subject/verb/object/modifier phrases for sentences) to reduce cognitive load before memorizing. Almost always invoked first by vocab-sentence-memorize, and for very long/compound words by vocab-word-memorize.
metadata:
  category: education
  technique: chunking
---

# 청킹 (Chunking)

## 개요

긴 정보를 의미 있는 작은 묶음(청크)으로 나누면 한 번에 처리해야 할 정보량이 줄어들어 기억 부담이 크게 감소한다. 단어에서는 형태소 단위, 문장에서는 통사적(주어-동사-목적어-수식어) 단위로 나눈다.

## 적합한 입력

- 긴 복합어, 합성어
- 모든 문장/긴 표현 (sentence-memorize에서 항상 1순위로 적용)

## 절차 (단어)

1. 단어를 형태소(접두사/어근/접미사) 또는 의미가 통하는 음절 묶음으로 나눈다. (자세한 어원 분석이 필요하면 mnemonic-etymology와 병행)
2. 각 청크를 하이픈으로 구분해 표시한다.

## 절차 (문장)

1. 문장을 핵심 통사 단위로 나눈다: 주어(S) / 동사구(V) / 목적어·보어(O,C) / 수식어구(전치사구, 부사구, 종속절 등)
2. 각 청크의 의미를 한국어로 짧게 병기한다.
3. 청크 수가 5개를 넘으면 더 큰 단위로 묶거나, 2단계(먼저 큰 절 단위 → 그 다음 구 단위)로 나눈다.
4. 청크를 순서대로 다시 결합해 전체 문장을 재구성하는 연습 문구를 제시한다.

## 출력 형식 (단어)

```
**청킹**
<청크1> - <청크2> - <청크3>
의미: <청크1 뜻> + <청크2 뜻> + <청크3 뜻>
```

## 출력 형식 (문장)

```
**청킹**
| 청크 | 내용 | 의미 |
|---|---|---|
| S | <주어> | <뜻> |
| V | <동사구> | <뜻> |
| O/C | <목적어/보어> | <뜻> |
| M | <수식어구> | <뜻> |

순서대로 이어 읽기: <청크1> / <청크2> / <청크3> / <청크4>
```

## 예시 (단어)

- **unbelievable** → un- / believe / -able
  - 의미: 아닌(un-) + 믿다(believe) + 할 수 있는(-able) → "믿을 수 없는"

## 예시 (문장)

문장: "Despite the heavy rain, she decided to walk to the station because she didn't want to be late."

```
**청킹**
| 청크 | 내용 | 의미 |
|---|---|---|
| M (양보) | Despite the heavy rain | 폭우에도 불구하고 |
| S+V | she decided | 그녀는 결심했다 |
| O (to부정사) | to walk to the station | 역까지 걸어가기로 |
| M (이유절) | because she didn't want to be late | 늦고 싶지 않았기 때문에 |

순서대로 이어 읽기: "폭우에도 불구하고 / 그녀는 결심했다 / 역까지 걸어가기로 / 늦고 싶지 않아서"
```

## 주의

- 청크는 너무 잘게 쪼개지 않는다 (3~5개가 이상적). 너무 잘게 쪼개면 오히려 청킹의 목적(부담 감소)에 어긋난다.
