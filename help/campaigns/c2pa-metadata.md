---
description: Coworker Campaigns에서 생성부터 이메일 게재에 이르기까지 이미지에 C2PA 메타데이터를 자동으로 첨부하고 보존하는 방법에 대해 알아봅니다.
title: 동료 캠페인의 C2PA 메타데이터
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%
---
# 동료 캠페인의 C2PA 메타데이터 {#overview}

생성 AI 투명성을 중심으로 새로운 법이 등장하고 있으며, Adobe은 관할권 전반에서 적용 가능한 요구 사항을 충족하기 위해 노력하고 있습니다. [C2PA 메타데이터](https://c2pa.org/)는 Adobe이 이러한 법률의 요구 사항을 충족하기 위해 사용하는 증명 도구입니다.

C2PA 메타데이터는 콘텐츠의 한 부분이 생성되거나 편집되는 방식을 기록하는 보이지 않는 지속적인 메타데이터입니다. 동료 캠페인에서 생성 AI 도구를 사용하여 이미지를 생성하거나 편집하면 C2PA 메타데이터가 해당 이미지에 자동으로 첨부됩니다. 사용자 측에서는 아무 작업도 필요하지 않습니다.

## 이메일 캠페인의 C2PA 메타데이터 {#c2pa-metadate-email}

이메일 캠페인에 전송된 이미지는 C2PA 메타데이터를 그대로 유지하므로 수신자는 게재된 이메일에서 직접 이미지의 원본 및 진위를 확인할 수 있습니다.

## C2PA 메타데이터를 첨부하는 작업 {#actions}

다음 표에서는 Coworker Campaign에서 이미지 생성에 수행된 이미지 작업을 기반으로 C2PA 메타데이터가 첨부되는 시기를 요약합니다.

| 액션 | 설명 | C2PA 메타데이터가 첨부되었습니까? | 사용 사례 예 |
| --- | --- | --- | --- |
| **이미지 생성** | 텍스트 프롬프트 또는 참조 이미지에서 새 이미지를 생성하거나 기존 이미지에서 유사한 이미지를 생성합니다. | 항상 이미지는 생성 AI에 의해 생성되므로 항상 새로운 C2PA 메타데이터를 전달합니다. | 이메일 캠페인에 대한 배너 이미지는 원하는 시각적 개체를 설명하는 텍스트 프롬프트에서 생성됩니다. |

## 컨텐츠 유형 및 해당 범위 {#content-types}

* **이미지**: 적용됨. C2PA 메타데이터는 생성 AI로 이미지가 생성될 때 첨부되며, 동료 캠페인에서 이미지 생성으로 수행된 자르기, 텍스트 오버레이 및 이미지 오버레이 작업을 통해 보존됩니다.
* **텍스트**: 적용할 수 없습니다. 복사 생성, 번역 및 브랜드 정렬 제안과 같은 Coworker Campaign의 텍스트 전용 출력에는 C2PA 메타데이터가 필요하지 않습니다.

## 콘텐츠가 이동할 때 수행되는 작업 {#content-moves}

동료 캠페인은 지원되는 이미지 에셋과 연결된 C2PA 메타데이터를 보존합니다. 동료 캠페인으로 가져올 때 이미지에 C2PA 메타데이터가 포함된 경우, 자산이 생성된 캠페인 콘텐츠 및 아웃바운드 이메일 경험에 사용될 때 해당 자격 증명이 유지됩니다.

## 추가 리소스 {#resources}

* [생성 AI 콘텐츠 투명도](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Adobe Experience Cloud Generative AI 사용자 지침](https://www.adobe.com/kr/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}
* [가드레일 및 제한 사항](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
