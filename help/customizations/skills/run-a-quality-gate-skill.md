---
title: 동료의 품질 게이트 스킬 구축 및 실행
description: 사용자 지정 동료 기술을 사용하여 배포 전에 제외 목록, 빈도 제한, 이름 지정 표준에 대해 대상자 활성화를 자동으로 확인하는 방법을 알아봅니다.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# 사용자 정의 AI 스킬을 사용하여 품질 게이트 스킬 구축 및 실행

마케팅 팀은 대상자가 올바르게 활성화되도록 규칙 및 거버넌스 프로세스를 사용합니다. 대상으로 대상을 시작하기 전에 팀은 제외 목록, 빈도 제한, 동의 요구 사항 및 이름 지정 규칙을 확인해야 하는 경우가 많습니다.
 
문제는 이러한 점검이 종종 부족 지식과 수동 검토에 의존한다는 것입니다. 과정들이 사람들의 머릿속에 살아 있을 때, 실수들이 일어날 수 있습니다.

이 비디오에서는 사용자 정의 동료 스킬이 다운스트림으로 이동하기 전에 조직의 활성화 표준에 대해 대상을 자동으로 확인하여 활성화 게이트 역할을 수행하는 방법에 대해 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/3503162/?learn=on&enablevpops)

## 샘플 활성화 품질 게이트 스킬
 
프롬프트를 Coworker에 붙여 넣어 재사용 가능한 **활성화 품질 게이트** 스킬을 만들 수 있습니다. 동료의 스킬 작성 기능은 프롬프트를 **자신의 환경** 내에 저장된 스킬로 변환합니다. 비디오 데모를 기반으로 한 샘플은 다음과 같습니다.
 
세 가지 거버넌스 게이트에 대해 **자체 합격/불합격 표준**&#x200B;을(를) 정의하는 것이 중요합니다.
 
1. 제외 / 동의
2. 빈도 상한
3. 명명 규칙
 
그 틀은 모든 사람들에게 동일하게 유지된다. 조직의 표준에 맞게 **`[...]`**(으)로 표시된 섹션을 사용자 지정합니다.

## 기본 프롬프트

> **활성화 품질 게이트라는 스킬로 저장하십시오.**

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## 게이트 1: 억제 / 동의
 
> 조직의 비표시 및 동의 요구 사항과 일치하도록 이 섹션을 편집합니다.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## 게이트 2: 주파수 상한

> 조직의 배달 빈도 요구 사항과 일치하도록 이 섹션을 편집합니다.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## 게이트 3: 명명 규칙
 
> 조직의 대상 이름 지정 규칙과 일치하도록 이 섹션을 편집합니다.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## 지침

### &#x200B;1. 괄호로 묶인 섹션만 사용자 정의

**`[...]`**&#x200B;에 포함된 섹션만 업데이트합니다.
 
이 섹션에서는 조직의 특정 거버넌스 표준을 정의합니다.
 
다른 모든 항목은 변경되지 않은 상태로 유지되어야 합니다.

- 대상 해상도
- 게이트 평가
- 스코어카드 렌더링
- 평결 논리


### &#x200B;2. 사전 요구 사항 확인
 
이 스킬은 다음에 따라 다릅니다.
 
- 지식 그래프 액세스
- 대상자 탐색
- 대상 검색
- 비표시 목록 검색
- 시각적 아티팩트 지원
- 경고 배너
- 지표 카드
- 데이터 테이블 렌더링

고객 환경에서 이러한 기능을 사용할 수 없는 경우 스킬을 설계된 대로 실행할 수 없습니다.

### &#x200B;3. 읽기 전용 스킬 유지

이 기술은 항상 읽기 전용으로 유지되어야 합니다.

스킬을 활성화 워크플로와 혼동하지 않도록 프롬프트에 이 요구 사항을 명시적으로 포함하십시오.

활성화 품질 게이트는 활성화 준비 상태만 평가합니다. 대상을 활성화하거나 구성을 수정하거나 데이터를 복사하지 **않습니다**.
