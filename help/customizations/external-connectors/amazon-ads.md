---
title: Amazon Ads 외부 커넥터
description: 조직의 CX Enterprise Coworker에서 Amazon Ads 외부 커넥터를 설정하고 채팅에서 Amazon Ads 도구를 사용하려면 Amazon으로 로그인하는 방법에 대해 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 80dda0b442d6c7fe560c965b985f58173b73fe13
workflow-type: tm+mt
source-wordcount: '3078'
ht-degree: 1%
---

# Amazon Ads 외부 커넥터 {#amazon-ads}

[!DNL Amazon Ads] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL Amazon Ads] 데이터로 작업하십시오. 커넥터를 설정한 후에는 액세스할 수 있는 광고 계정을 동료에게 질문하고 캠페인, 보고서, 청구 및 기타 계정 정보를 검토하십시오. 커넥터가 [!DNL Amazon]에서 호스트하는 MCP(모델 컨텍스트 프로토콜) 서버입니다.

>[!AVAILABILITY]
>
>[!DNL Amazon Ads] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 세 개의 개별 부품이 있습니다.

* **[!DNL Amazon]준비:** [!DNL Amazon Ads] 계정 관리자는 각 구성원에게 필요한 광고 계정에 대한 액세스 권한을 부여합니다. 조직에서 자체 OAuth 앱을 사용하는 경우 앱 소유자가 승인을 확인하고 Coworker 리디렉션 URL을 등록합니다.
* **조직 설정:** 동료 관리자가 전체 조직에 대해 커넥터를 한 번 구성합니다. 관리자는 지역, OAuth 애플리케이션 및 구성원이 사용할 수 있는 도구를 선택합니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL Amazon] 계정으로 로그인합니다. 구성원은 [!DNL Amazon] 계정에 사용 권한이 있는 광고 계정에만 액세스할 수 있습니다.

조직 구성을 저장해도 구성원에 로그인하거나 [!DNL Amazon Ads] 권한을 부여하지 않습니다. 각 구성원은 [!DNL Amazon Ads]에서 필요한 액세스 권한을 이미 가지고 있어야 하며 별도로 로그인해야 합니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **동료 액세스:** [!DNL Amazon Ads] 커넥터를 사용할 수 있는 조직에서 조직 커넥터를 관리할 수 있는 권한이 있는 계정입니다.
* **Advertising 계정:** 사용할 광고 계정 및 해당 [!DNL Amazon Ads] 지역과 해당 계정에 필요한 권한이 있는 구성원입니다. 자세한 내용은 [광고 계정 액세스 권한 부여](#grant-member-access)를 참조하십시오.
* **OAuth 응용 프로그램 결정:** 다음 옵션 중에서 선택합니다.
  * **Adobe 관리 OAuth 응용 프로그램:** Adobe에서 앱 등록 및 자격 증명을 관리합니다. 관리되는 앱은 사용자 환경에서 사용할 수 있어야 합니다.
  * **자체 OAuth 응용 프로그램:** [!DNL Amazon Ads] API, 해당 OAuth 클라이언트 ID 및 클라이언트 암호와 보안 프로필을 편집할 수 있는 관리자가 승인된 [!DNL Login with Amazon] 앱입니다. 등록된 보안 프로필은 [!DNL Amazon Ads] API 승인을 부여하지 않습니다.

안내식 설정은 조직당 하나의 [!DNL Amazon Ads] 연결과 하나의 지역을 지원합니다. 각 구성원은 자신의 [!DNL Amazon] 계정으로 로그인합니다. Adobe 관리 앱은 공유 [!DNL Amazon] 계정이 아닌 공유 앱 등록입니다.

## Amazon 액세스 준비 {#prepare-amazon}

Coworker에서 커넥터를 구성하기 전에 [!DNL Amazon]에서 앱 및 계정 액세스를 준비하십시오. 앱 설정 액세스와 광고 데이터 액세스는 별개입니다. 커넥터를 사용하는 구성원은 앱을 편집할 권한이 필요하지 않습니다.

### 앱 승인 확인 {#confirm-app-approval}

자체 OAuth 애플리케이션을 사용하는 경우 앱 소유자에게 올바른 [!DNL Login with Amazon] 보안 프로필과 해당 [!DNL Amazon Ads] API 승인을 확인하도록 요청하십시오. 보안 프로필을 만들거나 [!DNL Amazon] 개발자 콘솔에서 앱을 보는 것은 [!DNL Amazon Ads] API 승인을 대체하지 않습니다. 자세한 내용은 [!DNL Amazon Ads] 설명서에서 [Amazon 광고 MCP 시작](https://advertising.amazon.com/API/docs/en-us/mcp/get-started) 및 [OAuth를 사용하여 광고 MCP 서버에 연결](https://advertising.amazon.com/API/docs/en-us/mcp/oauth)을 참조하십시오.

사용자의 앱에 대해 Coworker는 다음 설정을 자동으로 적용합니다. 설정 대화 상자에는 이러한 값을 입력하지 않습니다.

| 설정 | 값 |
| --- | --- |
| 인증 URL | `https://lwa.amazon.com/ap/oa` |
| 토큰 URL | `https://api.amazon.com/auth/o2/token` |
| 요청된 범위 | `advertising::campaign_management` |
| PKCE(Proof Key for Code Exchange) | 활성화됨 |
| 토큰 끝점 클라이언트 인증 | 비밀 클라이언트인 `client_secret_post` |
| 동적 클라이언트 등록 | 지원되지 않음 |
| 전송 및 도구 시간 초과 | 스트리밍 가능 HTTP, 60초 |

Adobe 관리 OAuth 애플리케이션을 사용하는 경우 Adobe에서 앱 등록 및 해당 자격 증명을 관리합니다. 이 단계를 완료하거나 앱 자격 증명을 입력할 필요가 없습니다.

### 리디렉션 URL 등록 {#register-redirect-url}

자체 OAuth 애플리케이션을 사용하는 경우 [!DNL Login with Amazon] 앱에 Coworker 리디렉션 URL을 등록합니다.

1. [조직에 대한 커넥터 구성](#configure-organization)에 설명된 대로 Coworker에서 **[!UICONTROL 조직에 대한 Amazon 광고 구성]** 대화 상자를 엽니다. **[!UICONTROL 내 OAuth 응용 프로그램 사용]**&#x200B;을 선택하여 **[!UICONTROL 리디렉션 URL]**&#x200B;을 표시한 다음 전체 값을 복사합니다.
1. [Amazon 콘솔로 로그인](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html)에서 앱의 보안 프로필을 찾습니다. **[!UICONTROL 관리]** > **[!UICONTROL 웹 설정]**&#x200B;을 선택한 다음 **[!UICONTROL 편집]**&#x200B;을 선택합니다.
1. **[!UICONTROL 허용된 반환 URL]** 아래에 전체 리디렉션 URL을 추가한 다음 저장합니다. 다른 팀이 앱을 공유하는 경우 설정을 변경하기 전에 기존 URL을 유지하고 앱 소유자로부터 승인을 받습니다.
1. 동일한 보안 프로필에서 OAuth 클라이언트 ID 및 클라이언트 암호를 확인합니다. [커넥터를 구성](#configure-organization)할 때 입력하세요.

항상 설정 중인 환경의 Coworker 대화 상자에서 리디렉션 URL을 복사합니다. URL을 직접 작성하거나, 브라우저에서 Coworker 페이지의 URL을 사용하거나, 다른 환경 또는 MCP 클라이언트의 리디렉션 URL을 재사용하지 마십시오. 자세한 내용은 [!DNL Amazon] 설명서의 [Amazon에 로그인 등록](https://developer.amazon.com/docs/login-with-amazon/register-web.html)을 참조하십시오.

>[!NOTE]
>
>**[!UICONTROL 리디렉션 URL]**&#x200B;에 경로 `/connectors/oauth/callback`만 표시되는 경우 환경에서 이 커넥터에 대한 로그인을 아직 지원하지 않습니다. 부분 경로를 등록하거나 호스트 이름을 추측하지 마십시오. Adobe 담당자에게 문의하십시오.

### 광고 계정 액세스 권한 부여 {#grant-member-access}

[!DNL Amazon Ads] 계정 관리자가 각 구성원을 필요한 광고 계정으로 초대합니다.

1. [Amazon 광고 콘솔](https://advertising.amazon.com/)을 연 다음 **[!UICONTROL 계정 변경]**&#x200B;을 선택하여 광고주 또는 관리자 계정을 선택합니다.
1. **[!UICONTROL 관리]** > **[!UICONTROL 계정 액세스 및 설정]** > **[!UICONTROL 사용자]** > **[!UICONTROL 사용자 초대]**&#x200B;를 선택합니다. 정확한 옵션은 계정 유형에 따라 다릅니다. 수행할 작업에 대한 최소 권한으로 구성원의 [!DNL Amazon] 계정을 초대합니다.
1. 관리자 계정의 경우, 액세스 권한이 전체 관리자 계정을 포함하는지 아니면 선택한 연결된 광고주만 포함하는지 확인하십시오. 구성원에게 Coworker에 사용하는 것과 동일한 [!DNL Amazon] 계정으로 초대를 수락하도록 요청하십시오.
1. 구성원이 [!DNL Amazon Ads]에서 광고주를 선택할 수 있는지 확인합니다. 승인된 내부 레코드에서 예상 계정 이름, 지역 및 광고주 ID를 메모하여 나중에 Coworker에서 액세스를 확인할 수 있습니다.

계획한 작업을 지원하는 가장 낮은 권한의 역할을 선택합니다. 액세스 검사에 성공하기 위한 관리자 액세스 권한만 부여하지 마십시오. [!DNL Amazon Marketing Cloud] 인스턴스에 대한 액세스는 광고주 캠페인에 대한 액세스와 별개입니다. 자세한 내용은 다음 [!DNL Amazon Ads] 설명서를 참조하십시오.

* [관리자 계정에서 사용자 관리](https://advertising.amazon.com/help/G4M4JGKGV2VAY9JC)
* [계정에서 사용자 추가 또는 제거](https://advertising.amazon.com/help/GDQVHVQMY9F88PCA)
* [계정 권한 이해](https://advertising.amazon.com/help/GM4EFDQQPG9LGL3F)
* [Amazon Ads API 권한](https://advertising.amazon.com/API/docs/en-us/guides/account-management/permissions)

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL Amazon Ads] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다. 구성원은 **[!UICONTROL 사용자]** 범위에서 조직 연결을 구성할 수 없습니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Amazon 광고]** 카드에서 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

   **[!UICONTROL 조직에 대한 Amazon 광고 구성]** 대화 상자가 열리고 **[!UICONTROL 연결 세부 정보]**, **[!UICONTROL 사용자가 사용할 수 있는 도구]**, **[!UICONTROL 액세스 및 권한]** 섹션이 표시됩니다. 구성을 저장하면 카드에 **[!UICONTROL 구성 저장됨]** 및 **[!UICONTROL 구성 보기]**&#x200B;에 대한 **[!UICONTROL 구성]** 변경 사항이 표시됩니다.

1. **[!UICONTROL Amazon 광고 지역]**&#x200B;에서 광고 계정과 일치하는 지역을 선택합니다. Coworker는 선택 영역 아래 영역에 대한 MCP 서버 URL을 표시합니다.

   | 지역 | MCP 서버 URL |
   | --- | --- |
   | [!UICONTROL 북미]&#x200B;(기본값) | `https://advertising-ai.amazon.com/mcp` |
   | [!UICONTROL 유럽] | `https://advertising-ai-eu.amazon.com/mcp` |
   | [!UICONTROL 극동] | `https://advertising-ai-fe.amazon.com/mcp` |

   안내가 있는 설정이 한 개의 영역을 저장합니다. 나중에 영역을 전환하려면 연결을 제거하고 다시 설정합니다. 그러면 모든 구성원이 다시 로그인해야 하므로 작업 연결을 중단하기 전에 변경 내용을 계획하십시오.

1. **[!UICONTROL OAuth 응용 프로그램 선택]**:

   * **[!UICONTROL Adobe 관리 OAuth 응용 프로그램]:** Adobe에서 [!DNL Amazon Ads] 앱을 제공하므로 앱 자격 증명을 입력할 필요가 없습니다. 각 구성원은 자신의 [!DNL Amazon] 계정으로 로그인하여 Adobe 앱을 승인합니다.

     ![북미 지역, 선택한 Adobe 관리 OAuth 애플리케이션 및 축소된 도구 그룹과 함께 조직 대화 상자에 Amazon Ads를 구성합니다.](./assets/amazon-ads/org-configure.png){width="500" zoomable="yes"}

   * **[!UICONTROL 나만의 OAuth 응용 프로그램 사용]:** 각 구성원은 자신의 [!DNL Amazon] 계정으로 조직 앱을 인증합니다. **[!UICONTROL Amazon 응용 프로그램]**&#x200B;에서 다음 단계를 완료하십시오.

     1. **[!UICONTROL 리디렉션 URL]**&#x200B;이 앱에 등록되어 있는지 확인하십시오. 자세한 내용은 [리디렉션 URL 등록](#register-redirect-url)을 참조하십시오.
     1. **[!UICONTROL Amazon 앱 ID]** 및 **[!UICONTROL Amazon 앱 암호]**&#x200B;를 입력하십시오. **[!UICONTROL Amazon 앱 ID]** 필드는 광고주 ID, 관리자 계정 ID 또는 [!DNL Amazon] 응용 프로그램 ID가 아닌 OAuth 클라이언트 ID를 사용합니다. 동료는 조직 비밀로 입력하는 값을 저장합니다.
     1. 저장된 자격 증명을 대신 다시 사용하려면 **[!UICONTROL 기존 암호 사용]**&#x200B;을 선택하십시오. 그런 다음 **[!UICONTROL 앱 ID를 보유한 암호]** 및 **[!UICONTROL 앱 암호를 보유한 암호]**&#x200B;를 선택합니다. 조직에 아직 암호가 없는 경우 **[!UICONTROL 설정]** > **[!UICONTROL 암호]**&#x200B;에 추가하십시오.

     두 자격 증명이 모두 필요합니다. 보안 필드에만 자격 증명 값을 입력합니다. 일반 값 필드에 비밀 참조를 입력하지 마십시오.

1. **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 각 도구 그룹을 확장하고 조직에 필요한 도구를 선택합니다. 기본적으로 `ads_accounts-list_ads_accounts` 및 `ads_accounts-get_ads_account` 도구만 선택됩니다. 모든 도구를 한 번에 변경하려면 **[!UICONTROL 모두 선택]** 또는 **[!UICONTROL 모두 지우기]**&#x200B;를 사용하세요. 하나 이상의 도구를 선택해야 합니다.

   첫 번째 액세스 검사를 위한 두 가지 계정 도구로 시작합니다. 조직에서 필요로 하고 승인할 때만 캠페인 및 보고 도구를 선택합니다. 자세한 내용은 [도구 그룹](#tool-groups)을 참조하세요.

1. **[!UICONTROL 연결 저장]**&#x200B;을 선택한 다음 저장된 **[!UICONTROL amazon-ads]** 커넥터 세부 사항을 검토하십시오.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL Source]** | 선택한 영역의 MCP 서버 URL입니다. |
   | **[!UICONTROL 인증]** | 인증 방법, `amazon-ads_login`입니다. |
   | **[!UICONTROL 도구 시간 초과]** | 동료가 도구 응답을 기다리는 시간입니다. |
   | **[!UICONTROL Connection]** | 사용 중인 OAuth 애플리케이션 및 고유한 로그인 상태입니다. |
   | **[!UICONTROL 도구]** | **[!UICONTROL 모두 선택]** 및 **[!UICONTROL 지우기]** 컨트롤과 선택한 도구 수가 있는 구성원을 위해 선택된 도구입니다. |

   ![북미 소스, 인증 방법, 로그아웃 및 새로 고침 단추와 관련하여 서명됨, 그리고 47개 도구 중 2개를 표시하는 저장된 amazon-ads 커넥터 세부 정보.](./assets/amazon-ads/org-details.png){width="700" zoomable="yes"}

저장해도 회원님이나 회원이 [!DNL Amazon]에 로그인되지 않습니다. 커넥터 세부 정보의 **[!UICONTROL 연결]** 상태는 조직에 대한 연결이 아니라 사용자 연결을 참조합니다. 연결을 확인하려면 커넥터 세부 정보 페이지에서 **[!UICONTROL 로그인]**&#x200B;을 선택하여 [!DNL Amazon] 계정으로 로그인한 다음 **[!UICONTROL 테스트]**&#x200B;를 선택합니다. 그 결과 도구 또는 오류가 반환되어 **[!UICONTROL 연결 성공]** 또는 **[!UICONTROL 연결 실패]**&#x200B;가 표시됩니다. 성공적인 결과는 특정 광고주 작업에 대한 액세스를 확인하지 않습니다.

나중에 회원이 사용할 수 있는 도구를 변경하려면 **[!UICONTROL 사용 가능한 도구]**&#x200B;의 선택 항목을 **[!UICONTROL 모두 선택]** 또는 **[!UICONTROL 지우기]**(으)로 업데이트한 다음 **[!UICONTROL 도구 선택 항목 저장]**&#x200B;을 선택하십시오. 하나 이상의 도구를 선택한 상태로 유지해야 합니다. 구성원은 도구 선택을 변경할 수 없습니다.

조직에 대한 커넥터 제공을 중지하려면 커넥터 세부 정보 페이지에서 **[!UICONTROL 제거]**&#x200B;를 선택하세요.

### 도구 그룹 {#tool-groups}

[!DNL Amazon Ads] 커넥터는 해당 도구를 다음 그룹으로 구성합니다.

| 도구 그룹 | 도구 | 도구의 기능 |
| --- | --- | --- |
| [!UICONTROL 캠페인 관리 및 타깃팅] | 7 | 캠페인, 광고 그룹, 광고, 타겟, 포트폴리오 및 연결을 쿼리하고 제품 적격성을 확인합니다. |
| [!UICONTROL 계정 및 조직] | 6 | 광고 계정을 나열 및 가져오고, 광고주와 계정 링크, 관리자 계정 및 테스트 계정을 쿼리합니다. |
| [!UICONTROL 사용자 액세스 및 보안] | 5 | 사용자, 역할, 권한 및 초대를 나열하고 초대를 받습니다. |
| [!UICONTROL 보고 및 분석] | 1 | 보고서를 검색합니다. 보고서 생성은 포함되지 않습니다. |
| [!UICONTROL Amazon Marketing Cloud] | 6 | 워크플로우 및 데이터 소스, 기존 실행의 상태 및 다운로드 URL을 읽습니다. 워크플로우 실행은 포함되지 않습니다. |
| [!UICONTROL 청구 및 재무 요약] | 4 | 송장, 송장 요약, 청구 프로필 사용 및 청구 알림을 읽어 보십시오. |
| [!UICONTROL Amazon Live] | 12 | 채널, 브로드캐스트, 라이브스트림, 미디어, 회전 메뉴 및 프로모션 코드 정보를 읽어 보십시오. |
| [!UICONTROL 자격 및 오퍼] | 6 | 프로그램 및 제품 자격, 프로모션 오퍼와 보상, 약관 토큰 정보를 읽어 보십시오. |

[!DNL Amazon]이(가) 커넥터를 업데이트할 때 각 그룹의 도구를 변경할 수 있습니다. 안내식 설정은 모든 도구를 선택하는 경우에도 선택하는 정확한 도구 목록을 저장합니다. 선택하지 않은 상태로 둔 도구 및 나중에 서버에서 추가하는 도구는 선택할 때까지 구성원이 사용할 수 없습니다.

>[!IMPORTANT]
>
>설정 도구 목록은 데이터를 읽기 위해 조정되지만 커넥터는 전체적으로 읽기 전용이 아닙니다. 구성원은 설정 목록보다 광범위한 `advertising::campaign_management` 범위를 승인합니다. 연결을 테스트할 때 도구 목록에는 서버가 반환하는 도구도 포함될 수 있습니다. 더 많은 도구를 선택하기 전에 각 도구 정의 및 구성원의 [!DNL Amazon Ads] 권한을 검토하십시오.

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL Amazon] 계정으로 로그인합니다. 로그인하기 위해 앱 비밀 또는 액세스 토큰이 필요하지 않습니다.

>[!NOTE]
>
>커넥터에서 로그인 및 **[!UICONTROL Test]**&#x200B;을(를) 사용자 환경에서 아직 사용할 수 없다고 표시하면 여기에서 중지하십시오. 조직 구성만으로는 구성원 로그인을 사용할 수 없습니다. Adobe 담당자에게 문의하십시오.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 사용자]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Amazon 광고]** 카드를 찾습니다.

1. 카드에 **[!UICONTROL 구성되지 않음]**&#x200B;이 표시되면 관리자에게 [커넥터 구성](#configure-organization)을 요청하십시오. 구성원이 커넥터를 구성할 수 없습니다.

1. 카드에 **[!UICONTROL 로그인되지 않음]**&#x200B;이 표시되면 **[!UICONTROL 로그인]**&#x200B;을 선택하세요. 로그인 팝업을 허용한 다음 광고 계정에 액세스할 수 있는 [!DNL Amazon] 계정으로 로그인합니다.

1. MFA(Multi-Factor Authentication) 및 동의 프롬프트와 같은 [!DNL Amazon] 인증 프롬프트를 완료하십시오. 승인하기 전에 앱 이름 및 요청된 액세스 권한을 검토하십시오.

   Adobe 관리 앱을 사용하면 Adobe 앱을 인증할 수 있습니다. 조직 앱을 사용하면 대신 해당 앱을 승인하게 됩니다.

   >[!IMPORTANT]
   >
   >앱을 인식하고 조직에서 요청된 액세스를 승인하는 경우에만 계속합니다.

1. Coworker로 돌아가서 카드에 **[!UICONTROL 로그인]**&#x200B;이 표시되는지 확인하십시오. **[!UICONTROL 세부 정보 보기]**&#x200B;를 선택한 다음 **[!UICONTROL 관리자가 활성화한 도구]**&#x200B;를 검토하세요. 구성원은 도구를 볼 수 있지만 도구를 변경하거나 조직 연결을 제거할 수 없습니다.

1. 도구 검색 및 연결 상태를 확인하려면 **[!UICONTROL 테스트]**&#x200B;를 선택하세요.

닫은 팝업만으로는 로그인이 성공했음을 확인할 수 없습니다. 테스트가 성공해도 모든 광고주, 캠페인, 보고서 또는 [!DNL Amazon Marketing Cloud] 인스턴스에 대한 액세스가 확인되지 않습니다. 관리자가 로그인하면 다른 구성원은 로그인되지 않습니다.

커넥터에서 [!DNL Amazon] 계정의 연결을 끊으려면 **[!UICONTROL 로그아웃]**&#x200B;을 선택하세요.

## 광고 계정 액세스 확인 {#check-account-access}

사용할 수 있는 광고 계정을 확인하려면 읽기 전용 검사를 실행하십시오. 승인된 테스트 계정을 사용하고 관리자가 `ads_accounts-list_ads_accounts` 및 `ads_accounts-get_ads_account` 도구를 사용하도록 설정했는지 확인하십시오. 그런 다음 채팅을 시작하고 프롬프트를 입력하십시오.

예제 프롬프트:

* &quot;Amazon 광고를 사용하여 구성된 영역에서 액세스할 수 있는 광고 계정을 최대 5개까지 나열합니다. 계정 이름, 계정 ID 및 해당 필드가 반환되는 경우 지역만 표시합니다. 워크플로우를 작성, 업데이트, 삭제, 실행, 보고서 생성 또는 변경하지 마십시오. 목록 제한이 지원되지 않는 경우 5개의 결과만 요약하고 추가 페이지를 요청하지 마십시오.&quot;

결과에 예상한 계정이 포함되어 있는지 확인합니다. 자세한 내용을 보려면 결과에서 계정 ID를 사용하여 Coworker에 해당 계정에 대한 세부 정보를 가져오도록 요청하십시오. 계정 ID를 추측하지 말고, 로그인을 테스트하기 위한 캠페인만 요청하지 마십시오.

계정 목록이 비어 있다고 해서 항상 커넥터가 작동하지 않는 것은 아닙니다. 로그인한 [!DNL Amazon] 계정, 초대를 수락한 사용자, 관리자 계정이 다루는 연결된 광고주 및 구성된 지역을 확인합니다. 캠페인이 없는 테스트 계정은 빈 캠페인 목록을 반환할 수도 있습니다. 필요한 도구가 활성화되지 않은 경우 관리자에게 문의하십시오. 데이터를 변경하는 도구를 대용으로 사용하지 마십시오.

## 액세스 문제 해결 {#troubleshoot-access}

[!DNL Amazon Ads] 데이터에 액세스할 수 없는 경우 관리자에게 다음 사항을 확인하십시오.

| 문제 | 확인할 사항 |
| --- | --- |
| **[!UICONTROL Amazon 광고]** 카드 또는 **[!UICONTROL 구성]**&#x200B;이 없습니다. | 조직에서 커넥터를 사용할 수 있으며 조직 커넥터를 관리할 권한이 있는지 확인하십시오. 구성원은 조직 설정을 기다려야 합니다. |
| Adobe 관리 설정이 저장되지만 로그인에 실패합니다 | Adobe 담당자에게 문의하여 현재 환경에서 Adobe 관리 앱을 사용할 수 있는지 확인하십시오. 저장이 성공해도 이를 확인하지 않습니다. |
| 리디렉션 URL이 일치하지 않습니다. | Coworker 대화 상자의 전체 **[!UICONTROL 리디렉션 URL]**&#x200B;을(를) [!DNL Login with Amazon]의 **[!UICONTROL 허용된 반환 URL]**&#x200B;과(와) 비교합니다(체계, 호스트 및 경로 포함). 다른 MCP 클라이언트, 지역 또는 환경의 리디렉션 URL 또는 브라우저에 있는 Coworker 페이지의 URL을 사용하지 마십시오. |
| **[!UICONTROL 리디렉션 URL]**&#x200B;에 `/connectors/oauth/callback`만 표시됩니다. | 환경에 전체 리디렉션 URL이 아직 표시되지 않거나 로그인 및 **[!UICONTROL 테스트]**&#x200B;를 지원합니다. 부분 경로를 등록하거나 호스트 이름을 추측하지 마십시오. Adobe 담당자에게 문의하십시오. |
| 자신의 OAuth 앱 설정을 저장할 수 없습니다. | OAuth 클라이언트 ID와 클라이언트 암호를 모두 입력하고 하나 이상의 도구를 선택한 상태로 유지합니다. **[!UICONTROL Amazon 앱 ID]**&#x200B;이(가) 광고주 ID 또는 [!DNL Amazon] 응용 프로그램 ID가 아닌 OAuth 클라이언트 ID인지 확인하십시오. |
| 동의 또는 앱 인증 실패 | 동의 화면에 표시된 [!DNL Amazon Ads] API 승인, 보안 프로필, 클라이언트 ID 및 암호 연결, 리디렉션 URL 등록 및 앱을 확인합니다. 도움을 요청할 때 동의 URL, 인증 코드 또는 토큰을 공유하지 마십시오. |
| 로그인하지만 계정 또는 도구가 거부되거나 비어 있습니다. | 로그인한 [!DNL Amazon] 계정, 초대를 수락한 사용자, 관리자 계정이 다루는 연결된 광고주, 구성된 영역 및 작업에 필요한 권한을 확인합니다. 앱 또는 파트너 도구에 대한 액세스는 광고주 액세스를 확인하지 않습니다. [!DNL Amazon Marketing Cloud] 액세스는 별개입니다. |
| [!DNL Amazon Ads]이(가) 현재 계정에서 페이지에 액세스할 수 없다고 합니다. | **[!UICONTROL 계정 변경]**&#x200B;을 선택하고 광고주 또는 관리자 계정을 선택하십시오. 계정이 누락된 경우 관리자에게 초대를 수락했는지, 그리고 계정에 할당되었는지 확인하도록 요청하십시오. 계정이 있지만 사용자 관리를 사용할 수 없는 경우 관리자에게 역할 확인을 요청하십시오. |
| 도구가 없거나 사용할 수 없습니다. | 조직의 도구 선택, 서버가 반환하는 도구 및 [!DNL Amazon Ads] 권한을 확인합니다. 서버가 나중에 추가하는 도구는 자동으로 선택되지 않습니다. 기본적으로 두 개의 계정 도구만 활성화됩니다. |
| **[!UICONTROL Test]**&#x200B;에서 이름이 같은 개인 커넥터를 보고합니다. | 같은 이름의 개인 커넥터가 조직 커넥터보다 우선할 수 있습니다. 표시된 지침에 따라 소유자의 승인을 받아 충돌하는 개인 커넥터만 제거하거나 이름을 변경합니다. |
| 로그인 팝업이 차단되거나 완료되지 않거나 상태가 업데이트되지 않습니다 | 팝업을 허용한 다음 Coworker로 돌아가서 상태 및 오류 세부 정보를 확인합니다. 팝업이 닫혔거나 랜딩 페이지를 표시했기 때문에 성공했다고 가정하지 마십시오. |
| 도구가 시간 초과되거나 반복해서 로그인해야 합니다. | 60초 **[!UICONTROL 도구 시간 초과]**, 오류 세부 정보, 네트워크 및 [!DNL Amazon] 사용 가능 여부, 앱 구성을 확인합니다. |
| 동료가 설정을 사용할 수 없거나 새 암호가 아직 설정 중이라고 합니다. | Adobe 담당자에게 상태를 확인합니다. 자격 증명을 다시 반복적으로 생성하지 말고, 실패한 저장을 성공으로 간주하지 마십시오. |

지원에 문의할 때는 오류 텍스트, 오류 시간, 환경, 선택한 영역 및 OAuth 애플리케이션 옵션만 포함하십시오. 앱 비밀, 액세스 토큰, 인증 코드, 인증 헤더, 동의 또는 리디렉션 쿼리 매개 변수 또는 고객 계정 데이터를 공유하지 마십시오.
