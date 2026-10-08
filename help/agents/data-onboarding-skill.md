---
title: 동료와 데이터 온보드
description: CX Coworker에서 데이터 온보딩 기술을 사용하여 대화형 워크플로우를 통해 새로운 데이터 소스를 Adobe Experience Platform에 온보딩하는 방법을 알아봅니다.
hide: true
source-git-commit: 8f7d5307b1928c052f020ca5e7aae3feee7af03e
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 2%
---

# 동료와 데이터 온보드

>[!AVAILABILITY]
>
>데이터 온보딩 기술은 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.
>
>데이터 온보딩 스킬은 Adobe CX Enterprise Coworker에 액세스할 수 있는 고객이 사용할 수 있으며, 이 경우 조직에 대해서도 활성화되어야 합니다. <!-- VERIFY BEFORE PUBLISH: confirm exact permission/entitlement name with Umesh Gohil, PLAT-296546. -->

CX Coworker의 데이터 온보딩 기술을 사용하여 단일 대화 워크플로우를 통해 새 데이터를 Adobe Experience Platform에 온보딩합니다. 여러 화면을 탐색하여 소스를 연결하고 손으로 스키마를 구축하는 대신 의도를 설명하고 동료가 소스 선택, 데이터 품질, 의미론적 강화, 스키마 매핑, 스키마 생성 및 데이터 흐름 생성을 안내합니다.

<!-- VERIFY BEFORE PUBLISH: confirm the loaded skill name ("Onboard Data to Experience Platform") and the exact post-landing prompt/flow with Umesh Gohil once flag access is arranged. -->

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인합니다.

- Adobe Experience Platform 및 적절한 조직과 샌드박스에 액세스합니다.
- 조직에 대한 데이터 온보딩 스킬이 활성화된 Adobe CX Enterprise Coworker에 액세스
- Adobe Experience Platform에서 스키마를 만들 수 있는 권한입니다.

플러그인 설치에 대한 지침은 [Coworker UI 안내서](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide)를 참조하십시오.

## 데이터 온보딩 스킬 사용 {#use-the-data-onboarding-skill}

현재 데이터 온보딩 기술은 Experience Platform UI의 스키마 생성에서 시작되며 이미 입력한 인텐트와 함께 Coworker를 엽니다.

데이터 온보딩 스킬을 사용하려면 다음을 수행하십시오.

1. Adobe Experience Platform에서 **[!UICONTROL 스키마]**(으)로 이동한 다음 **[!UICONTROL 스키마 만들기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 스키마 만들기]** 대화 상자에서 **[!UICONTROL AI로 데이터 온보딩]**&#x200B;을 선택한 다음 **[!UICONTROL 선택]**&#x200B;을 선택합니다.

   ![AI가 있는 온보드 데이터를 사용하여 스키마 만들기 대화 상자를 선택합니다.](./assets/data-onboarding-skill/create-a-schema-dialog.png)

1. CX Coworker은 스키마 생성 의도에서 미리 채워진 프롬프트가 있는 새 브라우저 탭에서 열리므로 다시 기술할 필요가 없습니다.
1. 메시지가 표시되면 온보딩할 소스(예: [!DNL Amazon S3], [!DNL Data Landing Zone], [!DNL Delta Share] 또는 [!DNL Marketo])를 선택하십시오.

   <!-- VERIFY BEFORE PUBLISH: screenshot of the Coworker landing/session-start state does not exist yet anywhere. Capture once flag access is confirmed. -->

1. 데이터 품질 검토, 의미론적 데이터 보강, 스키마 매핑 및 스키마 작성을 통해 동료와 대화를 계속하고 각 단계를 확인합니다.

CX Coworker 사용에 대한 자세한 내용은 [Coworker UI 안내서](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide)를 참조하십시오.

## 지원되는 사용 사례 {#supported-use-cases}

완료에 도움이 되는 데이터 온보딩 스킬을 통해 온보딩 워크플로의 부분을 살펴보십시오.

### 소스 선택 및 연결

수동으로 소스 커넥터를 찾아 구성하는 대신 가져올 데이터를 설명하고 Coworker 도움말을 통해 올바른 소스를 식별할 수 있습니다.

### 데이터 품질 검토

동료는 스키마에 커밋하기 전에 선택한 소스에 대한 데이터 품질 신호를 노출하므로 프로세스에서 문제를 조기에 발견할 수 있습니다.

### 의미론적으로 데이터 강화

동료는 수신 필드에 대한 의미론적 의미를 제안하여 원시 필드를 표준 정의에 매핑하는 수작업을 줄입니다.

### 스키마 매핑 및 생성

동료는 검토된 필드를 새 스키마 또는 기존 스키마에 매핑하고 동일한 대화의 일부로 Adobe Experience Platform에서 직접 만듭니다.

### 데이터 흐름 만들기

동료는 데이터를 지속적으로 가져오는 데 필요한 데이터 흐름을 만들어 온보딩을 완료합니다.

## 다음 단계 {#next-steps}

이 안내서를 읽은 후에는 스키마 생성에서 데이터 온보딩 기술을 시작하는 방법과 CX Coworker에서 수행하는 데 도움이 되는 사항을 이해해야 합니다.

Experience Platform UI 절차 및 액세스/자격 시나리오에 대해서는 스키마 UI 안내서에서 [AI로 데이터 온보딩](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas#data-onboarding-skill)을 참조하십시오.
