---
title: 동료 채팅으로 마케팅 영향 및 속성 측정
description: Coworker Chat 을 사용하여 각 채널의 증분 영향을 측정하고, 어디에 지출이 누적되는지 찾고, 가정 예산 시나리오를 작성하고, 마케팅 모델 품질을 확인합니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# 마케팅 측정 및 속성 개요

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Adobe CX Enterprise Coworker Chat을 사용하여 모든 마케팅 채널 및 캠페인의 증분 영향을 이해함으로써 ROI를 최적화하기 위해 지출을 할당할 수 있습니다. 채널을 함께 사용하는 방법, 추가 지출이 지급을 중단하는 위치 및 커밋하기 전에 다양한 예산 배부를 비교하는 방법을 확인하십시오.

마케팅 측정 및 기여도 분석은 Coworker Chat의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**전문가:**, 비즈니스 사용자

## 사전 요구 사항

<!-- FLAG: Confidence: High for the shared bullets (sourced from analytics-chat.md and the Skills and limitations table). They're confirmed for Measure campaign performance only; whether the marketing mix modeling use cases also need a data view or report suite connection is unknown. Low for the "Additional prerequisite" notes on the four marketing mix modeling rows in the Use cases table: incremental impact, response curves, budget scenarios, and model retraining describe a marketing mix model, but no source names the product or data that these use cases need. It could be Adobe Mix Modeler or Marketing Campaign Analytics (listed as an implementation path in implementation-guide.md). Confirm with the PM before publishing. -->

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기 또는 보고서 세트에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| 각 채널의 점진적 영향 파악 | 각 채널의 증분 값, 채널이 서로 증폭되는 방법 및 외부 요인의 역할을 보여줍니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;가장 많은 증분 전환을 유도한 채널은 무엇입니까?&quot;</li><li>&quot;유료 검색과 디스플레이는 어떻게 서로를 증폭합니까?&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 훈련된 마케팅 측정 모델도 필요합니다. *[제품 및 설치 요구 사항을 확인해야 합니다.]*</p> |
| 지출이 집중되기 시작하는 위치 찾기<p>![지출이 누적되기 시작하는 위치 찾기](assets/marketing-measurement.png)</p> | 추가 지출이 성과를 중단하는 위치를 나타내는 응답 곡선을 표시합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;유료 검색 지출은 어디에서 채화됩니까?&quot;</li><li>&quot;각 채널에 대한 응답 곡선 표시&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 훈련된 마케팅 측정 모델도 필요합니다. *[제품 및 설치 요구 사항을 확인해야 합니다.]*</p> |
| 가정 예산 시나리오 작성 | 할당 옵션을 나란히 비교하여 계획 결정을 지원합니다.<p>**비즈니스 사용자:**&#x200B;을 위한 추천</p><p>**샘플 프롬프트:**</p><ul><li>&quot;다음 분기에 대한 예산 시나리오 작성&quot;</li><li>&quot;지출의 10%를 디스플레이에서 검색으로 전환하면 어떻게 됩니까?&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 훈련된 마케팅 측정 모델도 필요합니다. *[제품 및 설치 요구 사항을 확인해야 합니다.]*</p> |
| 모델 품질 및 재교육 시기 확인 | 모델 품질, 교육 세부 정보 및 채점 지표를 검사하여 답을 신뢰할 수 있는 정도를 파악합니다.<p>**우수 사례:** 분석가</p><p>**샘플 프롬프트:**</p><ul><li>&quot;이 모델에 필요한 다른 요소가 있습니까?&quot;</li><li>&quot;이 모델을 재교육해야 합니까?&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 훈련된 마케팅 측정 모델도 필요합니다. *[제품 및 설치 요구 사항을 확인해야 합니다.]*</p> |
| [캠페인 성과 측정](/help/chat/use-cases/workflows.md#data-insights) | 주어진 기간 동안 캠페인, 채널 및 웹 속성을 수행하는 방법을 확인하십시오.<p>**샘플 프롬프트:** &quot;지난 달 Acrobat 웹 캠페인의 성능은 어떻습니까?&quot;</p><p>자세한 내용은 동료 채팅 사용 사례의 [데이터 인사이트](/help/chat/use-cases/workflows.md#data-insights)를 참조하십시오.</p> |

## 사용된 스킬

<!-- FLAG: Confidence: High for Measure campaign performance (workflows.md lists `cja`, `aa`, `dx-api`, and `knowledge-graph` for "Campaign performance"). `dx-api` and `knowledge-graph` aren't in the Skills and limitations table on analytics-overview.md. Low for the other four use cases: no source names their skills. Get the skill IDs from the PM, replace the placeholder row, and add the skills to the Skills and limitations table. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| `cja`, `aa`, `dx-api`, `knowledge-graph` | 캠페인 성과 측정 |
| *[확인할 스킬]* | 각 채널의 점진적 영향 살펴보기<br>지출이 누적되는 위치를 찾기<br>가상 예산 시나리오 구축<br>모델 품질 및 재교육 시기 확인 |

## 더 나은 결과를 위한 팁

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the sample prompts. -->

* 분석할 채널, 캠페인 및 날짜 범위에 이름을 지정합니다.
* 함께 작동하는 두 채널과 같이 이미 가지고 있는 가설을 언급하여 Coworker Chat이 이를 검증하거나 배제할 수 있도록 하십시오.
* 지출의 10%를 한 채널에서 다른 채널로 이동하는 것과 같은 what-if 시나리오를 작성할 때 테스트할 특정 예산 이동을 기술합니다.

## 다음 단계

* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* 동료 채팅을 설정하고 작업 예제를 보려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
