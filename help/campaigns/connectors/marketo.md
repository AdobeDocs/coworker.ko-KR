---
description: Marketo 스마트 및 정적 목록을 동기화할 수 있도록 Marketo Engage 계정을 Coworker Campaigns에 연결하는 방법을 알아봅니다.
title: Marketo Engage에 연결
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Marketo Engage에 연결 {#marketo}

Adobe Coworker Campaigns를 사용하면 Marketo Engage 계정을 연결하여 스마트 및 정적 목록을 가져올 수 있습니다.

>[!PREREQUISITES]
>
>이 커넥터를 사용하려면 먼저 다음을 수행해야 합니다.
>
>* 활성 Marketo Engage 계정
>* Marketo **인스턴스 URL**
>* [클라이언트 ID 및 클라이언트 암호](https://experienceleague.adobe.com/ko/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token)를 통해 Marketo의 동료 캠페인에 대해 [사용자 지정 서비스](https://experienceleague.adobe.com/ko/docs/marketo-developer/marketo/rest/custom-services#custom-services-1)를 만들었습니다.

## 연결 방법

1. [동료 캠페인 홈 페이지](https://coworker-campaigns.experience.adobe.com/)에서 **사용자 지정**&#x200B;을 클릭하고 **커넥터**&#x200B;를 선택합니다.

   ![Coworker Campaigns 왼쪽 탐색(확장된 커넥터 사용자 지정 및 강조 표시)](./assets/marketo-1.png)

1. **통합 추가**&#x200B;를 클릭합니다.

   ![Connectors 화면에 통합 단추 추가](./assets/marketo-2.png)

   >[!NOTE]
   >
   >첫 번째 통합이 아닌 경우 버튼에 &quot;커넥터 추가&quot;가 표시됩니다.

1. Marketo 행에서 **연결**&#x200B;을 클릭합니다.

   연결 단추가 있는 ![Marketo 커넥터 타일](./assets/marketo-3.png)

1. Marketo **인스턴스 URL**, **클라이언트 ID** 및 **클라이언트 암호**&#x200B;를 입력하십시오. **연결**&#x200B;을 클릭합니다.

   >[!NOTE]
   >
   >내 Marketo 페이지를 볼 때 브라우저의 주소 표시줄에 Marketo 인스턴스 URL을 찾을 수 있습니다.

   ![인스턴스 URL, 클라이언트 ID 및 클라이언트 암호와 함께 Marketo 연결 대화 상자](./assets/marketo-4.png)

연결 후 Marketo이 커넥터 목록에 나타나며 Marketo에서 동기화할 연락처 목록을 연결할 때 선택할 수 있습니다.

**연결을 끊으려면:**

1. Connectors 화면에서 Marketo 타일을 찾아 **관리**&#x200B;를 클릭합니다.

   ![연결된 상태 및 관리 단추를 표시하는 Marketo 타일이 있는 커넥터 화면](./assets/marketo-5.png)

1. **연결 해제**&#x200B;를 클릭합니다(지금은 클라이언트 암호를 다시 입력할 필요가 없음).

   ![인스턴스 URL 및 클라이언트 ID 필드와 연결 해제 단추가 있는 Marketo 관리 대화 상자](./assets/marketo-6.png)

   >[!NOTE]
   >
   >인스턴스 URL이 처음 추가되면 기본적으로 REST 끝점 URL로 설정되고 `*.mktorest.com`로 끝납니다.

1. 확인하려면 **연결 끊기**&#x200B;를 다시 클릭하세요.

   ![연결 끊기 확인 대화 상자](./assets/marketo-7.png)
