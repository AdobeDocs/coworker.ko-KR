---
title: 동료 채팅을 사용하여 Analytics 데이터의 유효성 검사 및 관리
description: 구현을 계획하고, 체크리스트에서 추적하고, Coworker Chat을 사용하여 Adobe Analytics, Customer Journey Analytics 및 Experience Platform 데이터의 유효성을 검사합니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%
---

# 데이터 거버넌스 및 유효성 검사 개요

Adobe CX Enterprise Coworker Chat을 사용하여 Analytics 구현을 설정, 마이그레이션 및 관리하고 모든 답변 뒤의 데이터를 신뢰할 수 있도록 하십시오. 동료는 구현을 계획하고, 해당 계획을 팀이 추적할 수 있는 체크리스트로 전환하며, 데이터가 수집된 후 유효성을 검사할 수 있습니다.

데이터 거버넌스 및 유효성 검사는 공동 작업자 채팅의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**관리자:** 추천

## 구현 워크플로의 결합 방식

이 페이지의 사용 사례는 3단계 워크플로(선택 사항)를 따릅니다. 모든 스테이지를 단독으로 사용할 수 있습니다. 예를 들어 계획 또는 체크리스트를 먼저 생성하지 않고 데이터를 검증할 수 있습니다.

1. **계획:** 개인화된 주문 구현 또는 업그레이드 계획을 가져옵니다. [동료와 함께 구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)을 참조하세요.
1. **구현:** 계획을 팀에서 할당 및 추적할 수 있는 Coworker Projects의 체크리스트로 전환합니다. [동료 프로젝트로 구현 검사 목록 생성](/help/chat/use-cases/data-insights/intelligent-checklist.md)을 참조하십시오.
1. **유효성 검사:** 데이터가 올바르게 구성 및 수집되었는지 확인하십시오. [사용 사례](#use-cases) 표에서 유효성 검사 사용 사례를 참조하십시오.

## 사전 요구 사항

<!-- FLAG: Confidence: Medium for the shared bullets. They differ from the other domain pages on purpose: planning doesn't query your data, and Experience Platform validation uses Experience Platform datasets rather than data views or report suites. The permission inheritance for Experience Platform is inferred. High for the "Additional prerequisite" notes in the Use cases table, which are sourced from the "Before you begin" section of each linked article. Some of those articles flag their own prerequisites as unconfirmed (implementation-guide.md, intelligent-checklist.md, streaming-media-validation.md), so verify those rows when those flags are resolved. Validate dataset quality for Customer Journey Analytics is a video page with no stated prerequisites, so it isn't listed. -->

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* 동료 채팅에 액세스합니다. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 유효성을 검사할 데이터에 대한 액세스 권한을 봅니다. 동료 채팅은 연결된 Adobe 애플리케이션에서 권한을 상속합니다.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| [구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![구현 계획](../../assets/ui-guide-6.png)</p> | Edge을 구현하거나, Adobe Analytics에서 업그레이드하거나, Content Analytics, Marketing Campaign Analytics 또는 Customer Journey Analytics에서의 스트리밍 미디어 컬렉션을 설정하기 위한 개인화된 단계별 플랜을 만듭니다. 계획에는 소유자, 작업량 예상, 종속성 및 유효성 검사 단계 등의 세부 사항이 포함됩니다.<p>**샘플 프롬프트:** &quot;Customer Journey Analytics 구현을 계획하는 데 도움&quot;</p><p>**추가 필수 구성 요소:** 이 사용 사례에서는 [일반 필수 구성 요소](#prerequisites) 외에 사용자에게 적용되는 구현 경로와 라이선스 상태 또는 계획된 데이터 수집 경로와 같은 현재 환경에 대한 기본 세부 정보를 알고 있어야 합니다.</p><p>자세한 내용은 [Coworker로 구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)을 참조하세요.</p> |
| [구현 검사 목록 생성](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![구현 검사 목록 생성](../../assets/data-validation-aa-cja/date-detail.png)</p> <p>실험</p> | Customer Journey Analytics 구현 계획을 Coworker Projects의 체크리스트로 전환하여 팀이 단계를 할당하고 상태를 추적하고 승인 게이트를 추가할 수 있습니다.<p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에, 이 사용 사례에는 완성된 구현 안내서 대화와 조직의 Coworker 프로젝트에 대한 액세스 권한도 필요합니다.</p><p>자세한 내용은 [Coworker 프로젝트를 사용하여 구현 검사 목록 생성](/help/chat/use-cases/data-insights/intelligent-checklist.md)을 참조하십시오.</p> |
| [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터 유효성 검사](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Adobe Analytics 보고서 세트와 Customer Journey Analytics 데이터 보기 간의 차원, 지표 및 트렌드를 비교하고, 불일치에 플래그를 지정한 다음, 업그레이드를 지원하는 수정 사항을 권장합니다.<p>**관리자:**, 분석가</p><p>**샘플 프롬프트:**</p><ul><li>&quot;AA 보고서 세트를 내 CJA 데이터 보기와 비교&quot;</li><li>&quot;AA와 CJA 간에 일치하지 않는 지표는 무엇입니까?&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에, 이 사용 사례에는 유효성을 검사할 Adobe Analytics 보고서 세트와 동일한 데이터를 포함하는 Customer Journey Analytics 데이터 보기도 필요합니다.</p><p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)를 참조하십시오.</p> |
| [스트리밍 미디어 구현의 유효성 검사](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![스트리밍 미디어 구현의 유효성 검사](../../assets/ui-guide-8.png)</p> <p>실험</p> | 데이터 스트림, 스키마, 데이터 세트, 데이터 보기 및 세션 데이터를 확인하여 Streaming Media 추적이 구성되어 있고 데이터가 올바르게 수집되는지 확인합니다.<p>**샘플 프롬프트:** &quot;Streaming Media 구현은 전체적으로 얼마나 정상입니까?&quot;</p><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에서는 조직의 Experience Platform 및 Customer Journey Analytics 데이터가 Coworker에 연결되어 있어야 합니다. 일부 유효성 검사 모드의 경우 비디오 세션 ID나 로그 파일도 필요합니다.</p><p>자세한 내용은 [Coworker를 사용하여 Streaming Media 구현 확인](/help/chat/use-cases/data-insights/streaming-media-validation.md)을 참조하십시오.</p> |
| [Customer Journey Analytics에 대한 데이터 세트 품질 확인](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Customer Journey Analytics에 대한 데이터 세트 품질 확인](../../assets/data-validation-aep/dataset-validation.png)</p> <p>실험(다음 주)</p> | Customer Journey Analytics 보고를 제공하는 데이터 세트를 식별한 다음 스키마, ID 품질 및 필드 품질을 검사하여 대시보드를 작성하기 전에 문제를 해결할 수 있습니다.<p>자세한 내용은 [Coworker의 데이터 유효성 검사 기술을 사용하여 Customer Journey Analytics 데이터 유효성 검사](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)를 참조하십시오.</p> |
| [Experience Platform으로 수집 후 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Experience Platform으로 수집 후 데이터 유효성 검사](../../assets/data-validation-aep/null-values.png)</p> | Experience Platform 데이터 세트 및 필드에 대한 통계 및 시맨틱 검사를 실행하여 새로운 구현 후 또는 지속적인 데이터 관리의 일부로 잘못된 값 또는 매핑 문제와 같은 데이터 품질 문제를 찾습니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;데이터 집합 [데이터 집합 이름]의 유효성 검사&quot;</li><li>&quot;데이터 집합 [데이터 집합 이름]에서 [데이터 필드]의 유효성 검사&quot;</li></ul><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 유효성을 검사할 데이터 집합의 이름이나 ID도 필요합니다. 선택적으로, 확인할 특정 필드의 이름을 제공할 수 있습니다.</p><p>자세한 내용은 [Coworker를 사용하여 Experience Platform 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aep.md)를 참조하십시오.</p> |
| [데이터 인사이트 가속화](/help/chat/use-cases/data-insights/accelerate-data-insights.md) | Coworker가 구현을 계획하고, 지원되는 작업을 실행하고, 웹 사이트 참여 데이터를 분석할 준비가 될 때까지 Adobe Experience Manager, Experience Platform, Web SDK 및 Customer Journey Analytics에서 제품 및 개발 단계를 안내하는 방법을 비디오에 표시합니다.<p>자세한 내용은 [Coworker, AEM 및 CJA을 사용하여 데이터 인사이트 가속화](/help/chat/use-cases/data-insights/accelerate-data-insights.md)를 참조하십시오.</p> |

## 사용된 스킬

<!-- FLAG: Confidence: High for `aa-cja-validation` (listed in the Skills and limitations table and in workflows.md). Medium for `data-validation`: workflows.md lists it, but with a TODO to confirm the skill ID with engineering. Medium for the implementation guide skills and the Streaming Media Validation skill: the articles name them but don't give technical skill IDs, so they're listed by display name. Only `aa-cja-validation` currently appears in the Skills and limitations table on analytics-overview.md. Add the others there so the link below covers them. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| 구현 안내서 기술(Customer Journey Analytics, Adobe Analytics에서 Customer Journey Analytics으로 업그레이드, Content Analytics, Marketing Campaign Analytics 및 스트리밍 미디어에 대해 각각 하나씩) | 구현 계획 |
| `aa-cja-validation` | Adobe Analytics에서 Customer Journey Analytics으로 업그레이드 시 데이터 유효성 검사 |
| 스트리밍 미디어 유효성 검사 스킬 | 스트리밍 미디어 구현의 유효성 검사 |
| 데이터 유효성 검사 스킬(`data-validation`) | Customer Journey Analytics에 대한 데이터 세트 품질 유효성 검사<br>Experience Platform에 수집 후 데이터 유효성 검사 |

## 더 나은 결과를 위한 팁

* 데이터의 유효성을 검사할 때 비교할 특정 보고서 세트 및 데이터 보기의 이름을 지정합니다.
* 유효성 검사 결과를 자신의 변경 사항에 대한 지침으로 사용합니다. 스트리밍 미디어 유효성 검사 및 데이터 유효성 검사 기술은 문제를 식별하지만 구성 또는 데이터를 변경하지 않습니다.
* 각 구현 변경 후 Streaming Media 유효성 검사를 다시 실행합니다. 요청 시 실행되며 지속적인 모니터링을 제공하지 않습니다.
* 구현 안내서 기술은 계획에만 사용하십시오. Adobe 시스템에 액세스하거나 구현을 수행하지 않습니다.

## 다음 단계

* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* 동료 채팅을 설정하고 작업 예제를 보려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
