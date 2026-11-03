---
title: Google Ads 외부 커넥터
description: 조직의 CX Enterprise Coworker에서 Google Ads 외부 커넥터를 설정하고 Google으로 로그인하여 채팅에서 Google Ads 데이터를 사용하는 방법에 대해 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 33bbe0ce723fcad4e25353749039c6b81b0dbdf9
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 1%
---

# Google Ads 외부 커넥터 {#google-ads}

[!DNL Google Ads] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL Google Ads] 데이터로 작업하십시오. 커넥터를 설정한 후에는 액세스할 수 있는 광고 계정, 사용 가능한 필드 및 지표, 캠페인의 수행 방법을 동료에게 문의하십시오. 커넥터는 MCP(Model Context Protocol) 서버입니다.

>[!AVAILABILITY]
>
>[!DNL Google Ads] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 두 개의 별도 부품이 있습니다.

* **조직 설정:** 관리자가 전체 조직에 대해 커넥터를 한 번 구성하고 구성원이 사용할 수 있는 도구를 선택합니다. Adobe은 OAuth 애플리케이션을 제공하므로 입력할 앱 자격 증명이 없습니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL Google] 계정으로 로그인합니다. 구성원은 [!DNL Google] 계정이 액세스할 수 있는 [!DNL Google Ads] 계정에만 액세스할 수 있습니다.

조직 구성을 저장해도 구성원이 로그인하지 않거나 [!DNL Google Ads] 계정에 대한 액세스 권한을 부여하지 않습니다. 각 구성원은 개별적으로 로그인해야 합니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **조직 설정의 경우:** Coworker에서 조직 커넥터를 관리할 수 있는 권한이 있는 계정입니다.
* **구성원 로그인:** 사용할 [!DNL Google Ads] 계정에 액세스할 수 있는 [!DNL Google] 계정입니다.

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL Google Ads] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Google 광고]** 카드에서 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

1. **[!UICONTROL 조직에 대한 Google 광고 구성]** 대화 상자에서 **[!UICONTROL OAuth 애플리케이션]**&#x200B;이 **[!UICONTROL Adobe 관리 OAuth 애플리케이션]**&#x200B;인지 확인하십시오. Adobe은 [!DNL Google Ads] 앱을 제공하므로 앱 자격 증명을 입력할 필요가 없습니다. **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 조직에 필요한 도구를 선택합니다. 자세한 내용은 [사용 가능한 도구](#available-tools)를 참조하세요. **[!UICONTROL 각 사용자가 개별적으로 로그인]** 알림을 검토한 다음 **[!UICONTROL 연결 저장]**&#x200B;을 선택하십시오.

   ![Adobe 관리 OAuth 애플리케이션과 함께 조직의 Google 광고 구성 대화 상자, 세 가지 도구를 모두 선택하고 각 사용자는 개별적으로 로그인합니다.](./assets/google-ads/org-configure.png){width="500" zoomable="yes"}

1. 저장된 **[!UICONTROL google-ads]** 커넥터 세부 정보를 검토하십시오.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL Source]** | 사용자 환경의 MCP 서버 URL. |
   | **[!UICONTROL 인증]** | 인증 방법, `google-ads_login`입니다. |
   | **[!UICONTROL 도구 정책]** | 허용된 도구 이름 또는 패턴입니다. |
   | **[!UICONTROL Connection]** | 자신의 로그인 상태입니다. |

   ![원본, 인증 방법, 3개의 사용 가능한 도구를 포함하는 도구 정책 및 로그아웃 및 새로 고침 단추와 관련하여 로그인된 상태를 표시하는 Google-ads 커넥터 세부 정보를 저장했습니다.](./assets/google-ads/org-details.png){width="700" zoomable="yes"}

커넥터 세부 정보의 **[!UICONTROL 연결]** 상태는 조직에 대한 연결이 아니라 사용자 연결을 참조합니다. 모든 회원은 여전히 자신의 계정으로 로그인해야 합니다. 구성원이 로그인한 후 **[!UICONTROL 테스트]**&#x200B;를 선택하여 도구 검색을 테스트할 수 있습니다. 커넥터를 직접 사용하려면 [구성원으로 로그인](#sign-in-as-a-member)의 단계를 따르십시오.

조직에 대한 커넥터 제공을 중지하려면 커넥터 세부 정보 페이지에서 **[!UICONTROL 제거]**&#x200B;를 선택하세요.

### 사용 가능한 도구 {#available-tools}

[!DNL Google Ads] 커넥터는 다음 도구를 제공합니다.

| 도구 | 설명 |
| --- | --- |
| `customers_list_accessible_customers` | 로그인한 [!DNL Google] 계정에서 직접 액세스할 수 있는 고객 ID를 나열합니다. |
| `metadata_get_resource_metadata` | [!DNL Google Ads] 리소스(예: 캠페인 또는 광고 그룹)에 사용할 수 있는 필드, 지표 및 세그먼트를 찾습니다. |
| `search_search` | [!DNL Google Ads] 구성 또는 보고 데이터를 검색합니다. |

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL Google] 계정으로 로그인합니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 사용자]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Google 광고]** 카드에서 **[!UICONTROL 로그인]**&#x200B;을 선택합니다.

   카드에 **[!UICONTROL 구성되지 않음]**&#x200B;이 표시되거나 커넥터를 사용할 수 없는 경우 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오.

1. [!DNL Google] **[!UICONTROL 계정 선택]** 화면에서 [!DNL Google Ads] 계정에 액세스할 수 있는 계정을 선택하거나 **[!UICONTROL 다른 계정 사용]**&#x200B;을 선택합니다. 그런 다음 SSO(Single Sign-On), MFA(Multi-Factor Authentication) 또는 ID 확인과 같이 조직에서 필요로 하는 모든 로그인 단계를 완료합니다.

   단계 및 순서는 조직과 계정 정책에 따라 다릅니다.

   ![Google Adobe Experience Platform의 계정 화면을 선택하여 두 개의 편집된 계정을 나열하고 다른 계정 사용 옵션을 선택합니다.](./assets/google-ads/member-choose-account.png){width="500" zoomable="yes"}

1. 선택한 계정 및 인증 중인 앱을 검토한 다음 **[!UICONTROL 계속]**&#x200B;을 선택합니다.

   [!DNL Google]이(가) 앱 이름을 [!DNL Adobe Experience Platform]&#x200B;(으)로 표시합니다. 이전에 앱을 사용한 경우 [!DNL Google]에 다시 로그인하는 것으로 표시됩니다. 처음 사용하는 사용자에게 서로 다른 프롬프트가 표시될 수 있습니다.

   ![Google 화면에 편집된 계정과 취소 및 계속 단추를 사용하여 Adobe Experience Platform에 다시 로그인하고 있다고 표시됩니다.](./assets/google-ads/member-continue.png){width="500" zoomable="yes"}

1. 액세스 요청을 검토한 다음 **[!UICONTROL 계속]**&#x200B;을 선택합니다.

   ![Adobe Experience Platform에서 편집된 계정을 사용하여 Google 계정에 액세스하려고 한다는 Google 화면, 앱에 이미 일부 액세스 권한이 있다는 알림, 취소 및 계속 단추](./assets/google-ads/member-consent.png){width="500" zoomable="yes"}

   >[!IMPORTANT]
   >
   >앱을 인식하고 조직에서 요청된 액세스를 승인하는 경우에만 계속합니다.

1. [!DNL Google]이(가) Coworker로 돌아간 후 **[!UICONTROL google-ads]** 커넥터 세부 정보를 엽니다. 커넥터에 **[!UICONTROL 연결됨]** 및 **[!UICONTROL 로그인됨]**&#x200B;이 표시되는지 확인하십시오.

   관리자가 다르게 지정하지 않는 한 **[!UICONTROL 리소스 식별자]**&#x200B;을(를) 기본값으로 유지하십시오. 이 필드는 로그인할 때 전송되는 토큰 대상을 설정합니다. 기본값으로 돌아가려면 필드를 지우고 **[!UICONTROL 리소스 식별자 저장]**&#x200B;을(를) 선택하십시오.

   ![연결된 상태, 로그아웃 및 새로 고침 단추와 연결된 로그인 상태 및 리소스 식별자 필드를 표시하는 google-ads 커넥터 세부 정보.](./assets/google-ads/member-connected.png){width="700" zoomable="yes"}

1. **[!UICONTROL 테스트]**&#x200B;를 선택하여 Coworker가 커넥터 도구를 검색할 수 있는지 확인합니다. 그런 다음 **[!UICONTROL 관리자가 활성화한 도구]**&#x200B;를 검토하여 사용할 수 있는 도구를 확인하십시오.

   로그인 후 **[!UICONTROL Test]**&#x200B;을(를) 사용할 수 있습니다.

   ![세 개의 Google 광고 도구와 설명을 나열하는 관리자 섹션에서 사용하도록 설정한 도구입니다.](./assets/google-ads/member-tools.png){width="700" zoomable="yes"}

커넥터에서 [!DNL Google] 계정의 연결을 끊으려면 **[!UICONTROL 로그아웃]**&#x200B;을 선택하세요. 또한 커넥터 세부 정보에 **[!UICONTROL 도구 시간 초과]** 설정 및 **[!UICONTROL 새로 고침]** 컨트롤이 표시됩니다.

**[!UICONTROL 연결됨]** 상태에서는 특정 광고 계정에 대한 액세스를 확인하지 못하거나 모든 보고서가 성공적으로 실행되는지 확인하지 못합니다. 액세스 권한을 확인하려면 [광고 계정 액세스 권한을 확인](#check-ad-account-access)하세요.

## 광고 계정 액세스 확인 {#check-ad-account-access}

사용할 수 있는 [!DNL Google Ads] 계정을 확인하려면 채팅을 시작하고 프롬프트를 입력하십시오.

예제 프롬프트:

* &quot;어떤 Google Ads 계정에 액세스할 수 있습니까?&quot;

동료는 `customers_list_accessible_customers` 도구를 사용하여 [!DNL Google] 계정이 직접 액세스할 수 있는 고객 ID를 나열합니다. 성과 보고서가 아닌 계정 액세스 확인입니다. 관리자 계정을 사용하는 경우 목록에 그 아래에 있는 모든 계정이 포함되지 않습니다.

보고서를 요청하기 전에 다음 작업을 수행하십시오.

* 목록에서 계정을 선택합니다.
* 시작 및 종료 날짜가 포함된 날짜 범위를 지정합니다.
* 동료에게 보고서에 사용할 수 있는 필드 및 지표를 찾으라고 요청하십시오.

## 액세스 문제 해결 {#troubleshoot-access}

[!DNL Google Ads] 데이터에 액세스할 수 없는 경우 관리자에게 다음 사항을 확인하십시오.

| 영역 | 확인할 사항 |
| --- | --- |
| [!DNL Google] 계정 | [!DNL Google Ads] 계정에 액세스할 수 있는 [!DNL Google] 계정으로 로그인했습니다. |
| 계정 권한 | [!DNL Google] 계정에 사용할 [!DNL Google Ads] 계정에 대한 권한이 있습니다. |
| 관리자 계정 | 관리자 계정을 통해 계정에 액세스하는 경우 관리자가 필요한 관리자 계정 설정을 확인했습니다. |
| 도구 선택 | 관리자가 **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 필요한 도구를 활성화했습니다. |
| 리소스 식별자 | 관리자가 다르게 지정하지 않은 경우 **[!UICONTROL 리소스 식별자]**&#x200B;은(는) 기본값을 사용합니다. |
