---
title: 동료 채팅을 사용하여 Customer Journey Analytics 데이터 분석
description: Adobe CX Enterprise Coworker Chat을 사용하여 Customer Journey Analytics 데이터를 분석하고 단계를 구축하며 여정에서 고객이 중단되는 위치를 찾는 방법에 대해 알아봅니다.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1944'
ht-degree: 1%
---

# 동료 채팅을 사용하여 데이터 분석

이 페이지의 정보에서는 Adobe CX Enterprise Coworker Chat에 대한 개요를 제공하며 조직의 데이터를 분석하는 데 어떻게 도움이 될 수 있는지 설명합니다.

Coworker Chat을 사용하면 팀이 자연어를 사용하여 Adobe 제품 작업을 자동화하여 유연한 계획, 사용자 정의 기술 및 지능형 실행을 통해 아이디어를 작업으로 신속하게 전환할 수 있습니다. Coworker에 대한 일반적인 정보는 [CX Enterprise Coworker 개요](/help/home.md)를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## 데이터 분석 작동 방식

동료 채팅은 이전에 Analysis Workspace에서만 가능했던 고급 데이터 분석을 수행할 수 있습니다. Coworker Chat은 Customer Journey Analytics 데이터 보기 또는 Adobe Analytics 보고서 세트의 데이터에 액세스하여 자연어 프롬프트로 데이터를 탐색하고 답변을 얻을 수 있습니다.

동료 채팅은 Customer Journey Analytics 또는 Adobe Analytics의 권한을 상속합니다. Analysis Workspace에서 사용할 수 있는 데이터 보기, 보고서 세트, 차원, 지표 및 세그먼트에만 액세스할 수 있습니다.

동료 채팅에서 시각화를 만들면 더 많은 수동 제어를 위해 언제든지 Analysis Workspace에서 열 수 있습니다.

## 빠른 답변 및 깊이 있는 작업

필요한 분석의 양에 따라 두 가지 방법으로 Coworker Chat을 사용할 수 있습니다.

* **빠른 답변** - 간단한 언어를 직접 질문하고 즉시 답변을 받으십시오. 비즈니스 사용자들은 이러한 방식으로 동료 채팅을 사용하는 경우가 많으며, 분석가들은 이해 관계자를 위한 빠른 답변이 필요할 때도 이를 사용합니다.
* **깊이 생각해본 작업** - 동료 채팅을 통해 비즈니스 문제를 조사하고, 원인을 배제하고, 권장 사항에 도달하기 위해 여러 차례 대화할 수 있습니다. 분석가는 일반적으로 이 접근 방식을 사용하여 권장 사항을 작성하기 전에 데이터를 심층적으로 탐색합니다.

## 동료 채팅에서 분석 시작

알기 원하는 내용을 쉬운 언어로 설명함으로써 시작하십시오. 공동 작업자 채팅은 분석을 계획하고, 데이터 보기 또는 보고서 세트를 쿼리하고, 시각화 및 요약을 만듭니다.

다음 사용 사례는 수행할 작업별로 그룹화되어 있습니다. 각 그룹에는 가장 적합한 역할이 나열됩니다.

### 성능 측정

**전문가:**, 비즈니스 사용자

| 사용 사례 | 함수 |
| --- | --- |
| [Customer Journey Analytics 및 Adobe Analytics 데이터 분석](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Customer Journey Analytics 및 Adobe Analytics 데이터 분석](../../assets/coworker-funnel-response-card.png)</p> | 데이터 보기 또는 보고서 세트에 대한 자연어 질문에 답변하고, 유입 경로 및 기타 시각화를 구축하며, 고객이 이탈하는 지점을 찾습니다. 추가적인 분석을 위해 Analysis Workspace에서 모든 시각화를 열 수 있습니다.<p>**샘플 프롬프트:** &quot;최근 30일 동안의 페이지 보기 표시&quot;</p><p>자세한 내용은 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.</p> |
| [성능 비교](#skills-and-limitations) | 채널, 기간 또는 세그먼트 간에 지표를 나란히 비교합니다.<p>**샘플 프롬프트:** &quot;월별 채널별 수익 비교&quot;</p><p>자세한 내용은 [기술 및 제한 사항](#skills-and-limitations)을 참조하세요.</p> |
| [캠페인 성과 측정](/help/chat/use-cases/overview.md#data-insights) | 주어진 기간 동안 캠페인, 채널 및 웹 속성을 수행하는 방법을 확인하십시오.<p>**샘플 프롬프트:** &quot;지난 달 Acrobat 웹 캠페인의 성능은 어떻습니까?&quot;</p><p>자세한 내용은 동료 채팅 사용 사례의 [데이터 인사이트](/help/chat/use-cases/overview.md#data-insights)를 참조하십시오.</p> |
| [단계 분석](#skills-and-limitations) | 여러 단계로 구성된 전환 단계를 살펴보고 각 단계에서 드롭오프가 있는지 확인합니다.<p>**우수 사례:** 분석가</p><p>**샘플 프롬프트:** &quot;체크아웃 funnel 안내&quot;</p><p>자세한 내용은 [기술 및 제한 사항](#skills-and-limitations)을 참조하세요.</p> |

### 지표가 변경된 이유 확인

**우수 사례:** 분석가

| 사용 사례 | 함수 |
| --- | --- |
| [트렌드 및 근본 원인 살펴보기](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![트렌드 및 근본 원인 살펴보기](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | 수동 쿼리 없이 Customer Journey Analytics 및 Adobe Analytics 데이터의 경향과 성능 변화를 주도하는 요인을 식별합니다.<p>**샘플 프롬프트:** &quot;지난 주에 전환율이 떨어진 이유는 무엇입니까?&quot;</p><p>자세한 내용은 [Customer Journey Analytics 및 동료](/help/chat/use-cases/data-insights/root-cause-analysis.md)를 참조하세요.</p> |
| [운영 추세 및 원인 분석](/help/chat/use-cases/overview.md#data-insights) | 대상자, 데이터 세트 및 여정에 대한 내역 시계열 데이터를 쿼리하고 변경 사항을 발생시킨 원인을 식별합니다.<p>**관리자:**, 분석가</p><p>**샘플 프롬프트:** &quot;지난 90일 동안의 대상자 크기 트렌드 표시&quot;</p><p>자세한 내용은 동료 채팅 사용 사례의 [데이터 인사이트](/help/chat/use-cases/overview.md#data-insights)를 참조하십시오.</p> |

### 향후 성과 예측

**우수 사례:** 분석가

| 사용 사례 | 함수 |
| --- | --- |
| [예측 지표](#skills-and-limitations) | 매출 목표를 달성하기 위한 적절한 과정에 있는지 여부와 같이, 과거 Customer Journey Analytics 또는 Adobe Analytics 데이터에서 향후 지표 값을 예상할 수 있습니다.<p>**샘플 프롬프트:** &quot;향후 30일 동안 세션 예측&quot;</p><p>자세한 내용은 [기술 및 제한 사항](#skills-and-limitations)을 참조하세요.</p> |

### 이해 당사자와 통찰력 공유

**전문가:**, 비즈니스 사용자

| 사용 사례 | 함수 |
| --- | --- |
| [경영진 요약 및 KPI 다이제스트 만들기](#skills-and-limitations) | 관련자가 즉시 사용할 수 있는 성능 요약, 권장 사항 및 슬라이드 데크 아웃라인을 생성합니다.<p>**샘플 프롬프트:** &quot;지난달 실행 요약 제공&quot;</p><p>자세한 내용은 [기술 및 제한 사항](#skills-and-limitations)을 참조하세요.</p> |

### 구현 계획 또는 업그레이드

**관리자:** 추천

| 사용 사례 | 함수 |
| --- | --- |
| [구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![구현 계획](../../assets/ui-guide-6.png)</p> | Edge을 구현하거나, Adobe Analytics에서 업그레이드하거나, Content Analytics, Marketing Campaign Analytics 또는 Customer Journey Analytics에서의 스트리밍 미디어 컬렉션을 설정하기 위한 개인화된 단계별 플랜을 만듭니다. 계획에는 소유자, 작업량 예상, 종속성 및 유효성 검사 단계 등의 세부 사항이 포함됩니다.<p>**샘플 프롬프트:** &quot;Customer Journey Analytics 구현을 계획하는 데 도움&quot;</p><p>자세한 내용은 [Coworker로 구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)을 참조하세요.</p> |
| [구현 검사 목록 생성](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![구현 검사 목록 생성](../../assets/data-validation-aa-cja/date-detail.png)</p> | Customer Journey Analytics 구현 계획을 Coworker Projects의 체크리스트로 전환하여 팀이 단계를 할당하고 상태를 추적하고 승인 게이트를 추가할 수 있습니다.<p>자세한 내용은 [Coworker 프로젝트를 사용하여 구현 검사 목록 생성](/help/chat/use-cases/data-insights/intelligent-checklist.md)을 참조하십시오.</p> |

### 데이터가 정확한지 확인

**관리자:** 추천

| 사용 사례 | 함수 |
| --- | --- |
| [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 데이터 유효성 검사](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Adobe Analytics 보고서 세트와 Customer Journey Analytics 데이터 보기 간의 차원, 지표 및 트렌드를 비교한 다음, 업그레이드를 지원하도록 수정 사항을 권장합니다.<p>**관리자:**, 분석가</p><p>**샘플 프롬프트:** &quot;내 AA 보고서 세트를 내 CJA 데이터 보기와 비교&quot;</p><p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Coworker를 사용하여 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)를 참조하십시오.</p> |
| [스트리밍 미디어 구현의 유효성 검사](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![스트리밍 미디어 구현의 유효성 검사](../../assets/ui-guide-8.png)</p> | 데이터 스트림, 스키마, 데이터 세트, 데이터 보기 및 세션 데이터를 확인하여 Streaming Media 추적이 구성되어 있고 데이터가 올바르게 수집되는지 확인합니다.<p>**샘플 프롬프트:** &quot;Streaming Media 구현은 전체적으로 얼마나 정상입니까?&quot;</p><p>자세한 내용은 [Coworker를 사용하여 Streaming Media 구현 확인](/help/chat/use-cases/data-insights/streaming-media-validation.md)을 참조하십시오.</p> |
| [Customer Journey Analytics에 대한 데이터 세트 품질 확인](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Customer Journey Analytics에 대한 데이터 세트 품질 확인](../../assets/data-validation-aep/dataset-validation.png)</p> | Customer Journey Analytics 보고를 제공하는 데이터 세트를 식별한 다음 스키마, ID 품질 및 필드 품질을 검사하여 대시보드를 작성하기 전에 문제를 해결할 수 있습니다.<p>자세한 내용은 [Coworker의 데이터 유효성 검사 기술을 사용하여 Customer Journey Analytics 데이터 유효성 검사](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)를 참조하십시오.</p> |
| [Experience Platform으로 수집 후 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Experience Platform으로 수집 후 데이터 유효성 검사](../../assets/data-validation-aep/null-values.png)</p> | Experience Platform 데이터 세트 및 필드에 대한 통계 및 시맨틱 검사를 실행하여 잘못된 값 또는 매핑 문제와 같은 데이터 품질 문제를 찾습니다.<p>**샘플 프롬프트:** &quot;데이터 집합 Electronics 샘플 1000의 유효성 검사&quot;</p><p>자세한 내용은 [Coworker를 사용하여 Experience Platform 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aep.md)를 참조하십시오.</p> |

### 반복하는 분석 자동화

**우수 사례:** 분석가

| 사용 사례 | 함수 |
| --- | --- |
| [사용자 지정 Customer Journey Analytics 기술 만들기](#skills-and-limitations) | 반복하는 분석을 세션 간에 지속되는 재사용 가능한 스킬로 전환합니다.<p>**샘플 프롬프트:** &quot;이 주별 수익 분석을 재사용 가능한 스킬로 전환&quot;</p><p>자세한 내용은 [기술 및 제한 사항](#skills-and-limitations)을 참조하세요.</p> |

사용 기술과 더 많은 샘플 프롬프트를 포함하여 이러한 사용 사례에 대한 자세한 내용은 [데이터 인사이트 사용 사례](/help/chat/use-cases/overview.md#data-insights)를 참조하십시오.

## 기술 및 제한 사항

Customer Journey Analytics 또는 Adobe Analytics 데이터를 분석하는 데 다음 기술을 사용할 수 있습니다.

| 스킬 | 사용 대상 | 필요한 권한 | 범위를 벗어남 |
| --- | --- | --- | --- |
| `cja`, `aa` | Customer Journey Analytics 데이터 보기(`cja`) 또는 Adobe Analytics 보고서 세트(`aa`)를 실시간으로 쿼리합니다.<ul><li>가져오기 지표, 차원, 세그먼트, 데이터 보기 및 보고서 세트</li><li>채널, 기간 또는 세그먼트를 나란히 비교</li><li>여러 단계로 구성된 funnel 및 폴아웃 분석 실행</li><li>이전 트렌드를 기반으로 한 예측 지표</li></ul> | 쿼리할 데이터 보기 또는 보고서 세트에 대한 액세스 보기 | <ul><li>데이터 보기 또는 보고서 세트 구성 요소 만들기 또는 편집</li><li>액세스 권한이 있는 데이터 보기 또는 보고서 세트 외부의 데이터</li><li>지표 예측을 뛰어넘는 예측 모델링</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | 지표가 변경되었다는 보고만 하지 않고 변경된 이유를 조사하십시오.<ul><li>알려진 기간 동안 알려진 지표의 변경 사항을 조사합니다</li><li>변경에 기여한 차원 및 세그먼트를 표시합니다.</li></ul> | 분석 중인 데이터 보기 또는 보고서 세트에 대한 액세스 보기 | <ul><li>확인하지 않은 예외 항목 탐지(자동화된 경고 또는 실시간 경고 없음)</li><li>액세스 권한이 있는 데이터 보기 또는 보고서 세트 외부의 지표에 대한 근본 원인 분석</li></ul> |
| `cja-executive-summary` | 관련자가 준비가 된 데이터 요약을 생성합니다.<ul><li>지정된 기간 동안의 성능 요약</li><li>데이터를 기반으로 규범적 권장 사항 생성</li><li>슬라이드 데크 또는 관련자 판독에 대한 윤곽선 콘텐츠</li></ul> | 요약에서 다루는 데이터 보기 또는 보고서 세트에 대한 액세스 보기 | <ul><li>최종 슬라이드 데크 또는 프레젠테이션 파일 구축</li><li>액세스 권한이 없는 데이터 보기 또는 보고서 세트에 걸쳐 있는 요약</li></ul> |
| `aa-cja-validation` | [!DNL Adobe Analytics]과(와) Customer Journey Analytics 간의 데이터 비교, 감사 및 조정:<ul><li>보고서 세트와 데이터 보기 간의 지표 값 비교</li><li>두 데이터 소스 간의 불일치 플래그 지정</li></ul> | 비교 중인 [!DNL Adobe Analytics] 보고서 세트 및 Customer Journey Analytics 데이터 보기에 대한 액세스 권한 보기 | <ul><li>데이터 불일치의 근본 원인 해결</li><li>[!DNL Adobe Analytics] 및 Customer Journey Analytics 이외의 데이터 원본 확인</li></ul> |
| `cja-skill-creator` | 이미 실행한 분석을 재사용 가능한 스킬로 전환합니다.<ul><li>완료된 분석을 명명된 재사용 가능한 스킬로 변환</li><li>저장된 스킬을 향후 채팅 세션에서 사용할 수 있도록 설정</li></ul> | 기술 관리 | <ul><li>저장된 스킬을 다른 사용자와 자동으로 공유(조직 수준의 스킬 라이브러리는 관리자 설정이 필요)</li><li>스킬이 참조하는 데이터 보기 또는 보고서 세트 구성 요소 편집</li></ul> |

## 동료 채팅을 사용하여 데이터를 분석할 때의 모범 사례

### 조직 수준 우수 사례

* 조직의 분석가를 동료 챔피언으로 지정합니다.

* 사용자가 사용할 수 있는 데이터 및 구성 요소와 상관 관계가 있는 검증된 프롬프트 및 스킬 라이브러리를 만듭니다.

* 분석에 사용할 구성 요소만 사용하도록 Coworker Chat에 지시하는 스킬을 한 개 이상 만듭니다. 이렇게 하면 Coworker Chat이 조직의 사용자에게 가장 관련성이 높은 데이터를 제공하는 데 도움이 됩니다.

* 빠른 답변을 위해 동료 채팅에게 질문할 시점과 깊은 생각에 잠긴 작업에 사용할 시점에 대해 사용자에게 교육합니다.

### 사용자 수준 우수 사례

* 계획 모드를 사용합니다.

  이 모드는 복잡한 작업에 특히 유용하지만, 동료가 행동하기 전에 후속 질문을 할 수 있기 때문에 간단한 작업에 대해 더 나은 결과를 얻을 수도 있습니다. 자세한 내용은 [플랜 모드](/help/chat/ui-guide.md#plan-mode)를 참조하세요.

* 프롬프트를 만들 때 가능한 한 구체적이어야 합니다.

  * 분석할 차원, 지표 및 날짜 범위의 이름을 지정합니다.
  * 정확한 이름으로 구성 요소를 참조합니다.
  * 포함, 제외 또는 비교하려는 세그먼트, 대상, 채널 또는 장치를 지정합니다.
  * funnel, 트렌드 또는 집단 테이블 등 특정 시각화 유형을 원하는지 여부를 기술합니다.
  * 동료 채팅에서 후속 질문을 제안하려면 권장되는 다음 단계를 요청하십시오.
  * 지표를 예상할 때 &quot;다음 30일&quot;과 같은 예측 대상 기간을 요청합니다.
  * 이미 가지고 있는 가설을 언급하면 Coworker Chat이 이를 검증하거나 배제할 수 있습니다.
  * 지표 변경에 대한 분류를 원하는 경우 기여 차원을 요청합니다.
  * 리더십 또는 마케팅 팀과 같은 요약에 대한 대상자를 지정하고 결과를 제시하려는 경우 슬라이드 데크 개요를 요청합니다.
  * 데이터의 유효성을 검사할 때 비교할 특정 보고서 세트 및 데이터 보기의 이름을 지정합니다.
  * 먼저 분석을 완료한 다음 동료 채팅에 요청하여 기술로 저장해 두십시오. 그러면 명확하고 설명적인 이름이 지정되고 재사용할 빈도가 얼마나 되는지 알 수 있습니다.

* 동료 채팅 메모리에 표준 방향을 추가합니다. 예를 들어, 항상 동일한 데이터 보기 또는 보고서 세트의 데이터를 사용하는 경우 해당 데이터를 메모리에 추가합니다. 자세한 내용은 Coworker Chat을 사용하여 데이터 분석 시작에서 [메모리에 데이터 보기 또는 보고서 세트 환경 설정 추가](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory)를 참조하십시오.

## 다음 단계

동료 채팅을 설정하고 작업 예제를 보려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.


