---
title: 대상자 및 고객 세그먼트를 동료와 채팅 비교
description: 동료 채팅을 사용하여 고객 그룹을 비교하고, 지나친 성장 기회를 찾고, 대상 트렌드를 추적하고, 통찰력을 빌드할 수 있는 대상으로 전환합니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# 대상 및 세그먼트 분석 개요

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Adobe CX Enterprise Coworker Chat을 사용하여 어떤 고객 그룹이 다르게 행동하고 어떻게 행동하는지 이해함으로써 가장 중요한 것에 집중할 수 있습니다. 채널, 기간 및 세그먼트를 나란히 비교하고, 시간이 지남에 따라 대상이 어떻게 변하는지를 추적한 다음, 찾은 내용을 빌드할 수 있는 대상으로 바꿉니다.

대상 및 세그먼트 분석은 동료 채팅의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**전문가:**, 비즈니스 사용자

## 사전 요구 사항

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기 또는 보고서 세트에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| [성능 비교](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 채널, 기간 또는 세그먼트 간에 지표를 나란히 비교합니다.<p>**샘플 프롬프트:** &quot;월별 채널별 수익 비교&quot;</p><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| [고객 그룹 비교](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 세그먼트 논리를 작성하지 않고도 다르게 동작하는 그룹을 표시합니다.<p>**비즈니스 사용자:**&#x200B;을 위한 추천</p><p>**샘플 프롬프트:**</p><ul><li>&quot;유료 소셜 방문자가 이메일과 다르게 전환됩니까?&quot;</li><li>&quot;매출액에서 신규 및 재방문자 비교&quot;</li></ul><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| 간과된 성장 기회 찾기 | 대상, 여정 및 채널을 탐색하여 전체 성능 수치에서 숨길 수 있는 기회를 식별합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;어느 대상이 평균 이상으로 전환하지만 트래픽이 거의 발생하지 않습니까?&quot;</li><li>&quot;전환율에 어떤 채널이 더 적게 사용됩니까?&quot;</li></ul> |
| [운영 추세 및 원인 분석](/help/chat/use-cases/workflows.md#data-insights) | 대상자, 데이터 세트 및 여정에 대한 내역 시계열 데이터를 쿼리하고 변경 사항을 발생시킨 원인을 식별합니다.<p>**관리자:**, 분석가</p><p>**샘플 프롬프트:** &quot;지난 90일 동안의 대상자 크기 트렌드 표시&quot;</p><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에서는 분석할 대상, 데이터 세트 또는 여정에 액세스해야 합니다.</p><p>자세한 내용은 동료 채팅 사용 사례의 [데이터 인사이트](/help/chat/use-cases/workflows.md#data-insights)를 참조하십시오.</p> |
| 대상자 크기 트렌드 추적 | 증가 또는 감소하는 대상자를 찾아 원인을 살펴봅니다.<p>**관리자:**, 분석가</p><p>**샘플 프롬프트:** &quot;이번 분기에 가장 빠르게 증가한 대상은 무엇입니까?&quot;</p><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에서는 추적하려는 대상에 대한 액세스 권한도 필요합니다.</p> |
| insight을 대상으로 가져오기 | insight에서 다시 시작하지 않고 빌드할 수 있는 대상으로 이동합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;Analysis Workspace에서 이 비교 열기&quot;</li><li>&quot;이 그룹에서 대상자 작성 지원&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에서는 Real-Time Customer Data Platform에 대한 액세스 권한과 대상을 만들 수 있는 권한도 필요합니다.</p> |

## 사용된 스킬

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| `cja`, `aa` | 성과 비교<br>고객 그룹 비교 |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | 성능 비교 |
| `operational-stats-causal-analysis` | 운영 트렌드 분석 및 원인<br>대상자 크기 트렌드 추적 |
| `audience-creation-flow` | insight을 대상으로 가져오기 |

## 더 나은 결과를 위한 팁

* 포함, 제외 또는 비교하려는 세그먼트, 대상, 채널 또는 장치를 지정합니다.
* 세그먼트 및 기타 구성 요소를 정확한 이름으로 참조합니다.
* 월별 매출액과 같이 비교할 지표 및 날짜 범위의 이름을 지정합니다.
* 한 그룹이 다른 그룹과 다르게 동작하는 이유를 알려면 기여 차원을 요청합니다.

## 다음 단계

* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* Coworker Chat에서 바로 대상자를 만들려면 [Experience Platform 상태 평가 및 Coworker를 사용하여 자연어로 대상자 만들기](/help/chat/use-cases/audiences/create-audience-from-natural-language.md)를 참조하십시오.
