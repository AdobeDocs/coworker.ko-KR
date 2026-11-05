---
title: Adobe Analytics 및 Customer Journey Analytics을 사용하여 근본 원인 분석
description: Adobe CX Enterprise Coworker을 사용하여 Adobe Analytics 및 CJA에서 지표 변경 사항을 조사하고, 기여하는 차원과 세그먼트를 식별하고, 가설을 테스트할 수 있습니다.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# [!DNL Adobe Analytics] 및 [!DNL Customer Journey Analytics]&#x200B;(으)로 근본 원인 분석

Adobe CX Enterprise Coworker 채팅 을 사용하여 Adobe Analytics 또는 Customer Journey Analytics(CJA)에서 지표가 변경된 이유를 조사합니다. 동료는 사용자가 지정하는 변경 사항을 분석하고 기여 차원 및 세그먼트를 표시하며 자연어를 사용하여 가설을 테스트하는 데 도움이 됩니다.

## 근본 원인 분석에 Customer Journey Analytics 데이터 사용

다음 비디오에서는 Coworker가 대화형 AI를 Customer Journey Analytics과 결합하는 방법을 보여 줍니다. 자연어로 질문하는 방법, 결과를 시각화하는 방법, 의미 있는 트렌드를 식별하는 방법, 수동 쿼리를 작성하지 않고도 성능을 이끄는 요인을 찾아내는 방법에 대해 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/3496857/?captions=kor&learn=on&enablevpops)

### 사전 요구 사항

시작하기 전에:

1. **동료 채팅에 액세스하고 Customer Journey Analytics에 연결합니다.** 조직에서 필요한 통합을 구성했는지 확인합니다.
1. **분석할 CJA 데이터 보기에 대한 보기 액세스 권한이 있습니다.** 동료는 사용 가능한 데이터 보기와 구성 요소만 사용할 수 있습니다.
1. **관련 지표와 차원을 포함하는 데이터 보기를 선택하십시오.** 여러 데이터 보기에 액세스할 수 있는 경우 Coworker에서 사용할 데이터 보기의 이름을 지정합니다.
1. **조사할 변경 내용을 식별합니다.** 지표, 날짜 범위 및 비교 기간을 지정합니다. 분석에 초점을 맞추기 위한 차원, 세그먼트 또는 가설을 제공할 수도 있습니다.

### Customer Journey Analytics에 대한 샘플 프롬프트

데이터 보기에서 대괄호로 묶인 텍스트를 구성 요소 이름 및 기간으로 바꿉니다.

* **[데이터 보기 이름]** 데이터 보기에서 **[비교 날짜 범위]**&#x200B;와(과) 비교하여 **[날짜 범위]** 동안 **[지표]**&#x200B;이(가) 변경된 이유는 무엇입니까? **[차원]**&#x200B;별로 변경 내용을 분류하고 가장 많은 기여를 한 세그먼트를 표시합니다.
* **[데이터 보기 이름]** 데이터 보기에서 **[차원 또는 세그먼트]**&#x200B;이(가) **[날짜 범위 A]**&#x200B;에서 **[날짜 범위 B]**&#x200B;까지 **[지표]** 감소에 기여했습니까? 두 기간의 값을 비교하고 변경된 사항을 설명합니다.
* **[데이터 보기 이름]** 데이터 보기에서 **[날짜 범위]** 동안 **[세그먼트 A]** 및 **[세그먼트 B]**&#x200B;에 대한 **[지표]**&#x200B;을(를) 비교합니다. 어떤 차원이 차이점에 가장 큰 기여를 했습니까?
* **[데이터 보기 이름]** 데이터 보기에서 다음 가설을 테스트합니다. **[가설을 설명]**. **[날짜 범위]**&#x200B;에 대해 **[지표]**&#x200B;을(를) 분석하고 이를 지원하거나 지원하지 않는 차원 또는 세그먼트를 표시합니다.

## 근본 원인 분석에 Adobe Analytics 데이터 사용

동료는 Adobe Analytics 보고서 세트에서 지표가 변경된 이유를 조사할 수 있습니다. `aa-root-cause-analysis` 스킬을 사용하여 사용자가 지정한 변경 내용을 분석하고 그 변경 내용에 기여한 차원과 세그먼트를 식별합니다.

### 사전 요구 사항

시작하기 전에:

1. **동료 채팅에 액세스하고 Adobe Analytics에 연결합니다.** 동료에서 **사용자 지정 > 통합**(으)로 이동하여 `aa-mcp` 통합이 나열되고 연결되어 있는지 확인하십시오. 사용할 수 없는 경우 관리자에게 조직의 설정을 확인하도록 요청하십시오. 설치 지침은 [동료 채팅을 사용하여 데이터 분석 시작](https://experienceleague.adobe.com/ko/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)을 참조하세요.
1. **분석할 Adobe Analytics 보고서 세트에 대한 보기 액세스 권한이 있습니다.** Coworker는 Adobe Analytics 권한을 상속하며 Analysis Workspace에서 사용할 수 있는 보고서 세트와 구성 요소만 사용할 수 있습니다.
1. **관련 데이터가 포함된 보고서 세트를 선택하십시오.** 여러 보고서 세트에 액세스할 수 있는 경우 Coworker에서 사용할 보고서 세트의 이름을 지정합니다.
1. **조사할 변경 내용을 식별합니다.** 지표 및 기간을 지정합니다. 보다 집중적인 분석을 위해 비교 기간, 관련 차원 또는 세그먼트, Coworker에서 테스트할 모든 가설을 포함하십시오.

### Adobe Analytics에 대한 샘플 프롬프트

대괄호로 묶인 텍스트를 보고서 세트의 구성 요소 이름 및 기간으로 바꿉니다.

* **[보고서 세트 이름]** 보고서 세트에서 **[비교 날짜 범위]**&#x200B;와(과) 비교하여 **[날짜 범위]** 동안 **[지표]**&#x200B;이(가) 변경된 이유는 무엇입니까? **[차원]**&#x200B;별로 변경 내용을 분류하고 가장 많은 기여를 한 세그먼트를 표시합니다.
* **[보고서 세트 이름]** 보고서 세트에서 **[차원 또는 세그먼트]**&#x200B;이(가) **[날짜 범위 A]**&#x200B;에서 **[날짜 범위 B]**&#x200B;까지 **[지표]** 감소에 기여했습니까? 두 기간의 값을 비교하고 변경된 사항을 설명합니다.
* **[보고서 세트 이름]** 보고서 세트에서 **[날짜 범위]** 동안 **[세그먼트 A]** 및 **[세그먼트 B]**&#x200B;에 대한 **[지표]**&#x200B;을(를) 비교합니다. 어떤 차원이 차이점에 가장 큰 기여를 했습니까?

## 관련 리소스

* [Adobe CX Enterprise Coworker Chat으로 데이터 분석](https://experienceleague.adobe.com/ko/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [동료 채팅을 사용하여 데이터 분석 시작](https://experienceleague.adobe.com/ko/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
