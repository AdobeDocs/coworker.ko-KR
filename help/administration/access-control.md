---
title: 동료에 대한 액세스 제어
description: 호환되는 Adobe 제품의 Adobe CX Enterprise Coworker 액세스 제어 및 권한에 대해 알아봅니다. 관리자 컨트롤을 찾고 액세스 관련 도움말을 봅니다.
last-substantial-update: 2026-11-04
level: beginner
role: Admin
jira: KT-22980
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 96c54754b978ac1be0fc5bb0741e9ed073017953
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%
---
# 동료에 대한 액세스 제어 {#access-control}

Adobe CX Enterprise Coworker 액세스 제어를 사용하여 Coworker를 사용할 수 있는 사용자와 사용자가 사용할 수 있는 기능을 관리합니다.

>[!NOTE]
>
>이 기능을 사용하려면 Coworker에서 조직을 활성화해야 합니다. 자세한 내용은 [동료 채팅 개요](https://experienceleague.adobe.com/ko/docs/coworker/content/chat/overview)를 참조하세요.

## 액세스 결정 방법 {#how-access-is-determined}

동료 액세스는 조직 전체 설정과 선택적 사용자 또는 그룹 재정의에 의해 제어됩니다. 조직 전체 설정은 조직의 사용자에 대해 동료 액세스를 활성화하거나 비활성화합니다. 액세스는 기본적으로 모든 사용자에 대해 활성화됩니다.

| 설정 | 액세스에 미치는 영향 |
| --- | --- |
| 조직 전체 설정 | 모든 사용자에 대해 동료 액세스를 활성화하거나 조직에 대해 비활성화합니다. |
| 사용자 또는 사용자 그룹 재정의 | 재정의는 관리자가 특정 사용자 또는 사용자 그룹에 대한 동료 액세스 권한을 제어합니다. |
| 호환 가능한 애플리케이션 권한 | 동료 액세스 컨트롤은 일반적으로 사용 가능한 모든 동료 기능에 액세스할 수 있는지 여부를 결정합니다. Coworker는 Coworker 호환 CX Enterprise 애플리케이션에서 사용자 권한을 상속하며 각 애플리케이션이 이미 시행하고 있는 권한을 준수합니다. |


## 동료 관리자 추가 {#add-coworker-admins}

동료 관리자는 [!DNL Adobe Admin Console]의 [!DNL Adobe Experience Platform]에 대해 **[!UICONTROL 제품 관리자]** 역할이 할당된 사용자입니다.

이 비디오를 통해 동료 관리자를 추가하는 방법을 알아보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/3507046?captions=kor&learn=on){transcript=true}

## 사용자 액세스 관리 {#manage-user-access}

1. 동료 경험을 엽니다. 자세한 내용은 [Coworker에 로그인](/help/chat/ui-guide.md#sign-in)을 참조하십시오.
2. 프로필 메뉴를 열고 **[!UICONTROL 관리자 설정]**&#x200B;을 선택합니다.

   ![프로필 메뉴 컨트롤이 강조 표시된 Coworker home입니다.](./assets/access-control/coworker-home.png)

   ![관리자 설정이 강조 표시된 Coworker 프로필 메뉴.](./assets/access-control/admin-settings.png)

3. **[!UICONTROL 액세스 제어]**&#x200B;를 선택합니다.

   액세스 제어 카드가 강조 표시된 ![관리자 설정.](./assets/access-control/access-control.png)

   이 비디오를 통해 동료 사용자를 관리하는 방법을 알아보십시오.

   >[!VIDEO](https://video.tv.adobe.com/v/3507156?captions=kor&learn=on){transcript=true}

4. Coworker에서 개인 사용자의 액세스를 관리하려면 **[!UICONTROL 사용자]**&#x200B;를 사용하고, 사용자 그룹의 Coworker 액세스를 관리하려면 **[!UICONTROL 사용자 그룹]**&#x200B;을 사용하십시오. 사용자 그룹 설정은 해당 구성원에게 적용됩니다.

   동료 사용자 그룹은 [!DNL Adobe Admin Console] 그룹과 별개입니다. 사용자 그룹을 [!DNL Adobe Admin Console]에서 Coworker로 동기화하는 작업이 곧 시작됩니다.

   사용자 목록에는 조직의 사용자가 포함됩니다. 이러한 사용자는 기본적으로 동료 액세스를 사용할 수 있습니다.

   * **사용:** 사용자 또는 사용자 그룹이 활성 상태입니다.
   * **사용 안 함:** 사용자 또는 사용자 그룹이 비활성 상태입니다.

   모든 사용자에 대한 액세스가 비활성화되면 **[!UICONTROL 재정의 허용]**&#x200B;을 켜고 **[!UICONTROL 재정의 추가]**&#x200B;를 선택하여 액세스 권한이 있는 사용자 또는 그룹을 추가하십시오.

## Coworker 호환 CX Enterprise 애플리케이션의 권한 {#permissions-in-compatible-applications}

동료 호환 CX Enterprise 애플리케이션은 자체 권한을 계속 적용합니다.

동료는 호환 가능한 애플리케이션에서 권한을 따릅니다. 예를 들어 [!DNL Adobe Experience Platform]의 데이터 세트에 액세스할 수 없는 경우 Coworker는 해당 데이터 세트를 검색하거나 작업을 대신 수행할 수 없습니다.

## 액세스 관련 도움말 보기 {#get-help-with-access}

[!UICONTROL 액세스 제어]가 표시되지 않으면 Adobe 관리자 또는 Adobe 담당자에게 문의하십시오. 조직에서 이 기능을 활성화했는지 여부와 해당 설정에 액세스할 수 있는지 여부를 확인할 수 있습니다.

액세스가 거부된 경우 관리자에게 조직 전체의 기본값과 사용자 또는 그룹 설정을 검토하도록 요청하십시오. Coworker 호환 CX Enterprise 애플리케이션의 경우 해당 애플리케이션에 대해 별도로 관리되는 권한을 확인하도록 요청하십시오.

## 이 항목에 대한 추가 도움말 {#more-help}

동료 및 관리에 대한 자세한 내용은 다음 리소스를 참조하십시오.

* [동료 채팅 개요](/help/chat/overview.md)
* [동료 채팅 시작](/help/chat/ui-guide.md)
* [플러그인 및 마켓 플레이스 관리](/help/customizations/plugins/manage-plugins-for-your-org.md)
