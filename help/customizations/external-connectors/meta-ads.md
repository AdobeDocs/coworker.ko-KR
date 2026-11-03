---
title: Meta Ads 외부 커넥터
description: 조직의 CX Enterprise Coworker에서 Meta Ads 외부 커넥터를 설정하고 Facebook으로 로그인하여 채팅에서 Meta Ads 도구를 사용하는 방법에 대해 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: d02ad688d14fef6e20f1a60f618fe4c0c7938e63
workflow-type: tm+mt
source-wordcount: '1439'
ht-degree: 1%
---

# Meta Ads 외부 커넥터 {#meta-ads}

[!DNL Meta Ads] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL Meta] 광고 데이터를 사용합니다. 커넥터를 설정한 후에는 Coworker에 광고 성과에 대한 보고, 캠페인 및 대상 관리, 제품 카탈로그 작업 등을 요청합니다. 커넥터가 [!DNL Meta]에서 호스트하는 MCP(모델 컨텍스트 프로토콜) 서버입니다.

>[!AVAILABILITY]
>
>[!DNL Meta Ads] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 두 개의 별도 부품이 있습니다.

* **조직 설정:** 관리자가 전체 조직에 대해 커넥터를 한 번 구성합니다. 관리자는 OAuth 애플리케이션을 선택하고 구성원이 사용할 수 있는 도구를 선택합니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL Facebook] 계정으로 로그인합니다. 구성원은 [!DNL Facebook] ID 및 승인된 앱에서 허용하는 [!DNL Meta] 자산에만 액세스할 수 있습니다.

조직 구성을 저장해도 구성원이 로그인하거나 광고 계정에 대한 액세스 권한이 부여되지 않습니다. 각 구성원은 개별적으로 로그인해야 합니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **조직 설정의 경우:** Coworker에서 조직 커넥터를 관리할 수 있는 권한이 있는 계정입니다.
* **구성원 로그인:** 사용할 광고 계정, 회사, 페이지 또는 기타 [!DNL Meta] 자산에 액세스할 수 있는 [!DNL Facebook] 계정입니다.
* **자체 OAuth 앱의 경우(선택 사항):** 조직에서 관리하는 [!DNL Meta] 앱과 해당 앱 ID 및 앱 비밀.

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL Meta Ads] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Meta 광고]** 카드에서 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

1. **[!UICONTROL 조직에 대한 Meta 광고 구성]** 대화 상자에서 **[!UICONTROL 연결 세부 정보]**&#x200B;를 검토한 다음 **[!UICONTROL OAuth 애플리케이션]**&#x200B;을 선택하십시오.

   * **[!UICONTROL Adobe 관리 OAuth 응용 프로그램]:** Adobe에서 [!DNL Meta Ads] 앱을 제공하므로 앱 자격 증명을 입력할 필요가 없습니다. 저장한 후에도 각 구성원은 여전히 자신의 [!DNL Facebook] 계정으로 로그인합니다.

     ![선택한 Adobe 관리 OAuth 애플리케이션과 축소된 도구 그룹이 있는 조직의 Meta 광고 구성 대화 상자입니다.](./assets/meta-ads/org-managed-oauth.png){width="500" zoomable="yes"}

   * **[!UICONTROL 내 OAuth 응용 프로그램 사용]:** 조직에서 자체 [!DNL Meta] 앱을 제공합니다. 구성원은 Adobe 앱이 아니라 사용자의 앱을 승인합니다. **[!UICONTROL Meta 응용 프로그램]**&#x200B;에서 다음 단계를 완료하십시오.

     1. **[!UICONTROL 리디렉션 URL]**&#x200B;을(를) 복사하여 [!DNL Meta] 앱의 로그인 설정에 추가하십시오. 리디렉션 URL이 환경마다 다르므로 대화 상자에 표시된 정확한 값을 사용합니다.
     1. **[!UICONTROL 자격 증명의 출처]**&#x200B;에서 **[!UICONTROL 새로 입력]**&#x200B;을 선택한 다음 **[!UICONTROL Meta 앱 ID]** 및 **[!UICONTROL Meta 앱 암호]**&#x200B;를 입력하십시오. [!DNL Meta] 앱의 기본 설정에서 앱 ID를 찾습니다. 동료는 앱 암호를 조직 암호로 저장합니다. 같은 앱에 대해 저장된 자격 증명을 대신 다시 사용하려면 **[!UICONTROL 기존 암호 사용]**&#x200B;을 선택하십시오.
     1. 로그인할 구성원이 앱을 사용할 수 있도록 합니다. [!DNL Meta] 앱 관리자에게 문의하여 필요한 권한과 의도한 사용에 대한 모든 앱 검토 요구 사항을 확인하십시오.

     **[!UICONTROL MCP 서버에서 검색됨]** 표시기가 Coworker에서 커넥터를 발견했음을 확인합니다. 앱 자격 증명이 유효한지 또는 구성원이 로그인했는지 확인하지 않습니다. 검색을 새로 고치려면 **[!UICONTROL 다시 검색]**&#x200B;을 선택하세요.

     ![리디렉션 URL, Meta 앱 ID 및 Meta 앱 비밀 필드, MCP 서버 표시기에서 검색됨 등을 표시하는 [내 OAuth 응용 프로그램 사용]을 선택한 상태로 조직에 대한 Meta Ads 대화 상자를 구성합니다.](./assets/meta-ads/org-own-oauth.png){width="500" zoomable="yes"}

1. **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 각 도구 그룹을 확장하고 조직에 필요한 도구를 선택합니다. 모든 도구를 한 번에 변경하려면 **[!UICONTROL 모두 선택]** 또는 **[!UICONTROL 모두 지우기]**&#x200B;를 사용하세요. 자세한 내용은 [도구 그룹](#tool-groups)을 참조하세요. 그런 다음 **[!UICONTROL 연결 저장]**&#x200B;을 선택합니다.

   ![보고 및 통찰력 도구 그룹을 확장하고 7개의 도구를 모두 선택한 상태로 조직에 대한 Meta 광고 구성 대화 상자를 엽니다.](./assets/meta-ads/org-reporting-tools.png){width="500" zoomable="yes"}

1. 저장된 **[!UICONTROL meta-ads]** 커넥터 세부 사항을 검토하십시오. 선택적으로 **[!UICONTROL 테스트]**&#x200B;를 선택하여 Coworker가 커넥터 도구를 검색할 수 있는지 확인합니다.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL Source]** | [!DNL Meta Ads] MCP 서버, `https://mcp.facebook.com/ads`. |
   | **[!UICONTROL 인증]** | 인증 방법, `meta-ads_login`입니다. |
   | **[!UICONTROL Connection]** | 사용 중인 OAuth 애플리케이션 및 고유한 로그인 상태입니다. |
   | **[!UICONTROL 도구]** | **[!UICONTROL 모두 선택]** 및 **[!UICONTROL 지우기]** 컨트롤과 선택한 도구 수가 있는 구성원을 위해 선택된 도구입니다. |

   ![소스, 인증 방법, 로그인 단추와 관련하여 로그인되지 않음 및 도구 선택을 표시하는 저장된 메타 광고 커넥터 세부 정보.](./assets/meta-ads/org-details.png){width="700" zoomable="yes"}

커넥터 세부 정보에 대한 **[!UICONTROL 로그인되지 않음]** 상태는 조직이 아니라 사용자 연결을 참조합니다. 커넥터를 직접 사용하려면 **[!UICONTROL 로그인]**&#x200B;을 선택하고 [구성원으로 로그인](#sign-in-as-a-member)의 단계를 따릅니다.

조직에 대한 커넥터 제공을 중지하려면 커넥터 세부 정보 페이지에서 **[!UICONTROL 제거]**&#x200B;를 선택하세요.

### 도구 그룹 {#tool-groups}

[!DNL Meta Ads] 커넥터는 해당 도구를 다음 그룹으로 구성합니다.

* [!UICONTROL 보고 및 인사이트]
* [!UICONTROL 광고, 캠페인 및 대상자]
* [!UICONTROL 카탈로그 및 제품]
* [!UICONTROL 신호 및 데이터 세트]
* [!UICONTROL A/B 테스트 및 리프트 연구]
* [!UICONTROL 활동 로그]
* [!UICONTROL 도움말 및 문제 해결]

예를 들어 [!UICONTROL 보고 및 인사이트] 그룹에는 `ads_insights_performance_trend` 및 `ads_insights_industry_benchmark` 등의 도구가 포함되어 있습니다. [!DNL Meta]이(가) 커넥터를 업데이트할 때 각 그룹의 도구를 변경할 수 있습니다.

>[!IMPORTANT]
>
>모든 도구가 읽기 전용은 아닙니다. 일부 도구는 캠페인, 예산, 대상, 카탈로그 또는 기타 광고 자산을 변경할 수 있습니다. 조직 구성원이 사용하려는 도구만 선택합니다.

저장한 후 선택하지 않은 상태로 둔 도구는 선택할 때까지 구성원이 사용할 수 없습니다. 구성원이 사용할 수 있는 도구를 확인하려면 커넥터 세부 정보 페이지의 **[!UICONTROL 사용 가능한 도구]** 섹션을 검토하십시오.

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL Facebook] 계정으로 로그인합니다. 로그인하기 위해 앱 비밀 또는 액세스 토큰이 필요하지 않습니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 사용자]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다.

1. **[!UICONTROL Meta 광고]** 카드에서 **[!UICONTROL 로그인]**&#x200B;을 선택합니다.

   카드에 **[!UICONTROL 구성되지 않음]**&#x200B;이 표시되거나 커넥터를 사용할 수 없는 경우 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오.

1. [!DNL Facebook]에 로그인하고 SSO(Single Sign-On), MFA(Multi-Factor Authentication), 동의 또는 신원 확인과 같은 필수 프롬프트를 완료하십시오.

   이러한 프롬프트의 순서는 계정 및 조직 정책에 따라 다릅니다. 처음 사용하는 사용자에게 권한을 부여하고 에셋을 선택하는 프롬프트가 표시될 수도 있습니다.

1. [!DNL Facebook] 계정 및 인증 중인 앱을 검토한 후 다음 중 하나를 수행합니다.

   * 이전 설정을 유지하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.
   * 인증을 검토하거나 변경하려면 **[!UICONTROL 설정 편집]**&#x200B;을 선택하세요.
   * 다른 [!DNL Facebook] 계정을 사용하려면 **[!UICONTROL 다른 계정에 로그인]**&#x200B;을 선택하세요.

   Adobe 관리 앱을 사용하여 [!DNL Adobe Experience Cloud]을(를) 승인합니다. 조직 앱의 경우 앱 이름과 프롬프트가 다릅니다.

   ![이전에 Adobe Experience Cloud에 연결한 재방문 사용자의 경우, 계정 이름 및 설정 편집, 계속, 다른 계정 로그인 옵션에 대해 Facebook Continue as screen을 표시합니다.](./assets/meta-ads/member-facebook-continue.png){width="400" zoomable="yes"}

   >[!IMPORTANT]
   >
   >앱은 사용자가 공유하는 정보에 대한 지속적인 액세스를 받으며, 앱이 해당 정보에 액세스할 때 [!DNL Meta]이(가) 기록합니다. 조직에서 요청된 액세스를 승인하는 경우에만 계속합니다.

1. [!DNL Facebook]이(가) Coworker로 돌아간 후 **[!UICONTROL meta-ads]** 커넥터 세부 정보를 엽니다. 커넥터에 **[!UICONTROL 연결됨]** 및 **[!UICONTROL 로그인됨]**&#x200B;이 표시되는지 확인하십시오.

   ![연결된 상태, 60초 도구 시간 제한, 로그아웃 및 다시 로드 도구 단추와 연결된 로그인, 관리자가 사용하도록 설정한 도구를 보여주는 meta-ads 커넥터 세부 정보.](./assets/meta-ads/member-connected.png){width="700" zoomable="yes"}

1. 사용할 수 있는 도구를 보려면 **[!UICONTROL 관리자가 사용하도록 설정한 도구]**&#x200B;를 검토하세요.

또한 커넥터 세부 정보에 **[!UICONTROL 도구 시간 초과]** 설정과 다음 컨트롤이 표시됩니다.

* **[!UICONTROL 도구 다시 로드]:** 도구 목록을 새로 고칩니다.
* **[!UICONTROL 테스트]:** Coworker에서 커넥터 도구를 검색할 수 있는지 확인합니다.
* **[!UICONTROL 로그아웃]:** 커넥터에서 [!DNL Facebook] 계정의 연결을 끊습니다.

**[!UICONTROL 연결됨]** 상태에서는 특정 광고 계정에 대한 액세스를 확인하지 못하거나 모든 도구가 성공적으로 실행되는지 확인하지 못합니다. 액세스 권한을 확인하려면 [광고 계정 액세스 권한을 확인](#check-ad-account-access)하세요.

## 광고 계정 액세스 확인 {#check-ad-account-access}

사용할 수 있는 광고 계정을 확인하려면 채팅을 시작하고 읽기 전용 프롬프트를 입력하십시오.

예제 프롬프트:

* &quot;어떤 Meta 광고 계정에 액세스할 수 있습니까? 아무것도 변경하지 않고 나열하십시오.&quot;

관리자가 `ads_get_ad_accounts` 도구를 사용하도록 설정한 경우 Coworker는 액세스할 수 있는 광고 계정을 나열합니다. 각 계정에 대해 Coworker는 소유 비즈니스, MCP 자격 요건 및 보고 가용성을 보여줍니다. 보고서를 요청하거나 작업을 수행하기 전에 액세스 가능한 계정을 선택하십시오.

## 액세스 문제 해결 {#troubleshoot-access}

[!DNL Meta] 자산에 액세스할 수 없는 경우 다음을 확인하십시오.

| 영역 | 확인할 사항 |
| --- | --- |
| [!DNL Facebook] 계정 | 광고 계정에 액세스할 수 있는 [!DNL Facebook] 계정으로 로그인했습니다. |
| 에셋 권한 | [!DNL Facebook] 계정에 사용할 광고 계정, 회사 또는 페이지에 대한 권한이 있습니다. |
| 앱 인증 | 앱을 승인하고 필요한 에셋을 공유했습니다. 인증을 검토하려면 로그아웃했다가 다시 로그인한 다음 **[!UICONTROL 설정 편집]**&#x200B;을 선택하십시오. |
| 활성화된 도구 | 관리자가 **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 필요한 도구를 활성화했습니다. |
| 자신의 OAuth 앱 | 리디렉션 URL이 정확히 일치하고, 앱 ID와 앱 암호가 정확하며, 구성원이 앱에 액세스할 수 있습니다. [!DNL Meta] 앱 관리자에게 필요한 권한을 확인하십시오. |
