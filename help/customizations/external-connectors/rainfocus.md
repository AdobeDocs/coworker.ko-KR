---
title: RainFocus 외부 커넥터
description: 조직의 CX Enterprise Coworker에서 RainFocus 외부 커넥터를 설정하고 RainFocus로 로그인하여 채팅에서 이벤트 데이터 도구를 사용하는 방법에 대해 알아봅니다.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="이 커넥터는 베타 버전입니다."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# RainFocus 외부 커넥터 {#rainfocus}

[!DNL RainFocus] 외부 커넥터를 사용하여 Adobe CX Enterprise Coworker에서 [!DNL RainFocus] 이벤트 데이터로 작업하십시오. 커넥터를 설정한 후에는 [!DNL RainFocus] 계정이 액세스할 수 있는 세션, 참석자 및 사용자 지정 특성에 대해 동료에게 문의하십시오. 커넥터가 [!DNL RainFocus]에서 호스팅하는 MCP(모델 컨텍스트 프로토콜) 서버인 [!DNL RainFocus] MCP 프로필을 사용합니다.

>[!AVAILABILITY]
>
>[!DNL RainFocus] 외부 커넥터가 Beta 버전입니다. 설명서 및 기능은 변경될 수 있습니다.

## 커넥터 구성 {#connector-configuration}

커넥터 구성 프로세스에는 세 개의 개별 부품이 있습니다.

* **[!DNL RainFocus]준비:** [!DNL RainFocus] 관리자는 MCP 프로필을 프로비저닝하고 도구를 사용하도록 설정하며 프로필 URL을 제공합니다. 각 구성원에는 올바른 역할을 가진 [!DNL RainFocus] 계정이 필요합니다.
* **조직 설정:** 동료 관리자가 조직 전체에 대해 MCP 프로필 URL을 한 번 저장합니다. 커넥터는 고정된 읽기 도구 목록을 활성화합니다.
* **구성원 로그인:** 각 구성원이 자신의 [!DNL RainFocus] 계정으로 로그인합니다. 구성원은 [!DNL RainFocus] 역할과 프로필에서 허용하는 데이터에만 액세스할 수 있습니다.

조직 구성을 저장해도 구성원이 로그인하지 않거나 [!DNL RainFocus] 권한을 부여하거나 [!DNL RainFocus] 데이터 도구를 실행하지 않습니다. 각 구성원은 개별적으로 로그인해야 합니다.

## 사전 요구 사항 {#prerequisites}

시작하기 전에 다음을 확인하십시오.

* **Coworker 액세스:** [!DNL RainFocus] 커넥터를 사용할 수 있는 조직에서 조직 설정이 켜져 있는 Coworker 관리자 계정입니다.
* **MCP 프로필:** 제공된 [!DNL RainFocus] MCP 프로필과 [!DNL RainFocus] 관리자가 제공한 전체 HTTPS 프로필 URL입니다. 자세한 내용은 [MCP 프로필 URL 가져오기](#get-profile-url)를 참조하십시오.
* **구성원 계정:** 각 구성원에 대해 필요한 데이터에 액세스할 수 있는 보안 역할을 가진 [!DNL RainFocus] 계정입니다.

Coworker에서 클라이언트 ID, 클라이언트 암호 또는 액세스 토큰을 입력하지 않습니다. 각 구성원은 자신의 계정으로 [!DNL RainFocus]에 로그인합니다.

## [!DNL RainFocus] 액세스 준비 {#prepare-rainfocus}

Coworker에서 커넥터를 구성하기 전에 [!DNL RainFocus]에서 MCP 프로필 및 구성원 액세스를 준비하십시오. [!DNL RainFocus]은(는) 프로필, 사용 가능한 도구, 구성원 역할 및 모든 비용을 소유합니다. 동료는 조직의 프로필 URL 및 도구 목록과 각 구성원의 로그인을 저장합니다.

### MCP 프로필 URL 가져오기 {#get-profile-url}

[!DNL RainFocus]은(는) 일반적으로 요구 사항에 따라 고객에 대한 MCP 프로필을 구성합니다. [!DNL RainFocus] 관리자가 프로필을 설정하는 경우 프로세스는 다음과 같습니다.

1. [!DNL RainFocus]에서 **[!UICONTROL 통합 세트]** > **[!UICONTROL 활성 프로필]** > **[!UICONTROL MCP 프로필]**&#x200B;을 연 다음 프로필을 만듭니다.
1. 사용 사례에 필요한 도구만 활성화하고 다른 도구는 해제하십시오.
1. 생성된 MCP 서버 URL을 복사합니다. URL은 프로필에만 해당됩니다.

커넥터를 구성하는 동료 관리자에게 전체 URL을 제공합니다. 프로필 이름을 추측하거나 URL을 직접 작성하지 마십시오. 자세한 내용은 [RainFocus MCP 프로필 발표](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/)를 참조하십시오.

### 구성원 액세스 확인 {#confirm-member-access}

각 구성원은 자신의 [!DNL RainFocus] 계정으로 로그인합니다. 계정의 보안 역할과 프로필에서 활성화된 도구는 구성원이 액세스할 수 있는 데이터를 제어합니다. [!DNL RainFocus] 관리자에게 각 구성원의 작업에 대해 권한이 가장 낮은 역할이 있는지 확인하십시오.

## 조직을 위한 커넥터 구성 {#configure-organization}

관리자는 조직의 모든 사용자가 [!DNL RainFocus] 커넥터를 사용할 수 있도록 합니다. 조직 페이지의 변경 사항은 조직의 모든 사용자에게 적용됩니다. **[!UICONTROL Org]** 범위는 조직 설정이 켜져 있는 관리자에게만 표시됩니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 열고 **[!UICONTROL 조직]**&#x200B;을 선택한 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다.
1. Beta 레이블이 있고 **[!UICONTROL 구성되지 않음]**&#x200B;을 표시하는 **[!UICONTROL RainFocus]** 카드를 찾습니다. **[!UICONTROL 구성]**&#x200B;을 선택합니다.

1. **[!UICONTROL RainFocus 설정]** 대화 상자에서 **[!UICONTROL 개발 프로필 URL]**&#x200B;을 입력하십시오. [!DNL RainFocus] 관리자가 제공한 전체 MCP 프로필 URL을 사용하십시오.

   URL은 `https://`(으)로 시작해야 합니다. 공백, 백슬래시, 쿼리 문자열(`?`), 조각(`#`), 사용자 이름 또는 암호, 기본값이 아닌 포트, `.` 또는 `..` 경로 세그먼트를 포함할 수 없습니다. URL이 규칙과 일치하지 않으면 Coworker는 규칙을 설명하는 메시지를 표시합니다. 동료는 URL의 형식만 확인합니다. 프로필이 존재하는지 또는 프로필이 사용 가능한지 확인하지 않습니다.

1. **[!UICONTROL 액세스 및 권한]** 및 **[!UICONTROL 읽기 도구 수정]** 섹션을 검토하십시오. 커넥터는 10개의 읽기 도구를 모두 사용할 수 있으며 이 대화 상자에서 추가, 제거 또는 편집할 수 없습니다. 일부 도구는 참석자 개인 데이터 또는 일괄 내보내기를 반환합니다. 자세한 내용은 [사용 가능한 도구](#available-tools)를 참조하세요.

   ![빈 개발 프로필 URL 필드, 액세스 및 권한 섹션, 고정된 읽기 도구 설정 및 10개의 연결 저장 단추를 표시하는 RainFocus 대화 상자](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. **[!UICONTROL 연결 저장]**&#x200B;을 선택합니다. Coworker가 연결을 저장하는 동안에는 양식을 편집하거나 취소할 수 없습니다.

저장이 실패하면 대화 상자에 **[!UICONTROL 연결을 저장할 수 없음]**&#x200B;이 표시되고 입력한 URL이 유지됩니다. 저장이 실패해도 일부 설정이 저장될 수 있습니다. 구성을 다시 열고 확인한 후 다시 시도하십시오. 변경 내용이 충돌하는 것을 방지하려면 한 번에 한 명의 관리자만 커넥터를 구성해야 합니다.

### 저장된 구성 확인 {#verify-configuration}

연결을 저장한 후 구성을 확인하십시오.

1. 저장한 후 대화 상자에서 저장된 커넥터 세부 사항을 엽니다. **[!UICONTROL 외부 커넥터]** 목록으로 돌아가서 **[!UICONTROL RainFocus]** 카드에 **[!UICONTROL 저장된 구성]** 및 **[!UICONTROL 구성 보기]**&#x200B;가 표시되는지 확인하십시오.
1. 페이지를 다시 로드한 다음 **[!UICONTROL 구성 보기]**&#x200B;를 선택합니다.
1. 다음 세부 정보를 확인하십시오.

   * **[!UICONTROL Source]**&#x200B;은(는) 입력한 프로필 URL을 표시합니다.
   * **[!UICONTROL 인증]**&#x200B;이 있습니다.
   * **[!UICONTROL 도구 정책]** > **[!UICONTROL 허용된 도구 이름 또는 패턴]**&#x200B;은(는) [사용 가능한 도구](#available-tools) 섹션과 동일한 10개의 도구를 나열합니다.

1. 연결을 확인하려면 **[!UICONTROL 테스트]**&#x200B;를 선택하세요. 동료가 로그인을 요청하는 경우 [구성원으로 로그인](#sign-in-as-a-member)에 설명된 대로 자신의 [!DNL RainFocus] 계정을 사용하십시오.

   **[!UICONTROL 테스트]**&#x200B;는 서버의 도구를 나열하고 **[!UICONTROL 도구]** 수를 업데이트합니다. 서버에서 도구를 반환하지 않는 경우 세부 정보에 **[!UICONTROL 사용 가능한 도구]**&#x200B;가 표시됩니다. 테스트가 실패하면 세부 정보에 **[!UICONTROL 연결 실패]**&#x200B;가 표시됩니다.

   ![수정된 원본, rainfocus_login 인증 방법, 로그인 단추와 관련하여 로그인되지 않음 및 테스트 및 제거 단추를 표시하는 저장된 rainfocus 커넥터 세부 정보.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

커넥터 세부 정보의 **[!UICONTROL Connection]**, **[!UICONTROL Test]** 및 로그인 컨트롤은 자신의 연결에만 적용됩니다. 관리자로 로그인하면 로그인한 구성원이 없습니다. 성공적인 테스트에는 도구만 나열됩니다. [!DNL RainFocus] 데이터 도구를 실행하지 않거나 구성원이 특정 데이터에 액세스할 수 있는지 확인하지 않습니다.

커넥터 세부 사항에는 프로필 URL을 편집할 수 있는 옵션이 없습니다. **[!UICONTROL 제거]**&#x200B;를 수행하면 확인이 열리고 전체 조직에 대한 연결이 제거됩니다. 제거 작업은 문제 해결 단계가 아닌 고의적인 관리자 결정으로 처리하십시오.

### 사용 가능한 도구 {#available-tools}

[!DNL RainFocus] 커넥터를 사용하면 10개의 읽기 도구에 대한 고정 목록을 사용할 수 있습니다.

| 도구 | 데이터 영역 |
| --- | --- |
| `get_attendeeInfo` | 참석자 |
| `get_attendee_load` | 참석자 |
| `get_attendee_search` | 참석자 |
| `get_attribute_load` | 사용자 지정 속성 |
| `get_attribute_search` | 사용자 지정 속성 |
| `get_attributevalue_load` | 사용자 지정 속성 |
| `get_entityDataDump_attendee` | 참석자, 일괄 내보내기 |
| `get_entityDataDump_session` | 세션, 일괄 내보내기 |
| `get_session_load` | 세션 |
| `get_session_search` | 세션 |

[!DNL RainFocus]이(가) 나중에 추가하는 도구를 포함하여 이 목록에 없는 도구는 자동으로 활성화되지 않습니다. 이 목록은 [!DNL RainFocus] 보안 역할이나 프로필의 도구 설정을 대체하지 않으며, 이 설정은 여전히 데이터에 대한 액세스를 제어합니다.

>[!IMPORTANT]
>
>여러 도구는 참석자에 대한 개인 데이터 및 연락처 정보를 반환할 수 있습니다. 두 개의 도구는 데이터를 대량으로 내보내 그 결과가 클 수 있다. 읽기는 [!DNL RainFocus] 약관에 따라 요금이 발생할 수도 있습니다. 구성원이 로그인하기 전에 데이터 거버넌스 소유자와 함께 이러한 도구를 검토하십시오.

## 멤버로 로그인 {#sign-in-as-a-member}

관리자가 커넥터를 구성한 후 각 구성원은 자신의 [!DNL RainFocus] 계정으로 로그인합니다. 로그인하기 위해 클라이언트 ID, 클라이언트 암호 또는 액세스 토큰이 필요하지 않습니다.

1. **[!UICONTROL 사용자 지정]**&#x200B;을 연 다음 **[!UICONTROL 외부 커넥터]**&#x200B;를 선택합니다. 구성원은 기본적으로 **[!UICONTROL User]** 범위를 사용합니다. **[!UICONTROL RainFocus]** 카드를 찾습니다.
1. 카드에 **[!UICONTROL 이(가) 아직 없는 경우. 관리자가 이를 설정해야 합니다.]** 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오. 구성원은 자신의 프로필 URL을 입력할 수 없습니다.
1. 카드의 상태를 확인하십시오. 카드에 **[!UICONTROL 로그인 필요]**, **[!UICONTROL 연결됨]**, **[!UICONTROL 관리자가 설정]** 또는 **[!UICONTROL 연결 실패]** 상태가 표시됩니다.

   **[!UICONTROL 관리자가 설정]**&#x200B;하면 동료가 로그인 상태를 확인할 수 없습니다. 로그인 또는 로그아웃을 의미하지는 않습니다.

1. **[!UICONTROL 로그인]**&#x200B;을 선택합니다. 카드 세부 정보를 열고 **[!UICONTROL 연결]** 섹션에서 **[!UICONTROL 로그인]**&#x200B;을 선택할 수도 있습니다. [!DNL RainFocus] 창에서 로그인, SSO(Single Sign-On), MFA(Multi-Factor Authentication) 및 동의 프롬프트를 완료합니다. 승인한 액세스 권한을 검토합니다.

   **[!UICONTROL 인증 검색]**&#x200B;이 나타나면 Coworker는 해당 도구가 아니라 서버의 로그인 세부 정보를 읽습니다. 검색이 실패하거나 패널에서 **[!UICONTROL 클라이언트 ID]** 또는 **[!UICONTROL 클라이언트 암호]**&#x200B;를 요청하는 경우 중지하고 관리자에게 문의하십시오. 자격 증명을 입력하거나 추측하지 마십시오.

   ![구성원에 대한 RainFocus 커넥터 세부 정보, 로그인 필수 상태, 수정된 서버 URL, 각 사용자가 로그인함, 검색 인증 단추와 관련하여 로그인되지 않음 및 관리자가 활성화한 10개의 도구 표시.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Coworker로 돌아가서 **[!UICONTROL 연결됨]** 상태가 표시되는지 확인하십시오. 닫힌 로그인 창만으로는 성공을 확인할 수 없습니다. 창을 일찍 닫으면 아무것도 변경되지 않고 다시 시도할 수 있습니다.
1. 카드 세부 정보를 열어 관리자의 설정을 검토하십시오. **[!UICONTROL 서버 URL]**, **[!UICONTROL 로그인하는 사용자]**, **[!UICONTROL 인증]** 및 **[!UICONTROL 관리자가 활성화한 도구]**&#x200B;를 볼 수 있습니다.
1. 카드에서 **[!UICONTROL 테스트]**&#x200B;를 선택하거나 세부 정보에서 **[!UICONTROL 연결 테스트]**&#x200B;를 선택하여 계정에 대한 연결을 확인하세요.

   테스트를 성공하면 [!DNL RainFocus]이(가) 사용 가능한 도구 수와 함께 사용자 계정을 사용하여 응답했음을 알 수 있습니다. 이 테스트에는 도구만 나열됩니다. 데이터 도구를 실행하거나 특정 이벤트나 레코드에 대한 액세스를 확인하지 않습니다. 로그인을 갱신하고 도구를 다시 나열하려면 **[!UICONTROL 새로 고침]**&#x200B;을 선택하세요. Coworker에서 로그인을 갱신할 수 없는 경우 대신 **[!UICONTROL 도구 다시 로드]**&#x200B;가 단추에 표시되며 이 단추에는 다시 도구만 나열됩니다.

1. 테스트가 실패하면 동료는 **[!UICONTROL 다시 시도]** 및 **[!UICONTROL 기술 세부 정보]**&#x200B;와 함께 **[!UICONTROL RainFocus에 연결할 수 없음]**&#x200B;을 표시합니다. 로그아웃되면 다시 로그인하십시오. 문제가 계속되면 관리자에게 문의하십시오.

구성원은 로그인, 로그아웃, 테스트, 새로 고침 및 활성화된 도구를 볼 수 있습니다. 구성원은 조직 연결을 변경하거나 제거할 수 없으며 프로필 URL을 편집하거나 도구를 변경할 수 없습니다. 세부 정보를 여는 모든 구성원은 프로필 URL을 볼 수 있습니다. 관리자가 로그인하면 다른 구성원은 로그인되지 않습니다.

커넥터에서 [!DNL RainFocus] 계정의 연결을 끊으려면 **[!UICONTROL 로그아웃]**&#x200B;을 선택하세요. 언제든지 다시 로그인할 수 있습니다.

## 이벤트 데이터 액세스 확인 {#check-event-access}

[!DNL RainFocus] 데이터를 사용할 수 있는지 확인하려면 좁은 요청으로 읽기 전용 검사를 실행하십시오. 작업할 수 있도록 승인된 이벤트를 사용하고, 이 검사에 대해 참석자 데이터나 대량 내보내기를 반환하는 도구는 피하십시오. 채팅을 시작하고 프롬프트를 입력하십시오.

예제 프롬프트:

* &quot;RainFocus를 사용하여 액세스할 수 있는 최대 5개의 세션을 찾아보십시오. 해당 필드가 반환되는 경우 세션 제목과 ID만 표시합니다. 데이터를 내보내거나 참석자 정보를 반환하거나 변경하지 마십시오.&quot;

결과에 예상한 세션이 포함되어 있는지 확인합니다. 결과가 비어 있다고 해서 커넥터가 항상 작동하지 않는 것은 아닙니다. 로그인한 [!DNL RainFocus] 계정, 보안 역할 및 프로필에서 활성화된 도구를 확인합니다. 결과가 예기치 않게 크거나 중요한 데이터를 포함하는 경우 요청을 중지하고 범위를 좁히십시오.

## 액세스 문제 해결 {#troubleshoot-access}

[!DNL RainFocus] 데이터에 액세스할 수 없는 경우 관리자에게 다음 사항을 확인하십시오.

| 문제 | 확인할 사항 |
| --- | --- |
| **[!UICONTROL RainFocus]** 카드가 없습니다. | 조직에서 커넥터를 사용할 수 있는지 Adobe 담당자에게 확인합니다. |
| **[!UICONTROL Org]** 범위가 없습니다. | 관리자이고 조직에 대한 조직 설정이 켜져 있는지 확인합니다. |
| 동료가 프로필 URL을 거부합니다. | 메시지의 규칙을 따릅니다. [!DNL RainFocus] 관리자의 전체 프로필 URL을 사용하고 프로필 이름을 추측하지 마십시오. |
| **[!UICONTROL 연결을 저장할 수 없습니다]** 표시 | 일부 설정이 저장될 수 있습니다. 구성을 다시 열고 확인한 후 다시 시도하십시오. 한 번에 한 명의 관리자만 커넥터를 구성해야 합니다. |
| 카드에 **[!UICONTROL 을(를) 아직 사용할 수 없습니다. 관리자가 이를 설정해야 합니다.]** | 조직 설정이 누락되었습니다. 관리자에게 [커넥터를 구성](#configure-organization)하도록 요청하십시오. |
| 로그인이 **[!UICONTROL 클라이언트 ID]** 또는 **[!UICONTROL 클라이언트 암호]**&#x200B;를 요청하거나 검색이 실패합니다. | 중지하고 관리자에게 문의하십시오. 자격 증명을 입력하거나 추측하거나 앱을 등록하지 마십시오. |
| [!DNL RainFocus]에서 액세스 권한을 승인하면 로그인이 실패합니다. | 사용한 [!DNL RainFocus] 계정 및 보안 역할을 확인하십시오. Adobe 담당자 및 [!DNL RainFocus]에게 환경에 대한 로그인 설정을 확인하도록 요청하세요. 로그인 URL을 공유하지 마십시오. |
| **[!UICONTROL 테스트]**&#x200B;가 성공했지만 데이터 요청이 실패했습니다. | **[!UICONTROL 테스트]**&#x200B;에는 도구만 나열됩니다. [!DNL RainFocus] 보안 역할, 프로필에서 활성화된 도구 및 도구에 필요한 필터를 확인합니다. |
| 로그인하면 **[!UICONTROL RainFocus에 연결할 수 없습니다]**&#x200B;이(가) 나타납니다. | **[!UICONTROL 다시 시도]**&#x200B;를 선택합니다. 문제가 계속되면 관리자에게 문의하십시오. |
| 결과가 예기치 않게 크거나 중요한 데이터를 포함합니다. | 요청을 중지하고 범위를 좁힙니다. 원시 이벤트 데이터를 티켓 또는 채팅에 붙여넣지 마십시오. |

지원 센터에 문의할 때 오류 텍스트, 오류 시간 및 환경만 포함하십시오. 기술 세부 사항, 프로필 URL, 로그인 캡처, 암호, 토큰 또는 인증 코드를 공유하지 마십시오.
