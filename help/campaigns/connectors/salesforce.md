---
description: 설명.
title: Salesforce에 연결
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 12ee914ed944c82694b9373f611e19cf040e2229
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%
---
# Salesforce에 연결 {#salesforce}

Adobe Coworker Campaigns를 사용하면 Salesforce 계정을 연결하여 리드 및 연락처에 액세스할 수 있습니다.

>[!PREREQUISITES]
>
>이 커넥터를 사용하려면 먼저 다음을 수행해야 합니다.
>
>* 활성 Salesforce 계정
>* Salesforce의 권한: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Salesforce 인스턴스 URL, [클라이언트 ID 및 클라이언트 암호](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key)가 편리합니다.

## 연결 방법

1. [동료 캠페인 홈 페이지](https://coworker-campaigns.experience.adobe.com/)에서 **사용자 지정**&#x200B;을 클릭하고 **커넥터**&#x200B;를 선택합니다.

   ![Coworker Campaigns 왼쪽 탐색(확장된 커넥터 사용자 지정 및 강조 표시)](./assets/salesforce-1.png)

1. **통합 추가**&#x200B;를 클릭합니다.

   ![Connectors 화면에 통합 단추 추가](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >첫 번째 통합이 아닌 경우 버튼에 &quot;커넥터 추가&quot;가 표시됩니다.

1. Salesforce 행에서 **연결**&#x200B;을 클릭합니다.

   ![](./assets/salesforce-3.png)

1. Salesforce **인스턴스 URL**, **클라이언트 ID** 및 **클라이언트 암호**&#x200B;를 입력하십시오. **연결**&#x200B;을 클릭합니다.

   >[!NOTE]
   >
   >* Salesforce에서 클라이언트 ID = 소비자 키 및 클라이언트 암호 = 소비자 암호.
   >
   >* Salesforce 계정에 있는 동안 브라우저의 주소 표시줄에서 인스턴스 URL을 찾거나 **설정** > **회사 설정** > **내 도메인**&#x200B;으로 이동하여 찾을 수 있습니다.

   ![](./assets/salesforce-4.png)

연결 후 Salesforce이 커넥터 목록에 나타나며 Salesforce에서 동기화하기 위해 리드 또는 연락처 목록을 연결할 때 선택할 수 있습니다.

**연결을 끊으려면:**

1. Connectors 화면에서 Salesforce 타일을 찾아 **관리**&#x200B;를 클릭합니다.

   ![](./assets/salesforce-5.png)

1. **연결 해제**&#x200B;를 클릭합니다(지금은 클라이언트 암호를 다시 입력할 필요가 없음).

   ![](./assets/salesforce-6.png)

1. 확인하려면 **연결 끊기**&#x200B;를 다시 클릭하세요.

   ![](./assets/salesforce-7.png)
