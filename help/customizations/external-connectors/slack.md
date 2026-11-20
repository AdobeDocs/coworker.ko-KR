---
title: Slack 외부 커넥터
description: Slack 앱을 사용하여 CX Enterprise Coworker에서 Slack 외부 커넥터를 설정하는 방법을 배우고, 로그인하여 채팅에서 Slack 대화를 사용하는 방법을 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Slack 외부 커넥터 {#slack}

[!DNL Slack] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL Slack] 대화와 함께 작업하십시오. 커넥터를 설정한 후 Coworker에게 메시지와 파일을 검색하고, 채널과 스레드를 읽고, 사람을 찾으라고 요청합니다. 관리자가 이러한 도구를 활성화한 경우 메시지와 답글을 보낼 수도 있습니다. 커넥터가 [!DNL Slack]에서 호스팅하는 공식 원격 MCP(Model Context Protocol) 서버를 사용합니다.

>[!AVAILABILITY]
>
>[!DNL Slack] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 세 개의 개별 부품이 있습니다.

* **[!DNL Slack]앱 준비:** [!DNL Slack] 앱의 소유자가 적격 앱을 준비하고 Coworker 리디렉션 URL을 등록하며 사용자 범위를 설정합니다. Adobe에서 관리되는 [!DNL Slack] 앱을 제공하지 않습니다.
* **조직 설정:** 동료 관리자가 전체 조직에 대해 커넥터를 한 번 구성합니다. 관리자는 앱 자격 증명을 입력하고 사용자 OAuth 범위 및 구성원이 사용할 수 있는 도구를 선택합니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL Slack] 계정으로 로그인합니다. 구성원은 [!DNL Slack] 계정이 액세스할 수 있는 콘텐츠에만 액세스할 수 있습니다.

커넥터가 공유 봇 또는 공유 [!DNL Slack] ID를 사용하지 않습니다. 동료가 로그인한 구성원으로 메시지와 회신을 보냅니다. 조직 구성을 저장해도 어떤 구성원도 로그인하지 않거나 [!DNL Slack] 액세스 권한을 추가로 부여하지 않습니다. 각 구성원은 개별적으로 로그인해야 합니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **동료 액세스:** [!DNL Slack] 커넥터를 사용할 수 있는 조직에서 조직 커넥터를 관리할 수 있는 권한이 있는 계정입니다.
* **작업 영역에 대해 승인된 [!DNL Slack] 앱:** 내부 앱 또는 [!DNL Slack Marketplace] 앱입니다. 승인된 사용자 범위를 확인하고 앱 설정을 편집할 수 있는 앱 소유자도 필요합니다.
* **앱 자격 증명:** 자격 증명을 처리하기 위해 승인된 프로세스를 통해 공유되는 앱의 클라이언트 ID 및 클라이언트 암호입니다.
* **도구 및 범위 결정:** 조직에서 사용하도록 설정할 읽기, 메시징 및 초안 도구와 요청한 사용자 OAuth 범위입니다.
* **테스트 작업 영역 또는 채널:** 테스트에 동의한 구성원과의 연결을 확인할 수 있는 위치입니다. 고객 또는 프로덕션 채널에서는 테스트 메시지를 보내지 마십시오.

>[!IMPORTANT]
>
>스크린샷, 채팅 또는 지원 티켓에서 클라이언트 암호, 액세스 토큰 또는 기타 자격 증명을 공유하지 마십시오. 설정 대화 상자의 보안 필드에만 자격 증명을 입력합니다.

## Slack 앱 준비 {#prepare-slack-app}

Coworker에서 커넥터를 구성하기 전에 앱 소유자가 [!DNL Slack] 앱을 준비합니다. 작업 영역 또는 조직 앱 관리자도 승인해야 할 수 있습니다. [!DNL Slack] 요구 사항에 대해서는 [!DNL Slack] 개발자 설명서에서 [Slack MCP 서버](https://docs.slack.dev/ai/slack-mcp-server/)를 참조하십시오.

### 적합한 앱 선택 {#choose-eligible-app}

[!DNL Slack]은(는) [!DNL Slack Marketplace]에 게시된 내부 사용자 지정 앱 및 앱에 대해서만 MCP 서버를 지원합니다. 조직 외부에 배포된 목록에 없는 앱은 [!DNL Slack] MCP 서버를 사용할 수 없습니다. 공개 배포를 켜는 것만으로는 앱을 사용할 수 없습니다.

1. 앱을 소유할 작업 영역 또는 조직과 앱 소유자를 선택합니다.
1. [Slack 앱 관리](https://api.slack.com/apps)에서 해당 작업 영역에 새 앱을 만듭니다. 기존의 적격 앱을 재사용하려면 먼저 소유자로부터 승인을 받으십시오.
1. 앱 설정에서 **[!UICONTROL 기본 정보]** > **[!UICONTROL 앱 자격 증명]**&#x200B;을 선택합니다. **[!UICONTROL 클라이언트 ID]** 및 **[!UICONTROL 클라이언트 암호]**&#x200B;를 참조하세요.

   Coworker에 이 두 값만 입력합니다. 앱 ID, 서명 암호, 보트 토큰 또는 앱 수준 토큰을 사용하지 마십시오.

### 리디렉션 URL 등록 {#register-redirect-url}

[!DNL Slack] 앱에서 Coworker 리디렉션 URL을 등록합니다.

1. [조직에 대한 커넥터 구성](#configure-organization)에 설명된 대로 Coworker에서 **[!UICONTROL Slack 연결]** 대화 상자를 엽니다. **[!UICONTROL 리디렉션 URL]**&#x200B;의 전체 값을 복사합니다.

   구성을 완료하거나 저장하기 전에 대화 상자를 열어 URL을 복사할 수 있습니다.

1. [!DNL Slack] 앱 설정에서 **[!UICONTROL OAuth 및 권한]**&#x200B;을 선택합니다. **[!UICONTROL 리디렉션 URL]**&#x200B;에서 전체 리디렉션 URL을 추가한 다음 저장합니다.

항상 설정 중인 환경의 Coworker 대화 상자에서 리디렉션 URL을 복사합니다. 정확한 체계, 호스트 이름, 포트(있는 경우) 및 경로를 등록합니다. URL을 직접 작성하거나 다른 환경의 리디렉션 URL을 재사용하지 마십시오. 두 개 이상의 환경을 사용하는 경우 각 리디렉션 URL을 별도로 등록합니다.

### 사용자 범위 설정 {#set-user-scopes}

커넥터는 각 멤버의 계정을 승인하는 사용자 OAuth 범위를 사용합니다. 봇 범위를 사용하지 않습니다.

1. [!DNL Slack] 앱 설정에서 **[!UICONTROL OAuth 및 권한]** > **[!UICONTROL 범위]** > **[!UICONTROL 사용자 토큰 범위]**&#x200B;를 선택합니다.
1. 조직에서 승인하는 사용자 범위를 추가합니다. Coworker의 [기본 범위](#review-scopes)와 비교하고 요청하려는 범위만 추가하십시오.

   기본 범위는 [!DNL Slack]에 필요한 최소 범위가 아니라 Coworker의 기본 기능 집합입니다. 이전 `search:read` 범위가 아닌 세분화된 `search:read.*` 범위를 사용하십시오. 앱 매니페스트에서 사용자 범위는 `oauth_config.scopes.bot`이(가) 아닌 `oauth_config.scopes.user`에 속합니다.

`chat:write` 사용자 범위를 사용하면 Coworker가 로그인한 구성원으로 메시지를 보낼 수 있습니다. 조직에서 메시지를 보낼 계획이 없는 경우 제외합니다.

작업 영역 또는 [!DNL Slack] 엔터프라이즈 조직에는 앱 승인 및 범위 검토가 필요할 수 있습니다. 앱 승인이 각 구성원의 동의를 대체하지는 않습니다. [!DNL Slack Marketplace]개 앱만 허용하는 정책이 내부 앱을 차단할 수 있습니다. 자세한 내용은 [작업 영역에 대한 앱 승인 관리](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace)를 참조하십시오.

앱에서 허용된 IP 주소 제한을 사용하는 경우 [!DNL Slack]도 MCP 요청에 적용됩니다. 허용할 주소를 확인하려면 Adobe 담당자에게 문의하십시오. IP 주소 범위를 추측하지 마십시오. 의미 체계 검색과 같은 일부 기능은 [!DNL Slack] 계획에 따라 달라질 수 있습니다.

### 비가역 앱 설정 검토 {#review-irreversible-settings}

동료는 클라이언트 ID 및 클라이언트 암호와 함께 기밀 OAuth 클라이언트로 연결합니다. 일부 [!DNL Slack] 앱 설정은 되돌릴 수 없으므로 변경하기 전에 다음을 검토하십시오.

* **PKCE(Proof Key for Code Exchange):** 확인 없이 이 커넥터에 대해 [!DNL Slack] PKCE 설정을 켜지 마십시오. 이 설정이 앱을 공용 클라이언트로 변경하는 문서가 [!DNL Slack]개 있으며 [!DNL Slack] 지원에서만 앱을 되돌릴 수 있습니다. 자세한 내용은 [PKCE 사용](https://docs.slack.dev/authentication/using-pkce/)을 참조하세요.
* **토큰 순환:** [!DNL Slack] 토큰 순환을 켜면 해제할 수 없습니다. 이 앱에 대해 켜기 전에 Adobe 담당자에게 문의하십시오. 자세한 내용은 [토큰 순환 사용](https://docs.slack.dev/authentication/using-token-rotation/)을 참조하세요.

### 보트 기능이 필요하지 않음 {#bot-features-not-required}

커넥터에는 보트 기능이 필요하지 않습니다. 봇 토큰 범위, [!DNL Events API] 요청 URL, 대화형 요청 URL, 들어오는 웹후크, 슬래시 명령, [!DNL Socket Mode] 또는 앱 수준 토큰이 필요하지 않습니다. 기존 앱이 이러한 기능을 다른 용도로 사용하는 경우 그대로 유지합니다.

[!DNL Slack] MCP 서버는 동적 클라이언트 등록 또는 SSE(서버 전송 이벤트)를 지원하지 않습니다. 동료는 등록된 앱과 스트리밍 가능한 HTTP 전송을 사용합니다.

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL Slack] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다. 구성원이 로그인하기 전에 [Slack 앱 준비](#prepare-slack-app)를 완료하십시오.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Slack]** 카드에서 **[!UICONTROL 구성]**&#x200B;을 선택합니다.

   **[!UICONTROL Slack 연결]** 대화 상자가 열립니다. 커넥터가 고정 [!DNL Slack] MCP 서버 URL `https://mcp.slack.com/mcp`을(를) 사용합니다. 이 구성에 대해 개인 연결이 아닌 조직 범위를 사용하십시오.

1. [리디렉션 URL 등록](#register-redirect-url)에 설명된 대로 **[!UICONTROL Slack 응용 프로그램]**&#x200B;의 **[!UICONTROL 리디렉션 URL]**&#x200B;이 앱에 등록되어 있는지 확인하십시오. 그런 다음 앱의 **[!UICONTROL 클라이언트 ID]** 및 **[!UICONTROL 클라이언트 암호]**&#x200B;를 입력하십시오. 두 필드는 모두 필수입니다.

   앱 ID, 서명 암호 또는 보트 토큰을 입력하지 마십시오. 동료는 자격 증명을 일반 텍스트 커넥터 설정이 아닌 비밀로 저장합니다.

   ![Slack 응용 프로그램 섹션을 편집된 리디렉션 URL, 빈 클라이언트 ID 및 클라이언트 암호 필드, 기본 사용자 OAuth 범위 및 사용자가 사용할 수 있는 첫 번째 도구를 표시하는 Slack 연결 대화 상자입니다.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. **[!UICONTROL 사용자 OAuth 범위]**&#x200B;를 검토하십시오. 자세한 내용은 [사용자 OAuth 범위 검토](#review-scopes)를 참조하십시오.

1. **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 구성원이 사용하지 않아야 하는 도구를 제거합니다. 하나 이상의 도구가 남아 있어야 합니다. 자세한 내용은 [사용 가능한 도구](#available-tools)를 참조하세요.

1. **[!UICONTROL 액세스 및 권한]**&#x200B;을 검토한 다음 **[!UICONTROL 연결 저장]**&#x200B;을 선택하십시오. **[!UICONTROL Slack]** 카드에 **[!UICONTROL 저장된 구성]**&#x200B;이 표시됩니다.

   대화 상자에 **[!UICONTROL 인증]** 메서드, **[!UICONTROL 연결]** 형식 및 **[!UICONTROL 도구 시간 초과]**&#x200B;도 표시됩니다. 자격 증명 필드 또는 범위 목록이 비어 있으면 동료가 구성을 저장하지 않습니다.

   페이지를 다시 로드하고 **[!UICONTROL 구성 보기]**&#x200B;를 선택한 다음 구성원과 도구 선택이 저장되었는지 확인한 후 구성원이 로그인합니다.

   ![사용자 OAuth 범위, 사용자가 사용할 수 있는 16개의 모든 도구, 액세스 및 권한 알림, OAuth 인증, HTTP 연결 및 60초 도구 시간 제한 설정을 표시하는 Slack 연결 대화 상자입니다.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

저장해도 회원님이나 회원이 [!DNL Slack]에 로그인되지 않습니다. 연결을 확인하려면 [구성원으로 로그인](#sign-in-as-a-member)에 설명된 대로 본인 계정으로 로그인하십시오.

### 사용자 OAuth 범위 검토 {#review-scopes}

**[!UICONTROL 사용자 OAuth 범위]** 필드가 필요합니다. 공백 또는 쉼표로 범위를 구분하고 앱에 대해 승인된 사용자 범위와 일치시킵니다. 기본적으로 필드에는 다음 22개의 범위가 포함되어 있습니다.

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

작업 영역에서 모든 기본 범위를 승인할 수 없습니다. 앱 소유자와 요청된 범위를 검토하십시오.

>[!IMPORTANT]
>
>기본 범위에는 비공개 채널, 그룹 메시지 및 직접 메시지와 같은 비공개 콘텐츠가 포함됩니다. 또한 `chat:write`이(가) 포함되어 있어 Coworker가 로그인한 구성원으로 메시지와 답글을 보낼 수 있습니다. 조직에서 메시지 전송 도구를 활성화할지 여부를 명시적으로 결정합니다. 도구를 제거해도 해당 OAuth 범위는 제거되지 않습니다. 구성원이 메시지를 보내지 못하게 하려면 `slack_send_message` 도구와 `chat:write` 범위를 제거하십시오.

도구 선택 및 OAuth 범위는 독립적입니다. 액세스 범위를 좁힐 때는 도구 목록과 범위 필드를 모두 검토하십시오. 활성화된 도구는 구성원에게 해당 계정의 액세스 권한보다 더 많은 [!DNL Slack] 액세스 권한을 제공하지 않습니다.

### 사용 가능한 도구 {#available-tools}

[!DNL Slack] 커넥터는 다음 16개의 도구를 제공합니다. 기본적으로 멤버는 모든 세그먼트를 사용할 수 있습니다.

| 기능 | 도구 |
| --- | --- |
| 검색 | `slack_search_public` |
| 검색 | `slack_search_public_and_private` |
| 검색 | `slack_search_channels` |
| 검색 | `slack_search_users` |
| 대화 읽기 | `slack_read_channel` |
| 대화 읽기 | `slack_read_thread` |
| 대화 읽기 | `slack_list_channel_members` |
| 대화 읽기 | `slack_list_user_channels` |
| 컨텐츠 및 프로필 읽기 | `slack_read_canvas` |
| 컨텐츠 및 프로필 읽기 | `slack_read_user_profile` |
| 컨텐츠 및 프로필 읽기 | `slack_read_file` |
| 컨텐츠 및 프로필 읽기 | `slack_read_list` |
| 이모지와 반응 | `slack_search_emojis` |
| 이모지와 반응 | `slack_get_reactions` |
| 메시지 및 초안 | `slack_send_message` |
| 메시지 및 초안 | `slack_send_message_draft` |

커넥터가 읽기 전용이 아닙니다. `slack_send_message` 도구를 제거하지 않는 한 구성원이 메시지와 회신을 보낼 수 있습니다. 채널 만들기, 예약된 메시지, 파일 업로드, 반응 추가 및 캔버스 또는 목록 변경 사항은 포함되지 않습니다.

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL Slack] 계정으로 로그인합니다. 로그인할 때 클라이언트 암호는 필요하지 않습니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 사용자]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다.

1. **[!UICONTROL Slack]** 카드를 찾습니다. 카드에 **[!UICONTROL 구성되지 않음]** 및 **[!UICONTROL 아직 사용할 수 없음&rbrace;이 표시되는 경우 관리자가 이를 설정해야 합니다.]** 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오.

   조직의 클라이언트 암호를 요청하거나 복사하지 마십시오.

1. 관리자가 커넥터를 구성한 후 **[!UICONTROL Slack]** 카드에 **[!UICONTROL 로그인 필요]**&#x200B;가 표시됩니다. 카드에서 **[!UICONTROL 로그인]**&#x200B;을 선택합니다.

   **[!UICONTROL Slack]** 커넥터 세부 정보를 열 수도 있습니다. 로그인하기 전에 **[!UICONTROL 연결]** 섹션에 **[!UICONTROL 로그인]** 단추가 있는 **[!UICONTROL 로그인하지 않음]**&#x200B;이 표시됩니다.

   ![회원에 대한 Slack 커넥터 세부 정보, 로그인 필수 상태, 연결 테스트 단추, 서버 URL, 각 사용자가 로그인함, 로그인 단추와 관련하여 로그인되지 않음 및 관리자가 활성화한 도구 표시.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. 사용할 [!DNL Slack] 계정 및 작업 영역을 사용하여 [!DNL Slack] 인증을 완료합니다. 요청된 권한 및 작업 공간 승인 요구 사항을 검토합니다.

   >[!IMPORTANT]
   >
   >앱을 인식하고 조직에서 요청된 액세스를 승인하는 경우에만 계속합니다.

1. 동료로 돌아가 연결 상태를 검토합니다. 연결을 사용하기 전에 **[!UICONTROL 연결 테스트]**&#x200B;를 선택한 다음 [Slack 액세스 확인](#check-access)을 선택합니다.

1. 메시징 작업을 주의 깊게 검토하십시오. 동료가 [!DNL Slack] 계정으로 메시지와 답장을 보냅니다.

구성원은 연결을 테스트하거나 로그아웃할 수 있지만 조직 설정은 변경할 수 없습니다. [!DNL Slack]과(와) 부여된 범위가 허용하는 콘텐츠에만 액세스할 수 있습니다. 이 콘텐츠에는 [!DNL Slack] 계정이 액세스할 수 있는 경우에만 비공개 대화가 포함됩니다.

커넥터에서 [!DNL Slack] 계정의 연결을 끊으려면 **[!UICONTROL 로그아웃]**&#x200B;을 선택하세요.

## Slack 액세스 확인 {#check-access}

커넥터가 [!DNL Slack] 콘텐츠를 읽을 수 있는지 확인하려면 채팅을 시작하고 읽기 전용 프롬프트를 입력하십시오. 관리자가 `slack_list_user_channels` 도구를 사용하도록 설정했는지 확인하십시오.

예제 프롬프트:

* &quot;Slack을 사용하여 내가 속한 채널을 최대 5개까지 나열합니다. 채널 이름만 표시합니다. 메시지를 보내거나 초안을 만들거나 변경하지 마십시오.&quot;

조직에서 메시징 도구를 사용하는 경우 테스트를 위해 또는 승인을 통해 미리 설정된 채널에서만 전송을 테스트하십시오. 다른 구성원에게 별도로 로그인하도록 요청하여 각 구성원이 자신의 [!DNL Slack] 콘텐츠만 볼 수 있는지 확인하십시오.

## 액세스 문제 해결 {#troubleshoot-access}

설정, 로그인 또는 액세스가 실패할 경우 관리자에게 다음 사항을 확인하십시오.

| 문제 | 확인할 사항 |
| --- | --- |
| 설정을 저장할 수 없습니다. | 클라이언트 ID와 클라이언트 암호를 모두 입력하고, 사용자 OAuth 범위를 한 개 이상 유지하고, 도구 한 개 이상을 유지합니다. 앱 ID, 서명 암호 또는 보트 토큰을 입력하지 마십시오. |
| **[!UICONTROL 리디렉션 URL]**&#x200B;이 없거나 [!DNL Slack]에서 리디렉션 불일치를 보고합니다 | 스키마, 호스트, 포트 및 경로를 포함한 Coworker 대화 상자의 전체 리디렉션 URL을 [!DNL Slack] 앱에 저장된 **[!UICONTROL 리디렉션 URL]**&#x200B;과(와) 비교합니다. URL이 없거나 값이 다른 경우 Adobe 담당자에게 문의하십시오. |
| [!DNL Slack] 로그인 또는 요청 실패 | 앱 승인, 부여된 사용자 범위, 로그인한 [!DNL Slack] 계정 및 작업 영역, 앱에 대한 IP 주소 제한을 확인하십시오. 요청이 계속 실패하는 경우 로그아웃한 후 다시 로그인하십시오. |
| 읽기 또는 보내기 작업을 사용할 수 없습니다. | 조직의 도구 선택, 요청된 범위와 부여된 범위 및 구성원의 [!DNL Slack] 권한을 확인합니다. 이러한 설정은 독립적입니다. |
| 회원은 앱 설정을 변경할 수 없습니다. | 이 동작은 조직이 관리하는 연결에 대해 발생합니다. 관리자에게 문의하십시오. 구성원은 조직의 클라이언트 암호를 입력하지 않습니다. |
