---
title: 동료 채팅으로 콘텐츠에 대해 질문하기
description: 일반 언어부터 특정 언어까지 일반 언어로 콘텐츠에 대해 동료 채팅에 질문하고 분석가 전문 지식 없이도 정확한 Content Analytics 답변을 얻을 수 있습니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: b54085a497ca4bbf0003d5837d816206a4d40396
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 2%
---

# 콘텐츠에 대한 질문

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

Adobe CX Enterprise Coworker 채팅을 사용하여 Adobe Content Analytics에서 콘텐츠에 대한 정확한 답변을 얻을 수 있습니다. &quot;지난 분기에 가장 많은 매출을 올린 영웅 이미지는 무엇입니까?&quot;와 같은 특정 질문이나 &quot;어떤 콘텐츠를 우선 순위 지정해야 합니까?&quot;와 같은 일반적인 질문을 하십시오. 동료는 질문을 건전한 분석으로 바꿉니다.

동료는 Content Analytics 데이터가 구성되는 방식을 이해하고 숙련된 분석가가 적용할 수 있는 보고 규칙을 적용하므로 마케터와 다른 비즈니스 사용자는 깊이 있는 Content Analytics 전문 지식 없이도 신뢰할 수 있는 결과를 얻을 수 있습니다.

다른 콘텐츠 성능 사용 사례는 [콘텐츠 성능 개요](/help/chat/use-cases/data-insights/content-performance.md)를 참조하십시오.

**우수 사례:** 비즈니스 사용자, 분석가

## 사전 요구 사항

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

콘텐츠에 대해 질문하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics의 권한을 상속합니다.
* Content Analytics용으로 구성된 데이터 보기. Customer Journey Analytics 안내서에서 [Content Analytics 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/content-analytics/configuration/configuration)을 참조하십시오.

## 콘텐츠 질문하기

1. 동료에게 로그인합니다.

1. **[!UICONTROL 새 채팅]**&#x200B;을 선택하세요.

1. 텍스트 필드에서 콘텐츠에 대해 질문합니다. 예:

   **프롬프트**

   > 어떤 종류의 콘텐츠를 우선시해야 합니까?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   동료는 `analyze-content` 스킬을 사용하여 콘텐츠 질문에 답변합니다.

1. (조건부) 질문이 두 개 이상의 해석에 열려 있는 경우, 의미 있는 콘텐츠 유형, 채널 또는 날짜 범위와 같이 Coworker가 묻는 명확한 질문에 답하십시오.

1. 결과를 검토합니다.

1. (선택 사항) 동일한 대화에서 후속 질문을 하여 더 깊이 살펴보거나 Analysis Workspace에서 시각화를 열어 보다 수동 제어를 하십시오. [Customer Journey Analytics에서 분석](/help/chat/use-cases/data-insights/analytics-chat.md#analyze-in-customer-journey-analytics)을 참조하세요.

## 프롬프트 예

다음 표는 다양한 유형의 콘텐츠 질문에 대한 예제 프롬프트를 보여 줍니다. 이를 시작점으로 사용하여 나만의 콘텐츠에 맞게 조정하십시오.

| 질문 유형 | 프롬프트 예 |
| --- | --- |
| 광범위 또는 탐색적 | <ul><li>&quot;어떤 종류의 콘텐츠를 우선 순위 지정해야 합니까?&quot;</li><li>&quot;콘텐츠의 성과는 어떻습니까?&quot;</li></ul> |
| 속성-수준 | <ul><li>&quot;가장 성과가 좋은 이미지는 공통점이 무엇입니까?&quot;</li><li>&quot;가장 많은 참여를 유도하는 콘텐츠 특성은 무엇입니까?&quot;</li></ul> |
| 수익 및 전환 | <ul><li>&quot;어떤 영웅 이미지가 지난 분기에 가장 많은 매출을 올렸습니까?&quot;</li><li>&quot;이 배너에 얼마나 많은 수익이 연결되어 있습니까?&quot;</li></ul> |
| 채널 및 대상자 | <ul><li>&quot;유료 및 당사 사이트에서 어떤 크리에이티브 테마가 승리합니까?&quot;</li><li>&quot;처음 방문하는 사용자에게 적합한 이미지는 무엇입니까?&quot;</li></ul> |

## Coworker가 콘텐츠 질문에 답변하는 방법

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

동료는 다음 컨텍스트 및 보호 기능을 포함하여 `analyze-content` 스킬로 콘텐츠 질문에 답변합니다. 이 스킬은 `cja` 스킬과 쌍을 이루며 동일한 Customer Journey Analytics 도구를 통해 Customer Journey Analytics 데이터 보기에 대해 모든 쿼리를 실행합니다.

### 쿼리 기본값 및 명확한 질문

질문이 세부 사항을 생략하면 이 기술은 적절한 기본값을 적용합니다. 만약 그 기술이 당신이 무엇을 의미하는지 확실하지 않다면, 그것은 추측하는 대신 명확한 질문을 던진다.

### 자산 및 경험에 대한 지표 일치

<!-- FLAG: The table covers web and mobile content. Paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). Confirm with the PM how the skill handles paid media, then add a row or note. -->

Content Analytics은 자산과 경험이라는 두 가지 유형의 콘텐츠를 추적합니다. 각 지표에는 고유한 지표가 있습니다. 이 기술은 항상 지표를 사용자가 묻는 콘텐츠 유형과 연결합니다.

| 콘텐츠 유형 | 정의 | 스킬이 사용하는 지표 |
| --- | --- | --- |
| 자산 | 이미지와 같은 개별 콘텐츠 | 자산 보기, 자산 클릭 수, 자산 클릭스루 비율(CTR) |
| 경험 | 웹 페이지의 모든 텍스트 또는 모바일 앱의 텍스트, 자산 및 작업 호출의 조합입니다 | 경험 보기, 경험 클릭 수, 경험 클릭스루 비율(CTR) |

### Content Analytics 데이터 아키텍처

이 기술은 Content Analytics 데이터가 구성되는 방식을 이해합니다. 예:

* **경험 ID:** 특정 페이지에 대해 물으면 스킬은 해당 페이지를 식별하는 콘텐츠 경험 ID로 필터링합니다.
* **AI 생성 특성:** 각 자산 및 경험은 사진 스타일, 색상, 색조 및 설득 전략과 같은 특성으로 설명됩니다. 스킬은 이러한 속성을 사용하여 어떤 콘텐츠가 잘 수행되는지뿐만 아니라 콘텐츠가 잘 수행되는 이유를 설명합니다.

전체 구성 요소 목록은 Customer Journey Analytics 안내서의 [Content Analytics 구성 요소](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/content-analytics/report/components)를 참조하십시오.

### 기여도

스킬은 질문에 맞는 속성 모델을 선택합니다. 예를 들어 이미지 클릭에 대한 질문은 해당 이미지가 기여한 매출에 대한 질문과 다르게 답변됩니다. 자세한 내용은 Customer Journey Analytics 안내서의 [속성 모델](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models)을 참조하십시오.

### 일반적인 분석 및 워크플로

이 기술에는 다음과 같은 일반적인 콘텐츠 분석에 대한 지침이 포함되어 있습니다.

* 성과가 가장 좋은 에셋 또는 경험에 공통적으로 포함된 특성을 찾습니다.
* 콘텐츠 노출을 전환 및 매출에 연결.
* 웹, 모바일 및 유료 미디어 채널 간 콘텐츠 비교.
* 서로 다른 대상 및 세그먼트에 대해 작동하는 콘텐츠를 비교합니다.
* 과다 사용되거나 과소 사용되는 콘텐츠 식별.

### 시각화

이 스킬은 질문 및 데이터에 맞는 시각화를 선택하여 결과를 쉽게 읽고 공유할 수 있도록 합니다.

## 더 나은 결과를 위한 팁

* 무엇을 물어봐야 할지 확실하지 않다면 광범위하게 시작하세요. 동료는 일반적인 질문을 집중된 분석으로 바꿀 수 있고, 여기서 정교화할 수 있습니다.
* 원하는 에셋을 알고 있는 경우 이미지와 같은 개별 에셋을 의미하는지 아니면 페이지와 같은 전체 경험을 의미하는지 여부를 지정합니다.
* 분석할 지표 및 날짜 범위(예: 지난 분기 매출액)에 이름을 지정합니다.
* 비교할 세그먼트, 대상 또는 채널을 지정합니다.
* 콘텐츠의 성과가 좋은 이유를 알고 싶을 때 개별 파일이 아닌 이미지, 테마 또는 메시지와 같은 콘텐츠 속성에 대해 질문합니다.
* 항상 동일한 데이터 보기를 분석할 경우 선호하는 데이터 보기를 동료 채팅 메모리에 추가합니다. [메모리에 데이터 보기 또는 보고서 세트 환경 설정 추가](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory)를 참조하십시오.

## 다음 단계

* 콘텐츠 성능 사용 사례에 대한 자세한 내용은 [콘텐츠 성능 개요](/help/chat/use-cases/data-insights/content-performance.md)를 참조하십시오.
* Content Analytics에 대한 자세한 내용은 Customer Journey Analytics 안내서의 [Content Analytics 개요](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/content-analytics/content-analytics)를 참조하십시오.
* Coworker Chat를 사용한 데이터 분석 개요 및 모범 사례를 보려면 [Coworker Chat를 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
