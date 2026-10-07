---
title: 동료 프로젝트에서 구현 체크리스트 생성
description: Coworker Projects에서 할당 및 추적할 수 있는 단계를 사용하여 구현 안내서 계획에서 미리 채워진 구현 체크리스트를 생성하는 방법을 알아봅니다.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Coworker Projects로 구현 체크리스트 생성

Adobe CX Enterprise Coworker은 Customer Journey Analytics, Adobe Analytics에서 Customer Journey Analytics으로 업그레이드, Content Analytics(ACA), Marketing Campaign Analytics(MCA) 또는 스트리밍 미디어용 구현 안내서 계획의 순서가 지정된 단계로 미리 채워진 Coworker 프로젝트에서 구현 체크리스트 프로젝트를 생성할 수 있습니다. Coworker는 기술적으로 가능한 한 많은 단계를 자동화하거나 지원하므로 귀하와 귀하의 팀은 구현 과정을 추적할 수 있는 단일 위치를 보유합니다.

구현을 주도하거나 기술 단계를 실행하거나 진행 상황에 대한 가시성만 필요한 경우 이 체크리스트를 사용하여 Coworker에서 나가지 않고 작업을 할당하고 상태를 추적하고 팀과 공동 작업을 수행할 수 있습니다.

>[!NOTE]
>
>다음 사항을 고려하십시오.
>
>* 이 기능은 사용자 지정 구현 또는 업그레이드 단계([Coworker로 구현 계획](./implementation-guide.md) 참조), 구현(이 체크리스트) 및 유효성 검사(예: [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드 유효성 검사](./data-validation-aa-cja.md) 또는 [Streaming Media 구현의 유효성 검사](./streaming-media-validation.md)) 워크플로의 일부입니다. 세 단계를 모두 사용할 필요는 없지만 이 체크리스트를 생성하려면 완료된 구현 가이드 플랜이 필요합니다.
>* Coworker가 실행하거나 지원하는 단계에는 신뢰도 또는 검증 신호가 자동으로 포함됩니다. 완료 표시를 하기 전에 이러한 단계를 검토하십시오. 동료는 자동화된 결과를 확인된 사실로 제시하지 않습니다.

이 체크리스트를 사용하여 다음을 수행합니다.

* 계획을 수동으로 조립하는 대신, 제품 경로에 대해 순서가 지정되고 미리 채워진 단계 세트로 구현 또는 마이그레이션을 시작하십시오.

* 구현 리드에 직접 문의하지 않고 차단된 항목과 다음 항목을 포함한 구현 중간 상태를 확인합니다.

* 단일 직선이 아니라 단계를 동시에 또는 단계적으로 실행하는 다중 플랫폼 또는 다중 지역 구현을 계획합니다.

* 가능한 경우 Coworker에서 Adobe Analytics 및 Customer Journey Analytics 구성 간 유효성 검사 실행과 같은 단계를 직접 수행하도록 합니다.

* 팀이 진행하기 전에 승인해야 하는 단계에 대한 승인 게이트를 소개합니다.


## 시작하기에 앞서

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### 필요한 정보

구현 체크리스트를 생성하려면 다음을 수행해야 합니다.

* 제품 경로에 대한 완료된 구현 안내서 대화. [동료와 함께 구현 계획](./implementation-guide.md)을 참조하세요. Coworker는 사전 정의된 플레이북을 사용하여 이 플랜을 자동으로 Coworker Project로 변환합니다. 직접 내보낼 필요가 없습니다.

* 조직의 동료 프로젝트에 액세스

### 제한 사항

이 기능을 사용하기 전에 다음 사항에 유의하십시오.

* **가이드 콘텐츠를 소유하지 않습니다**: 이 기능은 구현 가이드 스킬의 계획을 사용합니다. 기본 콘텐츠는 작성하거나 유지 관리하지 않습니다.
* **동기화 동작이 아직 완전히 정의되지 않았습니다**: 체크리스트가 구현 가이드 플랜에 대한 업데이트와 계속 동기화되도록 되어 있지만 정확한 동기화 메커니즘이 아직 정의되어 있습니다. 구현이 긴 타임라인에 걸쳐 있는 경우 안내서 계획 업데이트를 수동으로 확인하십시오.
* **Coworker 프로젝트 필요**: 이 기능은 조직에서 사용 가능한 Coworker 프로젝트 플랫폼에 따라 다릅니다.

## 체크리스트 생성

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. 동료에게 로그인합니다.

1. 탐색 레일에서 [!UICONTROL **프로젝트**]&#x200B;를 선택합니다.

1. [!UICONTROL **새 프로젝트**]&#x200B;를 선택한 다음 구현 안내서 계획과 일치하는 미리 정의된 플레이북을 선택하십시오.

   동료는 계획을 경로에 대한 순서가 지정된 단계로 미리 채워진 프로젝트로 변환합니다.

## 결과 검토

동료는 사용자와 팀이 작업할 수 있는 동료 프로젝트로 구현 체크리스트를 생성합니다.

**프로젝트 보기**

프로젝트는 사용자의 계획에서 주문된 구현 단계를 그룹화합니다. 각 단계에 대해 다음 작업을 수행할 수 있습니다.

* 소유자 할당
* 진행 중 또는 완료 등 업데이트 상태
* 단계를 적용할 수 없음으로 표시하거나 구현에 적용되지 않는 경우 건너뜁니다.
* 의견 추가 및 팀과 공동 작업
* 승인 필요 단계를 완료로 간주하려면 승인 필요(승인 필요)

**자동화 및 지원 단계**

기술적으로 가능한 경우 Coworker는 Adobe Analytics 또는 Customer Journey Analytics의 구성 또는 상태 데이터 표시와 같이 단계를 직접 실행하거나 지원합니다. 이러한 단계들은 전술한 바와 같이, 신뢰도 또는 검증 신호를 포함한다.

**내보내기**

체크리스트 또는 요약 수준 진행률을 Jira, Workfront 또는 Excel로 내보내므로 기존 프로젝트 관리 워크플로우로 폴드할 수 있습니다.

**여러 확인 목록**

여러 보고서 세트, 지역 또는 브랜드와 같은 여러 동시 구현을 관리하는 경우 하나로 제한되지 않고 여러 구현 체크리스트 프로젝트를 유지 관리할 수 있습니다.
