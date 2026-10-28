---
title: Adobe Analytics 프로젝트를 Customer Journey Analytics으로 마이그레이션
description: Coworker를 사용하여 Adobe Analytics Workspace 프로젝트 및 해당 구성 요소를 Customer Journey Analytics에 확인, 매핑 및 마이그레이션한 다음 마이그레이션 상태를 확인합니다.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Coworker를 사용하여 Adobe Analytics 프로젝트를 Customer Journey Analytics으로 마이그레이션

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Adobe CX Enterprise Coworker을 사용하여 단일 대화 내에서 Adobe Analytics 프로젝트 및 관련 구성 요소를 Customer Journey Analytics으로 마이그레이션할 수 있습니다.

공동 작업자는 프로젝트의 차원과 지표가 Customer Journey Analytics 데이터 보기에 매핑되어 있는지 확인하고 매핑되지 않은 차원은 매핑하도록 도와준 다음 Customer Journey Analytics에서 프로젝트를 다시 만듭니다.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>이 문서에 설명된 기능은 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용하지 못할 수 있습니다. 이 메모는 기능을 일반적으로 사용할 수 있을 때 제거됩니다.

>[!IMPORTANT]
>
>프로젝트를 마이그레이션하기 전에 Adobe Analytics 설명서에서 [구성 요소와 프로젝트를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션 준비](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)를 참조하십시오. 마이그레이션을 준비하는 방법, 포함된 항목, 오류를 일으키는 요소, 매핑이 조직 전체에 미치는 영향 등을 설명합니다. 이 정보는 Coworker의 마이그레이션에 적용됩니다.

## Adobe Analytics 사용자 인터페이스에서의 마이그레이션과의 차이점

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

Coworker를 사용하여 프로젝트를 마이그레이션하는 것은 다음과 같은 점에서 Adobe Analytics 사용자 인터페이스에서 프로젝트를 마이그레이션하는 것과 다릅니다.

| | Coworker | Adobe Analytics 사용자 인터페이스 |
| --- | --- | --- |
| **프로젝트를 마이그레이션할 수 있는 사용자** | Adobe Analytics 관리자 및 [!UICONTROL **구성 요소 마이그레이션**] 권한이 있는 사용자 | Adobe Analytics 관리자만 |
| **프로젝트 소유자** | 마이그레이션을 수행하는 사용자 | [!UICONTROL **프로젝트 소유자**] 필드에 지정한 사용자 |
| **차원 및 지표 매핑** | 동료가 프로젝트의 유효성을 검사하고 각 차원과 지표가 매핑되는 방법을 나열합니다. 자동으로 매핑될 수 없는 모든 항목에 대해 Coworker는 데이터 보기에서 차원 또는 지표를 제안하고 매핑을 업데이트합니다. | [!UICONTROL **스키마 매핑**] 섹션에서 [!UICONTROL **매핑되지 않음**] 상태의 각 차원 또는 지표를 선택하고 수동으로 매핑합니다. |
| **마이그레이션하는 방법** | 원하는 내용을 즉시 설명하십시오. 동료는 그 과정에서 몇 가지 질문을 하며 일을 한다. 예를 들어 Coworker는 사용자가 이름을 지정한 구성 요소로 프로젝트를 만든 다음 마이그레이션할 수 있습니다. [특정 구성 요소에서 시작](#start-from-specific-components)을 참조하십시오. | Analysis Workspace에서 프로젝트를 만들고, 마이그레이션할 구성 요소를 추가하고, 프로젝트를 저장합니다. 그런 다음 [!UICONTROL **구성 요소 마이그레이션**]&#x200B;에서 프로젝트를 선택하고 프로젝트 소유자를 지정하고 각 보고서 세트에 대한 스키마를 매핑한 다음 [!UICONTROL **마이그레이션**]&#x200B;을 선택합니다. |

## 사전 요구 사항

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Coworker를 사용하여 프로젝트를 마이그레이션하려면 다음이 필요합니다.

* Adobe Analytics MCP에 액세스 구성 요소 마이그레이션 도구는 Adobe Analytics MCP 액세스 권한이 있는 고객에 대해 자동으로 활성화됩니다. [!UICONTROL **aa-mcp**]&#x200B;이(가) 연결되어 있는지 확인하려면 [동료 채팅을 사용하여 데이터 분석 시작](/help/chat/use-cases/data-insights/analytics-chat.md)을 참조하세요.

* Adobe Analytics 관리자 권한 또는 Admin Console의 [!UICONTROL **구성 요소 마이그레이션**] 권한. 관리자가 될 필요는 없습니다.

* Adobe Analytics 설명서의 구성 요소 마이그레이션을 위한 [사전 요구 사항](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites).

* 기본 보고서 세트를 사용하는 프로젝트. 가상 보고서 세트는 마이그레이션할 수 없습니다.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## 마이그레이션하기 전에 보고서 세트 매핑 검토

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

해당 보고서 세트에서 첫 번째 마이그레이션 전에 보고서 세트의 차원 및 지표가 매핑되는 방법을 검토하는 것이 좋습니다. 매핑은 조직이 마이그레이션하는 모든 프로젝트에 적용되므로 매핑을 먼저 해결하면 나중에 프로젝트가 유효성 검사를 통과할 수 있습니다. 매핑 선택에 대한 지침은 Adobe Analytics 설명서에서 [구성 요소를 매핑할 방법을 조직으로 결정](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components)을 참조하십시오.

매핑을 검토하려면 [!UICONTROL **범위**] 탭에서 [!UICONTROL **매핑만 검토**]&#x200B;를 선택하거나 동료에게 직접 요청하십시오.

**프롬프트**

* &quot;보고서 세트의 차원과 지표가 데이터 보기에 매핑되는 방식 표시&quot;
* &quot;내 보고서 세트의 차원 및 지표 중 내 데이터 보기에 매핑되지 않은 차원과 지표는 무엇입니까?&quot;

동료에게 매핑을 업데이트하도록 요청할 수도 있습니다.

이 검토를 건너뛰어도 Coworker는 [마이그레이션하는 각 프로젝트에 대한 매핑을 확인](#review-the-validation-results-and-mappings)합니다.

## 마이그레이션 시작

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

동료는 항상 프로젝트와 관련 구성 요소를 마이그레이션합니다. 특정 구성 요소를 마이그레이션하려면 Coworker에 새 프로젝트에 추가한 다음 해당 프로젝트를 마이그레이션하도록 요청하십시오.

Customer Journey Analytics에 이미 존재하는 구성 요소는 다시 만들어지지 않으므로 두 방법을 모두 사용할 수 있습니다. 예를 들어 가장 중요한 프로젝트를 먼저 마이그레이션한 다음 나머지 구성 요소를 마이그레이션합니다. Customer Journey Analytics에서 원하는 항목을 기반으로 시작할 위치 선택:

* Customer Journey Analytics에 프로젝트의 패널 및 시각화를 유지하려는 경우 **프로젝트를 마이그레이션**&#x200B;합니다. [프로젝트에서 시작](#start-from-a-project)을 참조하세요.
* Customer Journey Analytics에서 세그먼트, 계산된 지표 또는 날짜 범위와 같은 구성 요소를 원하는 경우 **특정 구성 요소를 마이그레이션**&#x200B;하지만 해당 구성 요소를 사용하는 프로젝트는 필요하지 않습니다. 예를 들어, Customer Journey Analytics에서 해당 프로젝트를 포함하는 새 프로젝트를 빌드하도록 계획할 수 있습니다. [특정 구성 요소에서 시작](#start-from-specific-components)을 참조하십시오.

### 프로젝트에서 시작

프로젝트 및 관련 구성 요소를 마이그레이션하려면 다음을 수행하십시오.

1. 동료에게 로그인합니다.

1. **[!UICONTROL 새 채팅]**&#x200B;을 선택하세요.

1. 텍스트 필드에서 Coworker에게 프로젝트를 마이그레이션하라는 메시지를 표시합니다. 예:

   **프롬프트**

   > Adobe Analytics에서 Customer Journey Analytics으로 구성 요소를 마이그레이션하려고 합니다.

   동료는 마이그레이션할 수 있는 사항을 설명하고 설문지를 시작합니다.

1. [!UICONTROL **범위**] 탭에서 다음 옵션 중 하나를 선택한 후 [!UICONTROL **다음**]&#x200B;을 선택합니다.

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | 옵션 | 설명 |
   | --- | --- |
   | [!UICONTROL **특정 AA 프로젝트**] | 이름을 지정한 프로젝트를 마이그레이션합니다. 이 섹션의 나머지 단계를 수행합니다. |
   | [!UICONTROL **매핑만 검토**] | 아무것도 마이그레이션하지 않고 보고서 세트의 지표 및 차원이 데이터 보기에 매핑되는 방식을 확인하십시오. 마이그레이션하기 전에 [보고서 세트 매핑 검토](#review-report-suite-mappings-before-you-migrate)를 참조하십시오. |
   | [!UICONTROL **전체 업그레이드 계획**] | Adobe Analytics에서 Customer Journey Analytics으로 이전하기 위한 전체적인 계획을 수립합니다. [동료와 함께 구현 계획](/help/chat/use-cases/data-insights/implementation-guide.md)을 참조하세요. |

1. (선택 사항) [!UICONTROL **Source 및 target**] 탭에서 질문에 답변한 후 [!UICONTROL **다음**]&#x200B;을 선택합니다.

1. [!UICONTROL **검토**] 탭에서 답변을 확인한 다음 [!UICONTROL **제출**]&#x200B;을 선택합니다.

   동료는 액세스 권한이 있는 Adobe Analytics 회사와 각 회사에 있는 기본 보고서 세트의 수를 확인한 다음 두 번째 질문을 시작합니다.

1. 다음 질문에 답변하고 각 질문 다음에 [!UICONTROL **다음**]&#x200B;을(를) 선택하십시오.

   | 탭 | 질문 | 추가 컨텍스트 |
   | --- | --- | --- |
   | [!UICONTROL **프로젝트**] | 마이그레이션하려는 AA 프로젝트의 이름을 입력하십시오. | 부분 이름이면 됩니다. |
   | [!UICONTROL **보고서 세트**] | 프로젝트는 어떤 보고서 세트를 사용합니까? | 목록에서 보고서 세트를 선택하거나 다른 보고서 세트의 이름을 입력합니다. |
   | [!UICONTROL **데이터 보기**] | 어떤 CJA 데이터 보기로 마이그레이션해야 합니까? | (선택 사항) 데이터 보기의 이름을 입력하거나 비워 두고 Coworker에서 일치하는 데이터 보기를 제안합니다. |

1. [!UICONTROL **검토**] 탭에서 답변을 확인한 다음 [!UICONTROL **제출**]&#x200B;을 선택합니다.

   어느 단계에서든 질문을 건너뛰려면 [!UICONTROL **질문서 건너뛰기**]&#x200B;를 선택하고 대신 채팅에서 원하는 내용을 설명하십시오.

1. [유효성 검사 결과 및 매핑을 검토](#review-the-validation-results-and-mappings)하여 계속합니다.

### 특정 구성 요소에서 시작

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

특정 구성 요소를 마이그레이션하려면 다음을 수행하십시오.

1. 동료에게 해당 구성 요소로 프로젝트를 만든 다음 마이그레이션하도록 요청하십시오. 예:

   **프롬프트**

   > 이름에 &quot;봄맞이 세일&quot;이 있는 모든 Analytics 세그먼트를 CJA으로 마이그레이션하려고 합니다. 이러한 모든 세그먼트가 추가된 새 Workspace 프로젝트를 만든 다음 해당 프로젝트를 CJA으로 마이그레이션합니다.

   동료가 Adobe Analytics에서 프로젝트를 만듭니다.

1. 다음 섹션을 계속합니다. [유효성 검사 결과 및 매핑을 검토하십시오](#review-the-validation-results-and-mappings).

## 유효성 검사 결과 및 매핑 검토

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

동료는 선택한 데이터 보기에 대해 프로젝트의 유효성을 검사한 다음 프로젝트를 마이그레이션할 수 있는지 여부를 보고합니다. 결과에는 프로젝트의 각 차원과 지표 및 이 차원과 지표가 매핑된 Customer Journey Analytics 차원 또는 지표가 나열됩니다. 예:

* **지표:** 발생 횟수가 이벤트가 됨
* **Dimension:**&#x200B;시간 체류 시간

마이그레이션된 구성 요소 및 프로젝트 요소에 대해서는 Adobe Analytics 설명서의 [마이그레이션에 포함된 내용 이해](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration)를 참조하십시오.

유효성 검사를 통과하지 못한 경우:

* **자동으로 매핑할 수 없는 차원 또는 지표:** Coworker가 데이터 보기에서 각 차원을 매핑할 차원 또는 지표를 제안하고 매핑을 업데이트한 다음 프로젝트의 유효성을 다시 확인합니다. 예를 들어 &quot;web.webPageDetails.pageViews.value에 페이지 보기 수 매핑&quot;과 같이 매핑할 차원 또는 지표를 동료에게 알릴 수도 있습니다.

* **지원되지 않는 요소:** Adobe Analytics의 프로젝트에서 지원되지 않는 요소를 제거하십시오. 예를 들어 모든 패널이 가상 보고서 세트가 아닌 기본 보고서 세트를 사용하도록 하십시오. 그런 다음 동료에게 프로젝트를 다시 확인하도록 요청하십시오. 지원되지 않는 요소 목록을 보려면 Adobe Analytics 설명서에서 [오류를 일으키는 지원되지 않는 요소 이해](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors)를 참조하십시오.

마이그레이션하기 전에 전체 보고서 세트에 대한 매핑을 확인하려면 [마이그레이션하기 전에 보고서 세트 매핑 검토](#review-report-suite-mappings-before-you-migrate)를 참조하십시오.

## 프로젝트 마이그레이션

1. 유효성 검사가 성공하면 선택한 데이터 보기에서 프로젝트의 Customer Journey Analytics 버전을 만들지 여부를 묻는 메시지가 표시됩니다. [!UICONTROL **예, 마이그레이션**]&#x200B;을 선택한 다음 [!UICONTROL **제출**]&#x200B;을 선택합니다.

   마이그레이션하지 않고 중지하려면 [!UICONTROL **아니요, 여기에서 중지**]&#x200B;를 선택하십시오.

   동료가 프로젝트 소유자로 사용하여 Customer Journey Analytics에서 프로젝트를 다시 만듭니다. 원래 Adobe Analytics 프로젝트는 변경되지 않습니다.

1. 다음 섹션을 계속합니다. [마이그레이션 상태를 확인](#check-the-migration-status).

## 마이그레이션 상태 확인

마이그레이션은 백그라운드에서 실행되므로 새 프로젝트가 즉시 준비되지 않을 수 있습니다.

1. 동료에게 마이그레이션 상태를 확인하라는 메시지 표시:

   **프롬프트**

   > 상태 확인

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   동료는 다음 상태 중 하나를 보고합니다.

   | 상태 | 의미 |
   | --- | --- |
   | 대기열에 추가됨 | 마이그레이션이 시작되기를 기다리는 중입니다. |
   | 시작됨 | 마이그레이션이 진행 중입니다. |
   | 완료 | 마이그레이션이 완료되었습니다. Coworker는 프로젝트 이름 및 데이터 보기를 포함하여 마이그레이션된 항목에 대한 요약을 제공합니다. |
   | 실패 | 마이그레이션에 실패했습니다. 마이그레이션을 다시 시도하십시오. Adobe Analytics 설명서에서 [실패한 마이그레이션 다시 시도](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration)를 참조하십시오. |

1. 마이그레이션이 완료되면 Customer Journey Analytics Workspace의 프로젝트 목록에서 새 프로젝트를 엽니다.

1. (선택 사항) 프로젝트의 소유권을 Customer Journey Analytics의 모든 사용자에게 이전합니다. 자세한 내용은 [자산 전송](https://experienceleague.adobe.com/en/docs/analytics-platform/using/tools/asset-transfer/transfer-assets)을 참조하세요.

마이그레이션이 완료되면 동료는 다음에 마이그레이션할 다른 프로젝트를 제안할 수 있습니다.

## 더 나은 결과를 위한 팁

* 어떤 데이터 보기를 사용해야 할지 확실하지 않은 경우 설문지에 데이터 보기를 비워 둡니다. Coworker는 보고서 세트와 일치하는 데이터 보기를 제안합니다.
* 마이그레이션한 후 Adobe Analytics 및 Customer Journey Analytics 데이터를 비교하여 보고서가 일치하는지 확인하십시오. Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 [Coworker를 사용하여 데이터 유효성 검사](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)를 참조하십시오.

## 다음 단계

* 대신 Adobe Analytics 사용자 인터페이스에서 프로젝트를 마이그레이션하려면 Adobe Analytics 설명서의 [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration)을 참조하십시오.
* 다른 구현 및 관리 사용 사례는 [지능형 구현 및 관리 개요](/help/chat/use-cases/data-insights/data-governance-and-validation.md)를 참조하십시오.
