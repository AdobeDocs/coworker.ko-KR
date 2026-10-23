---
title: 동료 채팅으로 고객 여정 및 드롭오프 분석
description: 동료 채팅을 사용하여 단계를 만들고, 고객이 중단되는 지점을 찾고, 전환 감소를 진단하고, 분석 데이터에서 여러 기간에 걸친 여정을 비교할 수 있습니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 2%
---

# 여정 분석 개요

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Adobe CX Enterprise Coworker Chat을 사용하여 고객이 여정에서 전환으로 드롭되는 위치와 그 이유를 채널, 장치 및 세그먼트에서 찾을 수 있습니다. 여정을 일반 언어로 설명하고 동료 채팅은 funnel을 빌드하고 각 단계의 드롭다운을 표시하며 원인을 조사하는 데 도움이 됩니다.

여정 분석은 Coworker Chat의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**전문가:**, 비즈니스 사용자

## 사전 요구 사항

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기 또는 보고서 세트에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| [Customer Journey Analytics 및 Adobe Analytics 데이터 분석](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Customer Journey Analytics 및 Adobe Analytics 데이터 분석](../../assets/coworker-funnel-response-card.png)</p> | 데이터 보기 또는 보고서 세트에 대한 자연어 질문에 답변하고, 유입 경로 및 기타 시각화를 구축하며, 고객이 이탈하는 지점을 찾습니다. 추가적인 분석을 위해 Analysis Workspace에서 모든 시각화를 열 수 있습니다.<p>**샘플 프롬프트:** &quot;최근 30일 동안의 페이지 보기 표시&quot;</p><p>자세한 내용은 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.</p> |
| [고객이 드롭오프하는 위치 찾기](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 일반 언어 질문에서 funnel을 빌드하고 가장 큰 누출 순위를 매기고 다음 단계를 제안합니다.<p>**비즈니스 사용자:**&#x200B;을 위한 추천</p><p>**샘플 프롬프트:**</p><ul><li>&quot;구매하는 도중에 사람들이 줄어드는 곳은 어디입니까?&quot;</li><li>&quot;체크아웃 funnel 안내&quot;</li></ul><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| 전환 감소 진단 | 고객이 드롭아웃된 위치를 조사하고 변경에 기여한 사항을 평가합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;지난 주에 전환율이 떨어진 이유는 무엇입니까?&quot;</li><li>&quot;사이트 변경 후 고객이 중도 하차한 곳은 어디입니까?&quot;</li></ul> |
| 드롭오프의 원인 파악 | 규칙을 해제하면 한 번에 하나씩 채널, 장치 또는 세그먼트를 문제 이면으로 분리하게 됩니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;모바일이나 데스크탑에서 장바구니 포기가 더 심합니까?&quot;</li><li>&quot;장바구니와 구매 중 어느 채널이 가장 많이 누출됩니까?&quot;</li></ul> |
| 기간 간 여정 비교 | 배송한 변경 사항이 funnel을 이동했는지 여부를 단계별로 표시합니다.<p>**비즈니스 사용자:**&#x200B;을 위한 추천</p><p>**샘플 프롬프트:**</p><ul><li>&quot;이번 분기와 마지막 체크아웃 전환 비교&quot;</li><li>&quot;재디자인 후 funnel은 어떻게 변경되었습니까?&quot;</li></ul> |

## 예: 고객이 드롭오프하는 위치 찾기

첫 번째 질문부터 추천까지의 전체 예제 대화에 대해서는 [예제: 고객이 드롭오프하는 위치 찾기](/help/chat/use-cases/data-insights/analytics-chat.md#example-find-where-customers-drop-off)를 Coworker Chat를 사용하여 데이터 분석 시작하기를 참조하십시오.

## 사용된 스킬

<!-- FLAG: Confidence: High for `cja` and `aa` (the Skills and limitations table lists funnel and fallout analysis and side-by-side comparison of time periods). Medium for the root cause analysis skills: workflows.md maps the prompt "Why did conversions drop last week?" to them, but the mapping to the slide rows "Diagnose conversion declines" and "Isolate the cause of a drop-off" is inferred. Confirm with the PM. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| `cja`, `aa` | Customer Journey Analytics 및 Adobe Analytics 데이터 분석<br>고객이 중단되는 위치 찾기<br>기간 간 여정 비교 |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | 전환 감소 진단<br>드롭오프의 원인 파악 |

## 더 나은 결과를 위한 팁

<!-- FLAG: Confidence: High, except the first bullet (Medium), which moved here from Prerequisites and is inferred from how funnel prompts work. The rest are adapted from the best practices in analytics-overview.md. -->

* 제품 페이지, 장바구니, 체크아웃 및 구매와 같이 분석할 여정 단계의 이름을 지정합니다.
* 분석할 차원, 지표 및 날짜 범위의 이름을 지정하고 정확한 이름으로 구성 요소를 참조합니다.
* 원하는 경우 funnel 또는 폴아웃 시각화를 요청하십시오.
* 포함하거나 제외하거나 비교할 세그먼트, 채널 또는 장치를 지정합니다.
* 최근 사이트 변경과 같이 이미 가지고 있는 가설을 언급하여 Coworker Chat이 이를 검증하거나 배제할 수 있도록 하십시오.
* 동료 채팅에서 후속 질문을 제안하려면 권장되는 다음 단계를 요청하십시오.
* 더 많은 수동 제어를 원하는 경우 Analysis Workspace에서 모든 시각화를 엽니다. [Analysis Workspace에서 시각화 열기](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace)를 참조하십시오.

## 다음 단계

* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* 동료 채팅을 설정하고 작업 예제를 보려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
