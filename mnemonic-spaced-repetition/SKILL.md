---
name: mnemonic-spaced-repetition
description: Use to generate a Leitner-style spaced-repetition review schedule (1/3/7/14/30-day intervals) for a newly learned word, term, or sentence based on today's date, and to append/update entries in the user's vocab tracking file. Invoked at the end by vocab-word-memorize and vocab-sentence-memorize after the mnemonic card is created.
metadata:
  category: education
  technique: spaced-repetition-leitner
---

# 간격 반복 복습 스케줄 (Spaced Repetition / Leitner System)

## 개요

에빙하우스 망각곡선에 따르면 새로 학습한 정보는 시간이 지날수록 빠르게 잊혀지지만, 적절한 간격으로 복습하면 단기기억이 장기기억으로 전환된다. 이 스킬은 오늘 날짜를 기준으로 복습 일정을 계산하고, 단어장 파일에 진행 상태를 기록/갱신한다.

## 복습 간격 (기본값)

학습일로부터 **1일, 3일, 7일, 14일, 30일** 후에 복습한다. (라이트너 박스 1~5단계에 대응)

- 복습에 성공하면 다음 단계로 진행 (간격이 늘어남)
- 복습에 실패하면 1단계(1일 후)로 되돌아간다고 안내

## 절차

1. **오늘 날짜 확인**: 시스템에서 제공된 현재 날짜를 기준으로 사용한다.
2. **복습 날짜 계산**: 오늘 날짜 + 1일, +3일, +7일, +14일, +30일을 계산해 날짜(YYYY-MM-DD)로 표시한다.
3. **단어장 파일 갱신**:
   - 단어장 파일(기본 경로는 호출하는 스킬에서 지정)의 "복습 일정" 또는 "review schedule" 섹션/표에 새 항목을 추가한다.
   - 파일이 없으면 새로 만들고, 헤더(컬럼: 날짜 | 단어/문장 | 단계 | 상태)를 포함한 표를 생성한다.
   - 기존 항목이 있으면 맨 아래에 행을 추가한다 (append).
4. **출력**: 사용자에게 다음 복습일(1단계, 보통 내일)을 강조해서 알려준다.

## 출력 형식

```
**복습 스케줄 (Leitner)**
- 1차 복습: <오늘+1일> (1일 후)
- 2차 복습: <오늘+3일> (3일 후)
- 3차 복습: <오늘+7일> (7일 후)
- 4차 복습: <오늘+14일> (14일 후)
- 5차 복습: <오늘+30일> (30일 후)

다음 복습일: <1차 복습 날짜> — 이 날 다시 떠올려보세요!
```

## 단어장 파일 내 복습 표 형식

```markdown
## 복습 일정

| 등록일 | 단어/문장 | 1차(1d) | 2차(3d) | 3차(7d) | 4차(14d) | 5차(30d) | 상태 |
|---|---|---|---|---|---|---|---|
| 2026-06-10 | mirage | 2026-06-11 | 2026-06-13 | 2026-06-17 | 2026-06-24 | 2026-07-10 | 진행중 |
```

## 주의

- 날짜 계산은 정확해야 한다 (월말/연말 경계 주의).
- 사용자가 복습 결과(성공/실패)를 알려주면 "상태" 컬럼과 다음 단계 날짜를 갱신한다.
