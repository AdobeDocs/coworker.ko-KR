---
title: 데이터 레이크 보존 관리
description: CX Coworker을 사용하여 최적화할 가치가 있는 경험 이벤트 데이터를 식별하고, 데이터 세트 사용 및 보존 영향을 분석하고, 데이터 레이크 보존 정책을 관리하는 방법을 알아봅니다.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 1%
---
# 데이터 레이크 보존 관리

CX Coworker을 사용하여 샌드박스에 있는 Experience Event 데이터의 가치를 이해하고 최적화의 이점을 얻을 수 있는 데이터를 식별합니다. 먼저 Coworker에 샌드박스 데이터를 최적화하거나 데이터 세트를 정리하도록 요청하는 등의 광범위한 요청으로 시작할 수 있습니다. Coworker는 Data Management Agent를 사용하여 조사할 가치가 있는 데이터 세트를 표시하고, 데이터 세트가 얼마나 활발하게 사용되는지 분석하고, 보존 기간의 영향을 모델링하고, 적절한 경우 데이터 레이크 보존 정책을 관리하는 데 도움이 됩니다.

## 시작하기에 앞서 {#before-you-begin}

검토할 데이터 세트가 포함된 샌드박스에서 작업 중인지 확인합니다. 또한 데이터 관리 에이전트에 대한 액세스 권한과 필요한 Adobe Experience Platform 권한이 필요합니다. [데이터 관리 에이전트 필수 구성 요소](https://experienceleague.adobe.com/ko/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management#prerequisites)를 참조하십시오.

## 샌드박스의 데이터 최적화 {#optimize-data-in-your-sandbox}

이러한 기술을 워크플로우로 함께 사용합니다. 데이터의 가치를 이해하거나 샌드박스의 데이터를 최적화하는 등 광범위한 데이터 관리 목표로 시작합니다. Coworker는 조사할 가치가 있는 데이터 세트를 찾고, 데이터 세트 사용 빈도를 확인하고, 잠재적인 보존 기간의 영향을 모델링한 다음 준비가 되면 보존 정책을 설정, 변경 또는 제거할 수 있도록 지원합니다.

### 최적화할 가치가 있는 데이터 찾기 {#find-data-worth-optimizing}

시작할 위치를 결정하려면 Coworker에게 조사할 가치가 있는 경험 이벤트 데이터 세트를 식별하도록 요청하십시오. 데이터의 가치, 데이터 최적화 또는 데이터 세트 정리에 대해 질문하여 광범위하게 시작할 수 있습니다. 목록 데이터 세트 기술을 사용하여 스토리지 크기, 행 수, 기존 보존 상태 및 프로필 활성화를 검토할 수 있습니다. 데이터 세트 크기, 행 수 또는 최근 액세스 등의 기준으로 결과를 필터링하여 목록을 좁힐 수 있습니다. 이 기술은 읽기 전용입니다. Coworker는 크기, 행 수 및 데이터 기간별로 데이터 세트를 강조 표시하는 시각화와 함께 스캔하고 비교할 수 있는 테이블을 반환합니다.

![저장소, 행 수, 보존 정보, 데이터 세트 크기 및 데이터 수명 시각화와 함께 테이블의 경험 이벤트 데이터 세트를 보여 주는 공동 작업자 결과입니다.](../../assets/data-management/dataset-discovery-results.png)

목록의 범위를 좁히면 데이터 세트 분석 사용 기술을 사용하여 특정 데이터 세트가 얼마나 활발하게 사용되는지 알아보십시오.

이 기술로 인해 표시된 사용하지 않거나 중단된 모든 데이터 세트가 데이터 레이크 보존 정책에 적합한 후보자는 아닙니다. 전체 데이터 세트를 제거하거나 다른 Experience Platform 스토어에서 데이터를 관리해야 하는 경우 [적합한 데이터 수명 주기 관리 기능 선택](https://experienceleague.adobe.com/ko/docs/experience-platform/data-lifecycle/choose-a-capability)을 참조하십시오. 데이터 레이크 보존 정책을 설정하기 전에 데이터 세트가 경험 이벤트 데이터 세트인지 확인하십시오.

프롬프트 예:

- &quot;데이터가 최적화될 수 있다고 생각합니다.&quot;
- &quot;내 데이터의 가치를 이해하는 데 도움이 됩니다.&quot;
- &quot;내 샌드박스 데이터 최적화.&quot;
- &quot;내 샌드박스 데이터 세트를 정리합니다.&quot;
- &quot;가장 큰 이벤트 데이터 세트를 표시합니다.&quot;
- &quot;데이터 레이크 보존이 설정되지 않은 100GB보다 큰 데이터 세트를 표시합니다.&quot;
- &quot;2TB 정도의 데이터를 제거해야 합니다. 어디에서 시작해야 합니까?&quot;
- &quot;고립되었거나, 버려졌거나, 사용되지 않은 데이터를 찾는 데 도움을 줄 수 있습니까?&quot;
- &quot;지난 90일 동안 액세스하지 않은 데이터 세트의 우선 순위를 지정하십시오.&quot;

### 데이터 세트가 얼마나 활발하게 사용되는지 확인 {#check-how-actively-a-dataset-is-used}

데이터 세트가 데이터 레이크 보존 정책에 적합한 후보인지 결정하기 전에 데이터 세트가 얼마나 적극적으로 사용되는지 확인하십시오. 데이터 세트 분석 사용 기술을 사용하여 여러 사용 신호에서 특정 데이터 세트를 평가합니다. 이러한 신호에는 최근 수집 활동, 쿼리 활동, 스키마 안정성 및 데이터 세트가 다른 Adobe Experience Platform 애플리케이션을 피드하는지 여부가 포함됩니다. 이 기술은 읽기 전용입니다. Coworker는 전체 사용 계층, 신호 분류 및 데이터 세트에 대해 표시되는 내용에 대한 일반 언어 요약을 반환합니다.

<!-- TODO: Confirm the final usage-tier thresholds with engineering after the planned update from a 7-day to a 30-day analysis window is complete. Update this section with the final definitions before publishing. -->

>[!NOTE]
>
>표시된 지표는 유용한 신호를 제공하기 위한 것이며 의사 결정과 관련된 모든 요소를 나타내지는 않을 수 있습니다. 조치를 취하기 전에 사용 가능한 세부 사항을 검토하고 비즈니스 컨텍스트를 적용하는 것이 좋습니다.

![사용 계층, 개별 사용 신호 및 데이터 집합 활동 요약을 보여 주는 동료 데이터 집합 사용 분석입니다.](../../assets/data-management/dataset-usage-analysis.png)

프롬프트 예:

- &quot;웹 이벤트 데이터 세트가 얼마나 활발하게 사용되고 있습니까?&quot;

### 보존 기간의 영향 모델링 {#model-the-impact-of-a-retention-period}

특정 보존 기간을 커밋하기 전에 보관 또는 제거할 데이터의 양을 확인하십시오. 데이터 세트 유지 분석 기술을 사용하여 데이터 세트의 스토리지 지표와 데이터 보존 기간 분포를 검토할 수 있습니다. 그런 다음 해당 분포를 사용하여 제안된 보존 기간이 유지하거나 제거하는 데이터의 양을 모델링합니다. Coworker는 행 수 및 저장소 크기별로 예상되는 영향을 보여줍니다.

![30일, 60일 및 90일 보존 기간 동안 보관 및 제거된 행 수를 비교하는 동료입니다.](../../assets/data-management/retention-period-comparison.png)

이 기술은 읽기 전용입니다. 동료는 데이터 나이 및 영향 분석을 대화에서 직접 반환하므로 변경 여부를 결정하기 전에 데이터 세트의 현재 보존 설정과 결과를 비교할 수 있습니다.

프롬프트 예:

- &quot;이 데이터 세트에 60일 보존 기간을 설정하면 어떤 영향이 있습니까?&quot;

### 보존 정책 설정, 변경 또는 제거 {#set-change-or-remove-a-retention-policy}

>[!IMPORTANT]
>
>최소 데이터 레이크 보존 기간은 30일입니다. 더 짧은 기간은 지원되지 않습니다.

보존 기간을 결정하면 데이터 세트 보존 관리 기술을 사용하여 데이터 세트에 대한 데이터 레이크 보존 정책을 설정, 변경 또는 제거합니다. 이 스킬은 변경 사항이 적용되기 전에 제안된 영향을 보여 줍니다. 요청을 명시적으로 승인한 후에만 정책이 적용됩니다. 원하는 변경 사항을 설명하는 것은 적용되지 않습니다.

![제안된 데이터 레이크 보존 정책, 그 영향 및 변경 내용이 적용되기 전에 필요한 확인을 표시하는 동료입니다.](../../assets/data-management/retention-impact-preview.png)

보존 정책을 확인한 후 변경 사항이 Adobe Experience Platform UI에 표시되는 데 시간이 조금 걸릴 수 있습니다. 보존 정책은 만료된 데이터를 즉시 삭제하지 않습니다. 정책이 적용된 후 24시간 내에 초기 보존 작업이 시작됩니다. 초기 실행 후 예약된 작업은 30일마다 만료된 레코드를 평가하고 삭제합니다. 유지 및 삭제에 대한 자세한 내용은 [경험 이벤트 TTL(데이터 세트 유지) 안내서](https://experienceleague.adobe.com/ko/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide)를 참조하십시오.

정책을 설정, 변경 또는 제거할 때를 포함하여 모든 보존 정책 변경 사항이 감사 추적에 기록됩니다. 감사 추적은 각 변경을 수행한 사용자, 발생 시기 및 수정된 내용을 기록합니다. Coworker에서 제공하는 링크를 따라 Adobe Experience Platform에 있는 데이터 세트의 감사 로그 탭에서 이러한 이벤트를 검토할 수 있습니다. 자세한 내용은 [감사 로그 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview)를 참조하십시오.

![타임스탬프, 사용자, 데이터 세트, 작업 및 상태를 포함하여 데이터 레이크 보존 정책 업데이트를 표시하는 Adobe Experience Platform 감사 로그.](../../assets/data-management/retention-audit-log.png)

프롬프트 예:

- &quot;이 데이터 세트의 보존을 60일로 설정합니다.&quot;
- &quot;이 데이터 세트에 대한 보존 정책을 제거합니다.&quot;

## 모범 사례 {#best-practices}

데이터 관리 에이전트를 사용할 때는 다음 사항을 염두에 두십시오.

- **광범위한 목표로 시작합니다.** 주의가 필요한 데이터 세트를 모르는 경우 Coworker에 데이터의 가치를 이해하거나 샌드박스의 데이터를 최적화할 수 있도록 도와달라고 요청하십시오. 개별 데이터 세트를 분석하기 전에 데이터 세트 목록 기술을 사용하여 최근 사용량 낮음 또는 전혀 사용을 제안하는 신호가 있는 데이터 세트를 식별합니다.
- **확인하기 전에 영향 미리 보기를 검토합니다.** 보존 변경을 승인하기 전에 보관 및 제거할 내용을 검토하십시오.
- **변경 내용을 표시할 시간을 허용합니다.** CX Coworker에서 보존 변경 사항을 확인한 후 Adobe Experience Platform UI에 변경 사항을 반영할 수 있는 짧은 시간을 제공합니다.

## 다음 단계 {#next-steps}

데이터 관리 에이전트의 기술, 범위, 동작 및 제한 사항에 대한 자세한 내용은 [데이터 관리 에이전트 개요](https://experienceleague.adobe.com/ko/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management)를 참조하십시오. Adobe Experience Platform에서 데이터 레이크 보존 정책이 작동하는 방법에 대한 자세한 내용은 [경험 이벤트 TTL(데이터 세트 보존) 안내서](https://experienceleague.adobe.com/ko/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide)를 참조하십시오.
