---
title: Coworker와 함께 Customer Journey Analytics 또는 스트리밍 미디어 구현 계획
description: Coworker의 구현 안내서 기술이 검색 대화를 내보낼 수 있는 체크리스트를 통해 개인화되고 순서가 지정된 구현 계획으로 변환하는 방법에 대해 알아봅니다.
hold: true
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 1%
---

# Coworker를 사용하여 구현 계획

Coworker에는 Customer Journey Analytics, Adobe Analytics에서 Customer Journey Analytics으로의 업그레이드, Content Analytics(ACA), Marketing Campaign Analytics(MCA) 및 스트리밍 미디어라는 5가지 구현 가이드 기술이 포함되어 있습니다. 각 스킬은 짧은 검색 대화를 단일 동료 채팅 대화 내에서 대화형 체크리스트와 즉시 사용할 수 있는 내보내기를 포함하는 개인화된 종속성 인식 구현 계획으로 전환합니다.

이러한 제품으로 바로 구입하거나 마이그레이션하는 경우 Adobe의 구현 요구 사항을 수동으로 조사하거나 프로젝트 계획을 처음부터 빌드하지 않고도 이러한 기술을 사용하여 주문된 단계별 계획을 얻을 수 있습니다.

>[!NOTE]
>
>다음 사항을 고려하십시오.
>
>* 이러한 구현 가이드 기술은 사용자 지정 구현 또는 업그레이드 단계(이러한 안내서), 구현([Coworker 프로젝트로 구현 체크리스트 생성](./intelligent-checklist.md) 참조) 및 유효성 검사(예: [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드 확인](./data-validation-aa-cja.md) 또는 [Streaming Media 구현의 유효성 검사](./streaming-media-validation.md))와 같은 보다 크고 선택적인 워크플로의 일부입니다. 세 단계를 모두 사용할 필요는 없습니다. 예를 들어 계획이나 체크리스트를 생성하지 않고 데이터를 검증할 수 있습니다.
>* 이러한 기술은 Adobe 시스템에 액세스하거나 변경하지 않습니다. 구현을 계획하는 데 도움이 됩니다. 라이브 테넌트에 대해 작업을 수행하거나 확인하지 않습니다.

이 기술을 사용하여 다음을 수행할 수 있습니다.

* 각 단계에 대한 소유자, 예상 작업량 및 종속성을 포함하여 Customer Journey Analytics을 처음부터 시작할 수 있도록 개인화되고 순서가 지정된 계획을 가져옵니다.

* Adobe Analytics을 해제하기 전에 Adobe Analytics 기능 패리티 매핑, 내역 채우기 순서 지정 및 유효성 검사 게이트를 포함하여 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하기 위한 마이그레이션 계획을 가져옵니다.

* 라이선스, 개인 정보 보호 및 PII 범위 지정, 안내식 구성 마법사를 포함하여 Content Analytics(ACA) 구현에 대한 안내식 계획을 가져옵니다.

* Adobe 소스 커넥터, 자체 데이터 세트 또는 하이브리드 접근 방식 중 어느 것을 사용하든 수집 경로에 맞게 조정된 Marketing Campaign Analytics(MCA)에 대한 온보딩 계획을 가져옵니다.

* 데이터스트림 구성, 플랫폼별 SDK/API 구현 및 미디어 이벤트 모델을 포함하여 Edge의 스트리밍 미디어 컬렉션에 대한 구현 계획을 가져옵니다.

## 시작하기에 앞서

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### 필요한 정보

구현 안내서 대화를 시작하려면 다음을 수행해야 합니다.

* Customer Journey Analytics(순 신규), Adobe Analytics에서 Customer Journey Analytics으로 업그레이드, Content Analytics(ACA), Marketing Campaign Analytics(MCA) 또는 Streaming Media로의 구현 경로 중 어느 것이 사용자에게 적용됩니까?

* 기존 Adobe Analytics 구현, 라이선스 상태 또는 계획된 데이터 수집 경로 여부 등 현재 환경에 대한 기본 세부 정보. 발견 대화는 이러한 세부 사항을 요구하지만, 준비된 상태로 두면 처리 속도가 빨라집니다.

### 제한 사항

이러한 기술을 사용하기 전에 다음 제한 사항을 염두에 두십시오.

* **계획만**: 이 스킬은 Adobe 시스템에 액세스하거나 변경하지 않습니다. 라이브 테넌트에 대해서는 구현을 수행하거나 확인하지 않습니다.
* **스킬당 하나의 제품 표면**: 각 스킬은 단일 구현 경로를 다룹니다. 요청이 다른 제품 표면에 적용되는 경우 스킬은 직접 답변하는 대신 올바른 제품 표면에 연결합니다.
* **자체적으로 프로젝트 추적 경험이 없음**: 이 기술은 계획을 생성하고 내보내지만 진행 중인 상태, 공동 작업 또는 승인을 스스로 추적하지 않습니다. 시간이 지남에 따라 플랜을 추적하려면 미리 정의된 플레이북을 사용하여 Coworker Project로 변환합니다. [동료 프로젝트로 구현 검사 목록 생성](./intelligent-checklist.md)을 참조하십시오.

## 구현 계획 세션 시작

1. 동료에게 로그인합니다.

1. [!UICONTROL **새 채팅**]&#x200B;을 선택하세요.

1. 텍스트 필드에서 계획할 구현 또는 마이그레이션에 대해 설명합니다. 예:

   **프롬프트**

   > Customer Journey Analytics 구현을 계획하는 데 도움이 됩니다.

   요청이 일치하는 구현 가이드 기술로 라우팅되어 대화형 검색 대화가 시작됩니다.

1. (조건부) 귀하에게 적용되는 구현 경로를 파악할 수 없는 경우 묻는 명확한 질문에 답한 후 계속합니다.

## 구현 경로 선택

각 구현 안내서 스킬은 하나의 제품 표면을 다룹니다.

### Customer Journey Analytics

기존 Adobe Analytics 배포 없이 Customer Journey Analytics을 처음부터 새로 시작할 수 있도록 개인화되고 순서가 지정된 구현 계획을 가져옵니다. 플랜에는 각 단계에 대한 소유자, 예상 작업량 및 종속성이 포함됩니다.

프롬프트 예:

* Customer Journey Analytics 구현을 계획하는 데 도움이 됩니다.
* 나는 Customer Journey Analytics을 처음부터 시작하고 있다. 구현 계획을 수립합니다.

### Adobe Analytics에서 Customer Journey Analytics으로 업그레이드

Adobe Analytics 기능 패리티를 Customer Journey Analytics에 매핑하고, 내역 채우기의 시퀀스를 지정하며, 유효성 검사 및 병렬 실행 게이트를 포함하는 마이그레이션 계획을 가져오면 Adobe Analytics을 해제할 수 있습니다.

프롬프트 예:

* Adobe Analytics에서 Customer Journey Analytics으로의 업그레이드 계획을 도와주십시오.
* Adobe Analytics에서 Customer Journey Analytics으로의 마이그레이션 계획을 수립합니다.

### Content Analytics(ACA)

라이선스, 개인 정보 보호 및 PII 범위 지정, 안내식 구성 마법사를 포함하여 Content Analytics(ACA) 구현에 대한 안내식 계획을 가져옵니다. ACA에는 DULE, CMK 또는 HIPAA 적용 범위가 없으므로 플랜에 개인 정보 보호 게이팅 단계가 포함됩니다.

프롬프트 예:

* Content Analytics 구현을 계획하는 데 도움이 됩니다.
* ACA 구현 계획을 수립합니다.

### Marketing Campaign Analytics (MCA)

Adobe 소스 커넥터, 자체 데이터 세트 또는 하이브리드 접근 방식 중 어느 것을 사용하든 간에 수집 경로에 맞게 조정된 Marketing Campaign Analytics(MCA) Essentials에 대한 온보딩 계획을 가져와서 funnel 매핑 및 데이터 정렬 단계가 사용자 환경에 맞게 조정되도록 합니다.

프롬프트 예:

* Marketing Campaign Analytics 구현을 계획하는 데 도움이 됩니다.
* 내 데이터 세트를 사용하여 MCA 온보딩 플랜을 작성하십시오.

### 스트리밍 미디어

Customer Journey Analytics 및/또는 Adobe Analytics 보고를 위해 세션, ping 및 완료를 올바르게 계측할 수 있도록 Edge에서 데이터 스트림 구성, 플랫폼별 SDK/API 구현 및 미디어 이벤트 모델에 대해 다루는 스트리밍 미디어 컬렉션에 대한 구현 계획을 가져옵니다.

프롬프트 예:

* Streaming Media 구현을 계획하는 데 도움이 됩니다.
* Edge에서 Streaming Media를 측정하기 위한 계획을 수립합니다.

## 결과 검토

Coworker는 구현 계획을 동일한 대화의 대화형 검사 목록 및 요약으로 반환합니다.

**대화형 검사 목록**

구현 단계를 단계 및 이정표로 그룹화하는 HTML 체크리스트입니다. 각 단계에 대해 체크리스트에는 다음이 포함됩니다.

* 작업량 견적
* 기본 소유자 및 모든 지원 소유자
* 다른 단계에 대한 하드 종속성
* 단계를 건너뛸 수 있는지 여부
* 관련 Experience League 또는 developer.adobe.com 설명서에 대한 링크

**내보내기**

워크플로우에 맞는 형식으로 플랜을 다운로드합니다.

| 내보내기 | 포함 사항 |
| --- | --- |
| CSV로 내보내기 | 간단한 단계 목록 |
| Jira-import CSV | Jira로 가져오기 위해 스토리 포인트, 우선 순위 및 레이블로 형식이 지정된 단계 |
| WORKFRONT CSV | Workfront으로 가져오기 위해 지속 시간 및 전임 작업으로 형식이 지정된 단계 |
| Markdown | 설명서 또는 Wiki에 붙여 넣을 수 있는 체크리스트 |

**채팅 중 요약**

체크리스트와 함께 Coworker는 대화에서 직접 다음과 같은 세 부분으로 구성된 요약을 제공합니다.

1. 플랜 개요
1. 전체 단계 테이블
1. 각 내보내기에 대한 다운로드 링크

## 플랜 작성 방법

각 구현 가이드 스킬은 동일한 4단계 프로세스를 따릅니다.

* **검색**: 미리 구성된 대화는 환경 및 목표에 대해 알아보기 위해 구현 경로와 관련된 5~9개의 질문을 합니다.
* **계산**: LLM은 응답에 적용할 조건부 단계 및 종속성 재정의를 결정합니다. 계획서 자체를 쓰지는 않습니다.
* **어셈블 및 렌더링**: 결정론적 프로세스는 단계 간의 종속성을 해결하고 순서를 지정하며 중요 경로(종속 단계의 가장 긴 체인)를 계산하고 체크리스트와 내보내기를 생성합니다.
* **게재**: 동료가 다운로드 링크와 플랜에 대한 채팅 요약을 제공합니다.

가이드 검색과 결정론적 조립의 이러한 조합은 귀하의 계획이 작성된 자유 재원이 아니라 귀하의 답변에서 일관되게 생성됨을 의미합니다.
