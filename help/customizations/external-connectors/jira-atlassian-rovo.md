---
title: Jira / Atlassian Rovo 외부 커넥터
description: CX Enterprise Coworker에서 Jira / Atlassian Rovo 외부 커넥터를 설정하고 Atlassian으로 로그인하여 Jira 작업 항목을 읽고 검색하는 방법에 대해 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Jira / Atlassian Rovo 외부 커넥터 {#jira-atlassian-rovo}

[!DNL Jira]/[!DNL Atlassian Rovo] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL Jira] 작업 항목을 읽고 검색하십시오. 커넥터를 설정한 후 Coworker에 작업 항목을 찾고 세부 사항을 읽은 다음 JIRA 쿼리 언어(JQL)를 사용하여 검색하도록 요청하십시오. 커넥터가 [!DNL Atlassian]에서 호스트하는 MCP(모델 컨텍스트 프로토콜) 서버입니다.

>[!AVAILABILITY]
>
>[!DNL Jira]/[!DNL Atlassian Rovo] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 세 개의 개별 부품이 있습니다.

* **[!DNL Atlassian]준비:** [!DNL Atlassian] 조직 관리자는 Coworker 리디렉션 URL 도메인을 허용하고 MCP 액세스 정책을 검토합니다.
* **조직 설정:** 동료 관리자가 전체 조직에 대해 커넥터를 한 번 구성합니다. 관리자는 구성원이 사용할 수 있는 읽기 전용 도구를 선택합니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL Atlassian] 계정으로 로그인합니다. 구성원은 자신의 계정에 보기 권한이 있는 [!DNL Jira] 데이터에만 액세스할 수 있습니다.

조직 구성을 저장해도 구성원에 로그인하거나 [!DNL Jira] 권한을 부여하지 않습니다. 각 구성원은 개별적으로 로그인해야 합니다.

커넥터에 공유 서비스 계정 또는 API 토큰 옵션이 없습니다. 동료가 [!DNL Atlassian]에 OAuth 응용 프로그램을 자동으로 등록하므로 클라이언트 ID 또는 클라이언트 암호를 입력하지 않습니다.

커넥터 이름에 [!DNL Atlassian Rovo]이(가) 포함되어 있지만 커넥터는 [!DNL Jira] 읽기 및 검색 액세스만 요청합니다. [!DNL Confluence], [!DNL Rovo]별, 쓰기 또는 원본에 대한 액세스를 요청하지 않습니다. 이 커넥터를 통해 다른 [!DNL Atlassian] MCP 기능을 사용할 필요는 없습니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **조직 설정의 경우:** [!DNL Jira] / [!DNL Atlassian Rovo] 커넥터를 사용할 수 있는 조직의 Coworker에서 조직 커넥터를 관리할 수 있는 권한이 있는 계정입니다.
* **[!DNL Atlassian] 준비:** MCP 액세스 및 Coworker 리디렉션 URL 도메인을 승인할 수 있는 [!DNL Atlassian] 조직 관리자
* **구성원 로그인의 경우:** [!DNL Atlassian] 계정에 의도한 [!DNL Jira]개의 사이트, 프로젝트 및 작업 항목에 액세스할 수 있습니다.
* **네트워크 액세스용:** 연결을 허용하는 [!DNL Atlassian] IP 허용 목록 및 앱 정책. 로그인에 성공해도 도구 요청이 허용되는지 확인되지 않습니다.
* **[!DNL Rovo]사용:** [!DNL Rovo]이(가) [!DNL Atlassian] 조직 및 의도한 [!DNL Jira] 사이트에 대해 활성화되었습니다. 자세한 내용은 [!DNL Atlassian] 설명서에서 [Rovo를 사용하는 방법](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation)을 참조하십시오.

## [!DNL Atlassian] 액세스 준비 {#prepare-atlassian}

구성원이 로그인하기 전에 [!DNL Atlassian] 조직 관리자가 [!DNL Atlassian Administration]에서 액세스를 준비합니다.

1. [!DNL Atlassian Administration]을(를) 열고 의도한 조직을 선택합니다.

1. **[!UICONTROL 커넥터]** > **[!UICONTROL Atlassian MCP 서버]** > **[!UICONTROL 도메인 추가]**&#x200B;를 선택합니다.

1. Coworker 설치 대화 상자에 표시된 **[!UICONTROL 리디렉션 URL]**&#x200B;의 도메인을 추가하십시오. 대화 상자에 대해서는 [조직에 대한 커넥터 구성](#configure-organization)을 참조하십시오.

   전체 URL을 붙여 넣는 대신 [!DNL Atlassian] 도메인 형식 규칙을 따릅니다. 자세한 내용은 [!DNL Atlassian] 설명서의 [사용 가능한 Atlassian MCP 서버 도메인](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/)을 참조하십시오.

1. [!DNL Atlassian] 관리자와 함께 MCP 권한 그룹, 앱 허용 목록 및 IP 정책을 검토하십시오. 자세한 내용은 다음 [!DNL Atlassian] 설명서를 참조하십시오.

   * [지원되는 Atlassian MCP 도구](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/), 각 도구에 필요한 권한 그룹 및 범위
   * 인증 및 IP 허용 목록에 추가를 위해 [Atlassian MCP 서버 설정 제어](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/)

항상 설정 중인 환경에 대해 [동료] 대화 상자에 표시된 리디렉션 URL을 사용합니다. 다른 환경에서 리디렉션 URL을 복사하지 마십시오.

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL Jira] / [!DNL Atlassian Rovo] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. **[!UICONTROL Jira / Atlassian Rovo]** 카드에서 **[!UICONTROL 구성]**&#x200B;을 선택합니다. 구성원은 이 연결을 구성하거나 제거할 수 없습니다.

1. **[!UICONTROL Connect Jira / Atlassian Rovo]** 대화 상자에서 고정 **[!UICONTROL 서버 URL]**, `https://mcp.atlassian.com/v2/mcp`을(를) 검토하십시오.

   [Atlassian 액세스 준비](#prepare-atlassian)에 설명된 대로 **[!UICONTROL 리디렉션 URL]**&#x200B;을 검토하고 [!DNL Atlassian] 관리자가 도메인을 승인하는지 확인하십시오. OAuth 자격 증명을 입력하지 않습니다.

1. **[!UICONTROL 사용자가 사용할 수 있는 도구]**&#x200B;에서 구성원이 사용할 수 있는 도구를 선택합니다. 자세한 내용은 [사용 가능한 도구](#available-tools)를 참조하세요.

   `getAccessibleAtlassianResources` 사이트 검색 도구가 필요하며 활성화된 상태를 유지합니다. 다른 5개의 도구는 선택 사항입니다. 조직의 모든 사용자를 위한 선택적 도구를 차단하려면 제거합니다. 제거한 도구를 다시 가져오려면 **[!UICONTROL 모든 도구 복원]**&#x200B;을 선택하세요. 사이트 검색만 사용하도록 설정한 상태에서 구성을 저장할 수 있지만 구성원이 작업 항목을 읽거나 검색할 수는 없습니다.

   ![필요한 getAccessibleAtlassianResources 도구와 5개의 선택적 도구를 사용하여 서버 URL, 수정된 리디렉션 URL 및 사용자가 사용할 수 있는 6개의 도구를 표시하는 Jira/Atlassian Rovo 연결 대화 상자.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. **[!UICONTROL 연결 저장]**&#x200B;을 선택한 다음 연결 세부 정보를 검토하십시오.

   각 구성원이 로그인할 때 커넥터가 다음과 같은 OAuth 범위를 요청합니다.

   | 범위 | 용도 |
   | --- | --- |
   | `read:me`, `read:account` | 구성원의 [!DNL Atlassian] 계정으로 인증을 지원합니다. |
   | `read:jira:agent-interface` | [!DNL Jira] 데이터를 읽습니다. |
   | `search:jira:agent-interface` | [!DNL Jira] 데이터를 검색합니다. |
   | `offline_access` | 로그인 토큰을 새로 고칩니다. |

   도구 시간 제한은 60초입니다. 첫 번째 연결 및 도구 검색이 더 오래 걸릴 수 있습니다.

### 사용 가능한 도구 {#available-tools}

[!DNL Jira] / [!DNL Atlassian Rovo] 커넥터는 다음과 같은 읽기 전용 도구를 제공합니다.

| 도구 | 설명 | 관리자 컨트롤 |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | 액세스할 수 있는 [!DNL Atlassian] 사이트 및 클라우드 ID를 찾으십시오. [!DNL Jira] 도구에는 이 도구가 필요합니다. | 필수 |
| `atlassianUserInfo` | 로그인한 사용자의 계정 정보를 가져옵니다. | 선택 사항입니다 |
| `getJiraIssue` | ID 또는 키로 [!DNL Jira] 작업 항목을 가져옵니다. | 선택 사항입니다 |
| `searchJiraIssuesUsingJql` | JQL로 [!DNL Jira] 작업 항목 검색. | 선택 사항입니다 |
| `discover` | 추가 도구 작업과 해당 입력 스키마를 찾습니다. | 선택 사항입니다 |
| `executeRead` | 댓글 읽기, 변경 내용, 프로젝트, 게시판, 달리기 등 `discover`을(를) 통해 검색된 읽기 작업을 실행합니다. | 선택 사항입니다 |

>[!IMPORTANT]
>
>`discover` 및 `executeRead` 도구를 사용하면 구성원에게 그룹으로 허용된 추가 읽기 작업에 액세스할 수 있습니다. 개별 작업을 끌 수 없습니다. 조직에서 이 액세스를 허용하지 않는 경우 두 도구를 모두 제거합니다. 커넥터에 쓰기 작업(`executeWrite`) 또는 제거 작업(`executeDestructive`)이 없습니다.

선택적 도구를 제거하면 Coworker에서 사용할 수 없게 제한됩니다. 로그인 시 커넥터가 요청하는 OAuth 범위는 감소되지 않습니다.

각 도구에는 특정 [!DNL Atlassian] 권한 그룹 및 범위가 필요합니다. 자세한 내용은 [!DNL Atlassian] 설명서에서 [지원되는 Atlassian MCP 도구](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/)를 참조하십시오.

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL Atlassian] 계정으로 로그인합니다. 로그인하기 위해 클라이언트 ID, 클라이언트 암호 또는 액세스 토큰이 필요하지 않습니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 사용자]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다.

1. **[!UICONTROL Jira / Atlassian Rovo]** 카드를 찾으십시오. 카드에 **[!UICONTROL 구성되지 않음]** 및 **[!UICONTROL 아직 사용할 수 없음&rbrace;이 표시되는 경우 관리자가 이를 설정해야 합니다.]** 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오. 구성원이 커넥터를 구성할 수 없습니다.

1. **[!UICONTROL 로그인]**&#x200B;을 선택하고 원하는 [!DNL Jira] 사이트에 액세스할 수 있는 [!DNL Atlassian] 계정을 사용하세요. 필요한 SSO(Single Sign-On), MFA(Multi-Factor Authentication) 및 동의 프롬프트를 완료합니다. 동의하기 전에 요청된 읽기 및 검색 액세스 권한을 검토하십시오.

   >[!IMPORTANT]
   >
   >앱을 인식하고 조직에서 요청된 액세스를 승인하는 경우에만 계속합니다.

1. Coworker로 돌아가 커넥터 세부 사항을 엽니다. 이 연결은 구성원에 대해 읽기 전용이며 관리자가 활성화한 도구를 볼 수 있습니다. **[!UICONTROL 연결 테스트]**&#x200B;를 선택하여 연결을 확인합니다.

1. 필요한 경우 [Jira 액세스 확인](#check-access)에 설명된 대로 작은 읽기 전용 검사를 실행합니다.

테스트가 성공해도 모든 [!DNL Jira] 사이트, 프로젝트 또는 작업 항목에 액세스할 수 있는지 확인되지 않습니다.

## [!DNL Jira] 액세스 확인 {#check-access}

커넥터가 데이터를 읽을 수 있는지 확인하려면 채팅을 시작하고 읽기 전용 프롬프트를 입력하십시오.

예제 프롬프트:

* &quot;Jira에서 가장 최근에 업데이트된 항목에서 주문한 최대 5개의 작업 항목을 검색합니다. 키와 링크를 포함하십시오. 아무 것도 수정하지 마십시오.&quot;

이 프롬프트가 작동하려면 관리자가 검색 도구를 사용하고 [!DNL Jira] 계정에 작업 항목을 볼 수 있는 권한이 있어야 합니다.

## 액세스 문제 해결 {#troubleshoot-access}

로그인 또는 액세스가 실패할 경우 관리자에게 다음 사항을 확인하십시오.

| 문제 | 확인할 사항 |
| --- | --- |
| 클라이언트 또는 도메인에 대한 로그인이 차단됨 | **[!UICONTROL Atlassian MCP 서버]** 설정의 [!DNL Atlassian Administration]에서 사용자 환경에 대한 리디렉션 URL 도메인이 승인되었는지 확인합니다. |
| 동의는 성공하지만 도구 호출은 거부됨 | [!DNL Jira] 권한, [!DNL Atlassian] MCP 권한 그룹, 앱 정책 및 IP 허용 목록을 확인하세요. 각 도구에 필요한 권한 그룹에 대해서는 [지원되는 Atlassian MCP 도구](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/)를 참조하십시오. |
| JQL 검색이 실패하지만 다른 읽기가 작동합니다 | 관리자가 `searchJiraIssuesUsingJql`을(를) 사용하도록 설정하고 연결이 `search:jira:agent-interface` 범위를 요청하는지 확인하십시오. |
| 동의가 `invalid_request`을(를) 반환합니다. | 관리자에게 요청하여 [!DNL Jira] 범위 외에 `read:me` 및 `read:account` 연결을 요청했는지 확인하십시오. |
| 변경 후에도 이전 범위가 계속 표시됩니다 | 오래된 사용자 수준 `jira_login` 인증 공급자 재정의는 조직 연결보다 우선할 수 있습니다. 관리자에게 오래된 재정의만 업데이트하거나 제거하도록 요청한 다음 다시 로그인하십시오. |
| 도구가 없습니다. | 관리자에게 도구 선택을 확인하도록 요청하십시오. 추가 읽기 작업에는 `discover` 및 `executeRead`, 필요한 범위 및 올바른 권한이 필요합니다. |
| **[!UICONTROL 연결 테스트]**&#x200B;가 느리거나 시간 초과되었습니다. | 도구 검색은 60초 도구 시간 제한보다 오래 걸릴 수 있습니다. 자격 증명을 변경하기 전에 문제가 느린 검색인지 로그인 실패인지 확인합니다. |

도움을 요청할 때 암호, 토큰, 인증 코드 또는 동의 URL을 공유하지 마십시오. 스크린샷이나 지원 티켓에 이러한 항목을 포함하지 마십시오.
