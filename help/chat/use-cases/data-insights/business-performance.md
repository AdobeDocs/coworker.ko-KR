---
title: Coworker Chat으로 비즈니스 성과 및 KPI 분석
description: 동료 채팅을 사용하여 지표가 이동한 이유, 지표가 향하는 방향을 예측하고 성과 검토를 준비하고 반복 분석을 재사용 가능한 기술로 전환할 수 있습니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 2%
---

# 비즈니스 성과 개요

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Adobe CX Enterprise Coworker 채팅을 사용하여 비즈니스의 운영 방식, 지표가 이동한 이유, 지표의 이동 위치 및 다음 작업을 파악합니다. 주요 지표의 변경 사항을 조사하고, 이를 전향에 투영한 다음, 결과를 관련자에게 준비된 요약 및 재사용 가능한 기술로 만들 수 있습니다.

비즈니스 성과는 동료 채팅의 여러 분석 도메인 중 하나입니다. 모든 도메인을 보려면 [동료의 채팅에서 분석 시작](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat)과(와) 함께 데이터 분석을 참조하십시오.

**전문가:**, 비즈니스 사용자

## 사전 요구 사항

이 페이지에서 사용 사례를 사용하려면 다음이 필요합니다.

* Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트에 연결된 동료 채팅. [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.
* 분석할 데이터 보기 또는 보고서 세트에 대한 액세스 권한을 봅니다. 동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다.

## 사용 사례

| 사용 사례 | 함수 |
| --- | --- |
| [트렌드 및 근본 원인 살펴보기](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![트렌드 및 근본 원인 살펴보기](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | 수동 쿼리 없이 Customer Journey Analytics 및 Adobe Analytics 데이터의 경향과 성능 변화를 주도하는 요인을 식별합니다.<p>**샘플 프롬프트:** &quot;지난 주에 전환율이 떨어진 이유는 무엇입니까?&quot;</p><p>자세한 내용은 [Customer Journey Analytics 및 동료](/help/chat/use-cases/data-insights/root-cause-analysis.md)를 참조하세요.</p> |
| [지표가 이동한 이유 설명](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 변경 사항 뒤에 있는 차원과 세그먼트를 표시하고 나머지를 배제하는 근본 원인 분석을 실행합니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;왜 화요일에 수익이 급증했는가?&quot;</li><li>&quot;무엇이 이번 달 세션의 변화를 이끌었는가?&quot;</li></ul><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| [비즈니스 성과 검토 준비](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 신뢰할 수 있는 지표를 결과 및 권장되는 다음 단계를 포함하는 설명된 성능 이야기로 바꿉니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;지난 달의 요약본을 주세요.&quot;</li><li>&quot;리더십 팀의 성과 요약&quot;</li></ul><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| [지표가 향하는 예측](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 이전 데이터에서 지표를 투사하여 다가오는 누락을 볼 수 있습니다.<p>**샘플 프롬프트:**</p><ul><li>&quot;향후 30일 동안의 세션 예측&quot;</li><li>&quot;매출 목표를 달성하는 데 도움이 됩니까?&quot;</li></ul><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| [사용자 지정 Customer Journey Analytics 기술 만들기](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 반복하는 분석을 세션 간에 지속되는 재사용 가능한 스킬로 전환합니다.<p>**샘플 프롬프트:** &quot;이 주별 수익 분석을 재사용 가능한 스킬로 전환&quot;</p><p>**추가 필수 구성 요소:** [일반 필수 구성 요소](#prerequisites) 외에 이 사용 사례에는 스킬 관리 권한도 필요합니다.</p><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |
| [시장 전체에 걸쳐 분석을 반복합니다](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | 브랜드, 지역 또는 사업부 전반에 걸쳐 검증된 분석 접근 방식을 적용합니다.<p>**우수 사례:** 분석가</p><p>**샘플 프롬프트:** &quot;EMEA 데이터 보기에 대해 주별 funnel 스킬 실행&quot;</p><p>자세한 내용은 [기술 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하세요.</p> |

## 사용된 스킬

<!-- FLAG: Confidence: High for the root cause analysis skills, `cja-executive-summary`, forecasting with `cja` and `aa`, and `cja-skill-creator` for creating skills. All are listed in the Skills and limitations table and in workflows.md. Medium for mapping Repeat successful analysis across markets to `cja-skill-creator`: the row describes running a saved skill, which is inferred. workflows.md also lists `cja-bacom-anomaly-tracker-v2`, `cja-cno-weekly-pulse`, and `cja-reporting` for executive summaries. They're left out because they look org-specific. Confirm with the PM. -->

동료는 이 문서에서 설명하는 사용 사례에 다음 기술을 사용합니다. 필요한 권한과 다루지 않는 기능을 포함하여 모든 분석 스킬 목록을 보려면 Coworker Chat로 데이터 분석에서 [스킬 및 제한 사항](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations)을 참조하십시오.

| 스킬 | 다음에 사용됨 |
| --- | --- |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | 트렌드 및 근본 원인 살펴보기<br>지표가 이동한 이유 설명 |
| `cja-executive-summary` | 비즈니스 성과 검토 준비 |
| `cja`, `aa` | 지표가 향하는 예측 |
| `cja-skill-creator` | 사용자 지정 Customer Journey Analytics 스킬 만들기<br>시장 전반에서 성공적인 분석을 반복합니다 |

## 더 나은 결과를 위한 팁

* 조사할 변경 사항 지표와 기간에 이름을 지정합니다. 근본 원인 분석은 알려진 기간 동안 알려진 지표에서 작동합니다.
* 지표 변경에 대한 분류를 원하는 경우 기여 차원을 요청합니다.
* 지표를 예상할 때 &quot;다음 30일&quot;과 같은 예측 대상 기간을 요청합니다.
* 리더십 또는 마케팅 팀과 같은 요약에 대한 대상자를 지정하고 결과를 제시하려는 경우 슬라이드 데크 개요를 요청합니다.
* 먼저 분석을 완료한 다음 동료 채팅에 요청하여 스킬로 저장합니다. 기술에 명확한 수사적 이름을 지정하고 재사용할 빈도를 메모하십시오.

## 다음 단계

* 다른 분석 도메인 및 모범 사례를 포함하여 Coworker Chat을 사용한 데이터 분석에 대한 개요를 보려면 [Coworker Chat을 사용하여 데이터 분석](/help/chat/use-cases/data-insights/analytics-overview.md)을 참조하십시오.
* 근본 원인 분석 작업을 보려면 [Customer Journey Analytics 및 동료](/help/chat/use-cases/data-insights/root-cause-analysis.md)를 참조하십시오.
