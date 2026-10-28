---
title: 동료 채팅을 사용하여 콘텐츠 및 Creative 성과 분석
description: 동료의 채팅 을 사용하여 가장 성과가 좋은 콘텐츠의 공통점을 찾고, 매출이 고객이 볼 수 있는 이미지에 기여하며, 채널 및 대상 간의 창의성을 비교할 수 있습니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%
---

# 컨텐츠 성능 개요

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Adobe CX Enterprise Coworker 채팅을 사용하여 각 에셋의 속성까지, 성과가 좋은 콘텐츠와 그 이유를 파악하여 효과가 있는 콘텐츠에 투자할 수 있습니다. 클릭을 통해 채널 및 대상 전반에서 참여 및 매출을 유도하는 이미지, 메시지 및 테마를 확인할 수 있는 파일을 살펴보십시오.

콘텐츠 성능은 Coworker Chat의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**비즈니스 사용자:**&#x200B;을 위한 추천

## 사전 요구 사항

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The SME confirmed (October 2026) that the skill doesn't support paid media yet, so the paid channel use case was rewritten for web and mobile. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, consider restoring paid channels to that row with an "Additional prerequisite" note: paid media needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads, and comparing paid creative with on-site revenue needs custom tracking-key mapping (config/paid-media.md in analytics-platform.en). -->

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기 또는 보고서 세트에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다.
* Content Analytics용으로 구성된 데이터 보기. Customer Journey Analytics 안내서에서 [Content Analytics 구성](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration)을 참조하십시오.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| 우수성이 검증된 콘텐츠의 공통점 찾기<p>![공통적으로 가장 성과가 좋은 콘텐츠 찾기](assets/content-performance.png)</p> | 클릭된 파일뿐만 아니라 속성 수준에서 작동하는 이미지 및 메시징을 표시합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;가장 성과가 좋은 이미지는 공통점이 무엇입니까?&quot;</li><li>&quot;가장 많은 참여를 유도하는 콘텐츠 특성은 무엇입니까?&quot;</li></ul> |
| 고객에게 표시되는 컨텐츠에 매출을 연결합니다. | 이미지 노출을 알고리즘 속성 을 통해 매출, 전환 및 참여에 연결합니다.<p>**전문가:**, 비즈니스 사용자</p><p>**샘플 프롬프트:**</p><ul><li>&quot;지난 분기에 가장 많은 매출을 올린 이미지는 무엇입니까?&quot;</li><li>&quot;https://www.example.com/images/spring-sale.jpg에 있는 이미지에 연결된 매출은 얼마나 됩니까?&quot;</li></ul> |
| 웹 및 모바일에서 크리에이티브 비교 | 한 보기에서 사이트 및 모바일 앱의 우승 비주얼과 테마를 보여 줍니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;모바일 앱과 사이트에서 어떤 크리에이티브 테마가 우수합니까?&quot;</li><li>&quot;모바일 앱과 사이트의 이미지 성능 비교&quot;</li></ul> |
| 각 대상을 움직이는 시각적 개체 파악 | 개인화 및 Creative Brief를 안내하기 위해 각 대상자에게 작동하는 시각적 개체를 표시합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;각 세그먼트에 가장 적합한 비주얼은 무엇입니까?&quot;</li><li>&quot;처음 방문하는 사용자에게 적합한 이미지는 무엇입니까?&quot;</li></ul> |

## 사용된 스킬

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| `cja`,`analyze-content` <br/>(제한된 가용성) | 가장 성과가 좋은 콘텐츠의 공통점을 찾습니다<br>고객이 볼 수 있는 콘텐츠에 대한 매출 특성<br>웹과 모바일에서 크리에이티브 비교<br>각 대상자를 움직이는 시각적 요소 파악<p>자세한 내용은 [콘텐츠에 대해 질문하기](/help/chat/use-cases/data-insights/ask-content-questions.md)를 참조하세요.</p> |

## 더 나은 결과를 위한 팁

<!-- FLAG: Confidence: High for the first bullet (SME feedback, October 2026). Medium for the rest: the second and third bullets are adapted from the best practices in analytics-overview.md, and the fourth bullet is inferred from the row descriptions. -->

* 특정 이미지에 대해 물으면 해당 URL 또는 에셋 ID를 포함하십시오. 동료는 대표 이미지나 배너와 같이 페이지에서 자신의 역할로 이미지를 식별할 수 없습니다.
* 분석할 지표 및 날짜 범위(예: 지난 분기 매출액)에 이름을 지정합니다.
* 비교할 세그먼트, 대상 또는 채널을 지정합니다.
* 콘텐츠의 성과가 좋은 이유를 알고 싶을 때 개별 파일이 아닌 이미지, 테마 또는 메시지와 같은 콘텐츠 속성에 대해 질문합니다.

## 다음 단계

* Coworker가 콘텐츠 질문에 답변하는 방법에 대해 알아보려면 [콘텐츠에 대해 질문하기](/help/chat/use-cases/data-insights/ask-content-questions.md)(제한된 가용성)를 참조하십시오.
* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* 동료 채팅을 설정하고 작업 예제를 보려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
