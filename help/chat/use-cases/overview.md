---
description: 데이터 인사이트, 대상, 여정 및 플랫폼 작업에서 영역별로 구성된 동료 채팅 사용 사례와 샘플 프롬프트를 찾아봅니다.
title: 동료 채팅 사용 사례
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 1071cb1d9d08d89592f14f05ec9e32087ad937f3
workflow-type: tm+mt
source-wordcount: '7196'
ht-degree: 6%
---
# 동료 채팅 사용 사례 {#use-cases}

동료 채팅을 사용하면 여러 UI를 탐색하거나 쿼리를 수동으로 작성하는 대신 자연어를 사용하여 [!DNL Experience Platform] 데이터를 쿼리하고, 분석하고, 작업할 수 있습니다. 이 페이지에는 데이터 통찰력, 대상, 여정, 충성도, 기본 요소 및 샌드박스 툴과 같이 작업 영역별로 구성된 사용 사례 전문가가 가장 많이 사용하는 카탈로그가 포함되어 있습니다. 각 항목에는 호출하는 스킬, 함께 작동하는 애플리케이션, 복사, 자체 데이터에 맞게 조정 및 대화를 통해 구체화할 수 있는 샘플 프롬프트가 포함됩니다.

>[!NOTE]
>
>준비 중:
>
>더 많은 작업을 더 빠르고 효율적으로 수행할 수 있도록 구축된 CX Enterprise Coworker을 통한 새로운 AEM 에이전트 기능입니다.
>
>자격이 있는 모든 고객은 순차적으로 Coworker의 Adobe Experience Manager 에이전트 기능에 액세스할 수 있습니다.
>
>AEM의 [AI - AEM의 Agentic 기능 개요](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/overview)도 참조하세요.

## 브랜드 경험

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [AEM 페이지 업데이트](brand-visibility/author-web-pages.md) | 경험을 정확하고 최신 상태로 유지하기 위해 콘텐츠 요소 업데이트, 제거, 바꾸기 또는 추가와 같은 작업을 수행합니다. 입력은 자연어 또는 PDF나 스크린샷과 같은 시각적 주석일 수 있습니다. | `aem-sites-pages-update` | Adobe Experience Manager(AEM) - AEM Sites | &lt;URL>에서 헤드라인을 Hello World로 업데이트<br><br>on &lt;URL>에서 &quot;Take our Coffee Quiz&quot; 단추를 더 매력적인 버전으로 변경<br><br>첨부된 내용을 기반으로 &lt;URL> 업데이트<br><br>On &lt;URL>에서 커피 머신을 구입하고 커피 2봉지를 무료로 제공하는 8월 프로모션에 대한 새로운 티저 섹션을 페이지 하단에 추가하려고 합니다. 또한 커피를 마시는 친구의 이미지를 찾아 티저에서 사용합니다 |
| AEM 일괄 업데이트 | 경험을 정확하고 최신 상태로 유지하기 위해 콘텐츠 요소를 제거, 대체 또는 추가하는 것과 같이, 동시에 여러 페이지에서 대량 작업을 수행할 수 있습니다. | `aem-sites-pages-bulkreplace` | Adobe Experience Manager(AEM) - AEM Sites | &lt;aem path>에서 &quot;MyBarista\&quot; 사본이 포함된 모든 페이지를 &quot;BrewPass&quot;로 업데이트합니다. |
| 조각에서 시각적 콘텐츠 조각으로 이동 | 자연어를 사용하여 Figma에서 Adobe Experience Manager으로 직접 디자인을 가져옵니다. 이 기술은 필요한 콘텐츠 모델, 콘텐츠 조각, 에셋 및 시각화 템플릿을 자동으로 만들어 비즈니스 사용자가 수동으로 설정하지 않고도 디자인에서 웹 준비가 된 콘텐츠로 몇 분 만에 이동할 수 있습니다. | `aem-sites-visualcontentfragments-create` | Adobe Experience Manager(AEM) - AEM Sites | &lt;Figure_URL>에서 가져오기 |

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 양식 만들기 | 일반 언어 설명, 첨부된 개요, 이미지 또는 PDF에서 새 적응형 양식을 생성합니다 | `aem-forms-adaptiveform-create` | Adobe Experience Manager(AEM) - AEM Forms | &quot;직원 온보딩 양식 만들기&quot;<br><br>&quot;첨부된 개요(이미지 또는 pdf)를 사용하여 양식 만들기&quot;<br><br>&quot;&lt;양식 유형> 적응형 양식 만들기&quot; |
| 양식 편집/업데이트 | 기존 양식 수정 - 필드 추가/편집, 간단한 레이아웃 조정, 제출 작업 구성 또는 첨부된 지침 문서의 변경 사항 적용 | `aem-forms-adaptiveform-edit` | Adobe Experience Manager(AEM) - AEM Forms | &quot;Add Middle Name field below First Name field&quot;<br><br>&quot;Put First Name and Last Name fields in a 2 column layout, 50/50&quot;<br><br>&quot;데이터를 REST 엔드포인트로 보내도록 양식을 구성&quot;<br><br>&quot;첨부된 지침 문서와 일치하도록 이 양식을 업데이트&quot;<br><br>&quot;Add &lt;existing field> field> field 아래에 &lt;field name> 필드 추가&quot; |
| 비즈니스 논리 추가 | 다른 필드의 값을 기반으로 필드를 표시하거나 숨기는 것과 같은 간단한 규칙을 만듭니다 | `aem-forms-adaptiveform-edit` | Adobe Experience Manager(AEM) - AEM Forms | &quot;직원 유형이 계약자인 경우에만 회사 필드 표시&quot;<br><br>&quot;다른 필드가 &lt;값>인 경우에만 &lt;필드> 필드 표시&quot; |
| 양식 포함 | 기존 양식 또는 새로 만든 양식을 지정된 AEM Sites 페이지에 배치합니다(Edge Delivery Services 페이지에서만 지원됨) | `aem-forms-adaptiveform-embed` | Adobe Experience Manager(AEM) - AEM Forms | &quot;이 양식을 사이트의 홈 페이지에 임베드&quot;<br><br>&quot;이 양식을 &lt;페이지 경로>에 임베드&quot; |

**관련 정보**

* [AEM의 에이전트 기능: 브랜드 경험 - 경험 프로덕션 - 사이트](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/brand-experience/experience-production/use-cases#use-cases-sites)

* [AEM의 에이전트 기능: 브랜드 경험 - 경험 프로덕션 - Forms](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/brand-experience/experience-production/use-cases#use-cases-forms)

### 개발

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| Cloud Manager 파이프라인 관리 | 로그, 아티팩트, 변수 및 설정을 포함한 AEM Cloud Manager 파이프라인 생성, 실행 및 모니터링 | `cloud-manager-pipeline-management` | AEM(Adobe Experience Manager) | &quot;프로그램 12345&quot;<br><br>&quot;에 대한 파이프라인을 나열합니다. 가장 최근 파이프라인의 상태는 무엇입니까?&quot; |
| Cloud Manager 환경 관리 | RDE, 환경 변수, 로그 및 백업을 포함한 AEM Cloud Manager 환경을 생성, 구성 및 유지 관리합니다. | `cloud-manager-environment-management` | AEM(Adobe Experience Manager) | &quot;프로그램 12345&quot;<br><br>&quot;내 RDE 다시 설정에 대한 환경 나열&quot; |
| Cloud Manager 프로그램 관리 | 파이프라인 및 환경을 포함하여 AEM Cloud Manager 프로그램 나열, 검사 및 삭제 | `cloud-manager-program-management` | AEM(Adobe Experience Manager) | &quot;내 Cloud Manager 프로그램 나열&quot;<br><br>&quot;프로그램 12345 세부 정보 가져오기&quot; |
| AEM 릴리스 업데이트 일정 관리 | 자동 유지 관리를 위해 매일 자동 중지 시간 및 업데이트가 없는 기간을 구성하고 Adobe의 글로벌 코드 동결 창을 봅니다 | `cloud-manager-release-management` | AEM(Adobe Experience Manager) | &quot;현재 방해 금지 시간 기간은 무엇입니까?&quot;<br><br>&quot;12월 20일부터 1월 2일까지를 업데이트 금지 기간으로 예약합니다.&quot; |

**관련 정보**

* [AEM의 에이전트 기능: 브랜드 경험 - 개발](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/brand-experience/development/use-cases)

### 온보딩

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 엔드 투 엔드 온보딩 가이드 | 필요한 특정 온보딩 작업을 모를 경우 전체 온보딩 라이프사이클, 저장소 선택, 폴더 위임, 태그, 메타데이터, 가져오기 및 검색 하위 기술을 조정합니다. | `aem-onboarding-workflow` | Adobe Experience Manager(AEM) - AEM Assets | &quot;AEM Assets으로 팀 온보딩&quot;<br><br>&quot;AEM DAM 온보딩 안내&quot; |
| 폴더 계층 구조 디자인 및 만들기 | 비즈니스 요구 사항 또는 CSV 입력을 기반으로 AEM Assets(`/content/dam` 아래)에서 확장 가능한 폴더 구조를 권장 및 만듭니다. | `aem-folder-management` | Adobe Experience Manager(AEM) - AEM Assets | &quot;라이프스타일 마케팅 자산에 대한 폴더 구조를 추천합니다.&quot;<br><br>&quot;이 CSV 파일을 기반으로 폴더를 만듭니다.&quot; |
| 태그 디자인 및 만들기 | 네임스페이스, 계층 태그 및 일괄 태그 작업과 같은 `/content/cq:tags` 아래에 제어된 태그 어휘를 디자인하고 만듭니다. | `aem-tag-taxonomy` | Adobe Experience Manager(AEM) - AEM Assets | &quot;제품 범주에 대한 네임스페이스를 사용하여 태그 분류법을 디자인합니다.&quot;<br><br>&quot;이 CSV에서 태그 가져오기&quot;<br><br>&quot;AEM에서 이러한 계층 구조 태그를 만듭니다.&quot; |
| 메타데이터 양식 만들기 및 할당 | 사용자 정의 메타데이터 양식을 디자인 및 만든 다음 필요한 경우 작성 UI 콘텐츠 작성자가 CSV, 테이블, 요구 사항 문서 또는 설명에서 사용하는 양식 을 폴더에 할당합니다. | `aem-metadata-form` | Adobe Experience Manager(AEM) - AEM Assets | &quot;이 필드 목록에서 메타데이터 양식을 만듭니다.&quot;<br><br>&quot;이 양식을 `campaigns` 폴더에 할당하십시오.&quot; |

**관련 정보**

* [AEM의 에이전트 기능: 브랜드 경험 - 온보딩](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/brand-experience/onboarding/use-cases)

## 콘텐츠 관리자

### 컨텐츠 검색

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 의미 체계 테마별 검색 | AI 기반의 의미 체계 일치를 사용하여 개념, 무드 또는 시각적 테마별로 에셋을 찾습니다. | `aem-assets-discovery` | Adobe Experience Manager(AEM) - AEM Assets | &quot;Find me morning coffee lifestyle images&quot; |
| 사용자 지정 메타데이터로 검색 | 사용자 지정 메타데이터 필드(예: 커피 블렌드, 브랜드, 로스트 레벨)로 자산을 필터링합니다. | `aem-assets-discovery` | Adobe Experience Manager(AEM) - AEM Assets | &quot;`Coffee Blend`이(가) `Morning Muse`인 자산을 찾습니다.&quot;<br><br>&quot;라이선스가 만료되지 않은 자산을 가져옵니다.&quot;<br><br>&quot;캠페인 이름이 설정되지 않은 자산을 찾습니다(속성은 적절한 결과를 위해 인덱싱되어야 함).&quot; |
| 승인 상태별 검색 | 승인 상태를 기반으로 에셋을 필터링합니다. 예를 들어 승인됨, 검토 중, 거부됨 또는 누락 상태가 있습니다. | `aem-assets-discovery` | Adobe Experience Manager(AEM) - AEM Assets | &quot;`Campaign` 폴더에 있는 승인된 모든 자산 표시&quot; |
| 폴더/경로로 검색 | AEM의 폴더 이름을 참조하는 자연어 프롬프트를 해석하여 에셋을 식별합니다. 저장소를 수동으로 탐색하지 않고 프롬프트에서 폴더를 언급하기만 하면 되므로 적절한 콘텐츠를 찾는 데 필요한 클릭 수를 크게 줄일 수 있습니다. | `aem-assets-discovery` | Adobe Experience Manager(AEM) - AEM Assets | &quot;`WKND`&quot; 폴더에 svgs가 있습니까?<br><br>&quot;2025년 11월 1일 이후에 수정된 자산을 `WKND` 폴더에 표시합니다.&quot; |

**관련 정보**

* [AEM의 에이전트 기능: Content Advisor - 콘텐츠 검색](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/content-advisor/discovery/use-cases)

### 콘텐츠 최적화

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 고해상도 렌디션 생성 및 채널 최적화 렌디션 | 지정된 해상도 및 품질 수준에서 에셋의 새 렌디션을 생성하여 수동으로 편집하지 않고도 채널 준비가 가능한 변형을 손쉽게 준비할 수 있습니다. 또한 Instagram 스토리와 같은 플랫폼별 요구 사항에 맞게 렌디션을 제작하여 에셋이 형식, 비율 및 품질 지침을 자동으로 충족하도록 할 수 있습니다. | `aem-assets-content-optimisation` | Adobe Experience Manager(AEM) - AEM Assets | &quot;`80% quality`&quot;<br><br>을(를) 사용하여 `2000px` 렌디션을 `JPEG`(으)로 만들기&quot;Instagram 스토리에 대한 렌디션 만들기&quot; |
| 브랜드 오버레이 및 복합 생성 | 정확한 배치로 기존 에셋에 홍보 그래픽, 오버레이 또는 배지를 적용하여 캠페인 준비 조합을 신속하게 만들 수 있습니다. | `aem-assets-content-optimisation` | Adobe Experience Manager(AEM) - AEM Assets | &quot;이미지 위에 `30%` 할인 그래픽을 적용하여 중앙에서 `100px`을(를) 배치합니다.&quot; |
| 이미지 개선 사항, 배경색 조정, 방향 변환 | 시각적 개선 사항 적용(이미지 선명하게 하기), 배경색 대체 및 방향 변환 수행 | `aem-assets-content-optimisation` | Adobe Experience Manager(AEM) - AEM Assets | &quot;`PNG`의 배경색을 `#ff8932`(으)로 변경합니다.<br><br>&quot;이미지 선명하게 하기&quot;<br><br>&quot;이미지를 가로로 미러링합니다.&quot; |

**관련 정보**

* [AEM의 에이전트 기능: 콘텐츠 관리자 - 콘텐츠 최적화](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/content-advisor/content-optimization/use-cases)

## 브랜드 거버넌스

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 지침 및 세그먼트 조회 | 세그먼트, 시장 또는 카테고리별로 세부 브랜드 가이드라인 검색 | enterprise-context | AEM(Adobe Experience Manager) | &quot;이 브랜드에 대한 음성 톤 지침은 무엇입니까?&quot;<br>&quot;상태 범주에 사용되는 클레임 범주를 나열합니다.&quot; |
| 브랜드 지침에 따라 콘텐츠 평가 | 구성된 브랜드 검사에 대해 게시/작성된 페이지, 텍스트 블록 또는 이미지 평가 | aem-governance | AEM(Adobe Experience Manager) | &quot;SecurBank 지침에 따라 이 랜딩 페이지를 평가하십시오.&quot;<br>&quot;이 태그가 음성 검사를 통과했습니까?&quot; |
| AEM 권한 디버그 | 권한 정책, ACL 및 상속 규칙을 디버그/이해합니다. | aem-governance | AEM(Adobe Experience Manager) | &quot;사용자 관리자가 `https://author/`에 `/content/folder/us`을(를) 쓸 수 있는 이유는 무엇입니까?&quot;<br>&quot;`https://author`의 `/content/dam`에서 샘플 작성자 쓰기를 샘플링할 수 없는 이유는 무엇입니까?&quot; |

**관련 정보**

* [AEM의 에이전트 기능: 브랜드 거버넌스](https://experienceleague.adobe.com/ko/docs/experience-manager-cloud-service/content/ai-in-aem/agentic-capabilities/brand-governance/use-cases)

## 데이터 인사이트

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [CJA 및 AA 보고서 및 지표 가져오기](data-insights/analytics-chat.md) | 실시간으로 CJA 또는 AA를 쿼리하여 지표, 차원, 세그먼트, 데이터 보기 및 보고서 세트를 가져옵니다 | `cja`, `aa` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;최근 30일 동안의 페이지 보기 수 표시&quot; <br> &quot;마스터 데이터 보기에 상위 세그먼트 나열&quot; |
| 비교 분석 | 채널, 기간 또는 세그먼트 간에 지표를 나란히 비교 | `cja-root-cause-analysis`, `cja`, `aa-root-cause-analysis`, `aa`, `dx-api`, `knowledge-graph` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;월별 채널별 매출액 비교&quot; <br> &quot;이번 분기에 모바일과 데스크탑 간 전환은 어떻게 보입니까?&quot; |
| 캠페인 성과 | 지정된 기간 동안 캠페인, 채널 및 웹 속성이 수행되는 방식을 측정합니다. | `cja`, `aa`, `dx-api`, `knowledge-graph` | | &quot;Acrobat 웹 캠페인은 지난 달에 어떻게 수행되었습니까?&quot; |
| Funnel 분석 | 각 단계에서 드롭오프로 여러 단계의 전환 단계를 거칩니다. | `cja`, `aa` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;체크아웃 funnel 안내&quot; <br> &quot;PDP에서 구매로 변환 funnel 표시&quot; |
| 예측 | 내역 CJA 또는 AA 데이터를 기반으로 향후 지표 값 예상 | `cja`, `aa` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;다음 30일 동안의 세션 예측&quot; <br> &quot;매출 목표를 달성하는 데 도움이 됩니까?&quot; |
| [근본 원인 분석](data-insights/root-cause-analysis.md) | 지표가 변경된 이유를 조사합니다. 드롭, 스파이크 및 예외 항목을 진단합니다. | `cja-root-cause-analysis`, `aa-root-cause-analysis` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;지난 주에 전환율이 떨어진 이유는 무엇입니까?&quot; <br> &quot;1월 15일 매출 급증의 원인은 무엇입니까?&quot; |
| 경영진 요약 및 KPI 다이제스트 | 이해 당사자에게 준비된 성능 요약, 규범적 권장 사항 및 슬라이드 데크 개요 작성 | `cja-executive-summary`, `cja-bacom-anomaly-tracker-v2`, `cja-cno-weekly-pulse`, `cja-reporting`, `cja`, `aa`, `dx-api` | Customer Journey Analytics (CJA), Adobe Analytics (AA) | &quot;지난달 요약 정보 제공&quot; <br> &quot;이번 분기 데이터로 슬라이드 데크 개요 만들기&quot; |
| [AA ↔ CJA 데이터 유효성 검사](data-insights/data-validation-aa-cja.md) | 특히 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 Adobe Analytics과 Customer Journey Analytics 간의 데이터를 비교, 감사 및 조정할 수 있습니다 | `aa-cja-validation`, `cja`, `aa`, `dx-api` | ADOBE ANALYTICS + CJA | &quot;내 AA 보고서 세트를 내 CJA 데이터 보기와 비교&quot; <br> &quot;AA와 CJA 간의 페이지 보기 유효성 검사&quot; |
| [데이터 집합 및 필드 품질 확인](data-insights/data-validation-aep.md) | Experience Platform 데이터 세트 및 필드에서 통계 및 의미 체계 유효성 검사를 실행하여 구현 후 또는 지속적으로 데이터 품질 문제를 파악합니다. <!--TODO: confirm skill ID(s) with engineering before publishing--> | `data-validation` | Adobe Experience Platform | &quot;데이터 집합 Electronics 샘플 1000의 유효성 검사&quot; <br> &quot;Customers_2024 데이터 집합의 전자 메일 필드 유효성 검사&quot; |
| 운영 시계열 및 인과관계 분석 | 인과 관계 속성을 사용하여 대상자, 데이터 세트 및 여정에 대한 내역 시계열 데이터를 쿼리하고 분석합니다. | `operational-stats-causal-analysis` | 모든 적격 지원 | &quot;지난 90일 동안의 대상 크기 트렌드를 표시합니다.&quot; <br> &quot;데이터 세트 행 수가 3월 3일에 급증한 이유는 무엇입니까?&quot; |
| 사용자 지정 CJA 스킬 만들기 | 분석 패턴을 세션 간에 지속되는 재사용 가능한 반복 가능한 스킬로 변환 | `cja-skill-creator` | Customer Journey Analytics(CJA) | &quot;이 주별 수익 분석을 재사용 가능한 스킬로 변환&quot; <br> &quot;월별 funnel 보고를 위한 스킬로 저장&quot; |

## 대상자

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [자연어에서 대상 만들기](audiences/create-audience-from-natural-language.md) | 각 단계에서 사용자 승인을 통해 단계별 대상 만들기 오케스트레이션 | `audience-creation-flow` | Real-Time CDP(RTCDP) | &quot;지난 30일 동안 구매한 사용자에 대한 대상 만들기&quot; <br> &quot;캘리포니아에서 고가치 충성도 구성원을 위한 세그먼트 만들기&quot; |
| PQL 정의 작성 | XDM 속성, 동작 이벤트 또는 기존 대상에서 대상 정의를 조합하고 집계 및 시간 창을 지원합니다. | `segment-definition-assembly` | Real-Time CDP(RTCDP) | &quot;3개 이상의 제품을 보았지만 구매하지 않은 사용자를 위한 PQL 만들기&quot; <br> &quot;내 이벤트 조건에 7일 기간 추가&quot; |
| 대상자 검색 및 찾기 | ID, 이름, 의미 체계 검색으로 대상 찾기, 중복 감지 및 중복 분석 | `audience-search` | Real-Time CDP(RTCDP) | &quot;모든 충성도 대상 찾기&quot; <br> &quot;내 &#39;휴일 쇼핑객&#39; 세그먼트가 중복됩니까?&quot; |
| 대상 크기 예상 | 폴링과 함께 Adobe Experience Platform 미리보기 API를 사용하여 PQL 표현식에 대한 프로필 도달 예상 | `audience-size-estimate` | Real-Time CDP(RTCDP) | &quot;이 대상자의 크기는 얼마나 됩니까?&quot; <br> &quot;이 PQL 표현식에 대한 도달 범위 예상&quot; |
| 대상자 크기 폭포 | PQL을 하위 술어로 분해하고 각 조건이 최종 대상 크기에 기여하는 방식을 표시합니다 | `audience-size-waterfall` | Real-Time CDP(RTCDP) | &quot;이 PQL의 폭포를 표시합니다.&quot; <br> &quot;각 조건에 따라 대상자가 줄어드는 방식을 분류합니다.&quot; |
| 타깃팅할 XDM 필드 검색 | 이름, 설명 또는 데이터 값으로 필드를 검색합니다. 해당 필드가 있는 위치와 이미 사용 중인 위치를 확인하세요. | `field-discovery` | Real-Time CDP(RTCDP) | &quot;충성도 고객을 타깃팅하는 데 사용할 수 있는 필드는 무엇입니까?&quot; <br> &quot;구매 내역과 관련된 필드 찾기&quot; |
| 대상자 게시/저장 | 이름 지정 규칙 및 준수 확인을 사용하여 Experience Platform 세그멘테이션 서비스에 대상 정의 유지 | `audience-publish` | Real-Time CDP(RTCDP) | &quot;초안으로 저장&quot; <br> &quot;이름이 &#39;봄 판매 구매자&#39;인 대상 게시&quot; |

## 여정

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [자연어에서 여정 만들기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-create){target="_blank"} | 텍스트 프롬프트 또는 업로드된 이미지/흐름도에서 AJO의 여정 생성 오케스트레이션 | `journey-create` | Adobe Journey Optimizer (AJO) | &quot;등록 후 전자 메일을 보내고 3일을 기다린 다음 후속 작업을 보내는 시작 여정 만들기&quot; <br> &quot;이 업로드된 순서도 이미지에서 여정 작성&quot; |
| [여정 충돌 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 활성 여정 간 대상 중복 감지, 충돌 예약 및 중복 제거 문제 | `journey-analyze-conflict` | Adobe Journey Optimizer (AJO) | &quot;여정 포기 여정이 다른 장바구니와 충돌합니까?&quot; <br> &quot;내 활성 여정 간 대상 겹침 확인&quot; |
| [여정 폴아웃 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 여정 중 고객이 중단되는 위치와 이유를 파악하고, 이탈로 이어지는 행동 패턴을 감지합니다 | `journey-analyze-fallout` | Adobe Journey Optimizer (AJO) | &quot;내 재참여 여정에서 사람들이 어디에 드롭하고 있습니까?&quot; <br> &quot;여정 X에서 폴아웃이 가장 높은 노드는 무엇입니까?&quot; |
| [사용자 지정 작업 오류 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 사용자 지정 작업이 실패하거나 여정 내에서 오류율이 급증하는 시점을 식별하고 실패가 더 광범위한 중단으로 이어지기 전에 근본 원인을 진단합니다 | `journey-analyze-custom-action` | Adobe Journey Optimizer (AJO) | &quot;충성도 등록 여정에서 사용자 지정 작업이 실패한 이유는 무엇입니까?&quot; <br> &quot;시작 여정에서 사용자 지정 작업 ExternalPush에 대한 오류율을 표시합니다.&quot; |
| [여정 예외 항목 탐지](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 과거 기준선에 대한 여정의 시작, 종료 또는 보내기 카운트에서 예상치 못한 급감, 강하 또는 평면선을 감지하고 확인하여 가능한 근본 원인을 표시합니다 | `journey-analyze-anomaly` | Adobe Journey Optimizer (AJO) | &quot;어제 환영 여정에 대한 항목이 왜 떨어졌습니까?&quot; <br> &quot;이번 주에 장바구니 포기 여정의 종료가 급증했습니까?&quot; |
| [비즈니스 성과 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 여정 성과를 분석하고 성과가 낮은 여정에 대한 구체적인 최적화 기회를 식별합니다. 참여도와 전환율을 향상시킬 수 있도록 경향, 병목 현상 및 낮은 결과를 초래하는 원인 표시 비즈니스 성과 통찰력을 기반으로 여정 디자인, 타기팅 또는 메시징 전략을 조정하는 실행 가능한 권장 사항을 얻을 수 있습니다. | 여정 분석 | Adobe Journey Optimizer (AJO) | &quot;여정 [여정 이름]의 성능을 분석하고 최적화를 권장합니다.&quot; <br> &quot;여정 [여정 이름]이(가) 지난달과 비교하여 성능이 낮은 이유는 무엇입니까?&quot; <br> &quot;여정 [여정 이름]의 성능을 향상시키려면 무엇을 변경해야 합니까?&quot; <br> &quot;[여정 이름] 여정 중 어느 부분이 전환이나 참여를 제한할 수 있습니까?&quot; |
| [여정 버전 비교](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/orchestrate-journeys/journeys-coworker-skills#journey-analyze){target="_blank"} | 두 여정 버전을 비교하고 노드, 연결 및 여정 수준 속성 변경의 구조적 차이를 검토합니다 | `journey-analyze-version-comparison` | Adobe Journey Optimizer (AJO) | &quot;시작 여정의 버전 2와 버전 3 비교&quot; <br> &quot;이 두 여정 버전 간의 변경 사항은 무엇입니까?&quot; |

**관련 정보**

* [AI를 사용하여 작업](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/get-started/ai-features#cx-coworker-skills){target="_blank"}에서는 Adobe Journey Optimizer의 동료 및 사용 가능한 기술에 대한 개요를 제공합니다.

## Journey Optimizer 컨텐츠 관리


| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [브랜드 지침 적용](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 캠페인 음성, 쓰기, 이미지, 용어 및 법적 지침을 위한 승인된 브랜드 지침을 찾아 선택하고 적용합니다. | `brand-lookup` | Adobe Journey Optimizer (AJO) | &quot;Acme 브랜드에 대한 작성 및 시각적 지침을 가져옵니다.&quot; |
| [콘텐츠 준비 확인](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 브랜드 음성, 편집 품질, 참여, 명확성 및 준비성에 대한 캠페인 콘텐츠를 검토합니다. | `check-content-readiness` | Adobe Journey Optimizer (AJO) | &quot;이 이메일 복사본을 보낼 준비가 되셨습니까? 브랜드 음성, 명확성, 접근성 및 규정 준수를 확인합니다.&quot; |
| [콘텐츠 작성 오케스트레이션](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 지원되는 채널 전반에서 캠페인 콘텐츠를 계획, 생성, 검토, 분석 및 저장합니다. | `orchestrate-content-authoring` | Adobe Journey Optimizer (AJO) | &quot;이 지침에서 가을 판매 이메일 캠페인에 대한 전체 컨텐츠 작성을 실행한 다음 최종 HTML을 검토하고 저장합니다.&quot; |
| [콘텐츠 디자인 평가](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 시각적 구현을 분석하고, 레이아웃 및 디자인 차이를 식별하며, 계층, 간격, 이미지 및 작업 호출에 대한 개선 사항을 권장합니다. | `assess-content-design` | Adobe Journey Optimizer (AJO) | &quot;이 이메일은 시각적으로 어떻습니까? 계층, 간격, 밀도, 이미지 및 CTA을 확인합니다.&quot; |
| [Figure에서 전자 메일 작성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 사본을 배송할 준비가 되면 라이브 피그마 프레임에서 최종 이메일 HTML을 생성합니다. 별도의 레이아웃 계획은 필요하지 않습니다. | `build-email-from-figma` | Adobe Journey Optimizer (AJO) | &quot;이 그림 프레임에서 최종 이메일 HTML을 작성합니다. 디자인의 사본은 제공해야 하는 것입니다.&quot; |
| [콘텐츠 전략 살펴보기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 접점, 채널, 대상 및 메시지 테마 간의 캠페인 전략을 비교하고, 쓰기 전에 각 메시지를 계획합니다. | `explore-content-strategy` | Adobe Journey Optimizer (AJO) | &quot;단일 윈백 이메일을 3터치 이메일 및 SMS 프로그램과 비교&quot; |
| [콘텐츠 생성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 이메일, SMS, 푸시, WhatsApp 및 랜딩 페이지를 포함하여 지원되는 채널에 대해 제한된 새 마케팅 메시지를 작성하거나 초안을 작성합니다. | `generate-content` | Adobe Journey Optimizer (AJO) | &quot;승인된 캠페인 방향에서 이메일, 푸시 및 SMS에 대한 온브랜드 실행 사본을 만듭니다.&quot; |
| [콘텐츠 개요 만들기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 승인된 캠페인 방향을 오퍼, 색조, 주요 메시지, 채널, 로케일, 변형 및 필수 콘텐츠에 대한 요구 사항으로 전환합니다. | `content-brief` | Adobe Journey Optimizer (AJO) | &quot;이 브리핑을 미국 가입자에게 보내는 따뜻한 윈백 이메일에 대한 작성 요구 사항으로 전환하십시오. 일요일까지 20% 할인, CTR을 KPI로 사용합니다.&quot; |
| [이미지 생성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 히어로 이미지, 자르기, 오버레이, 변형 및 서명된 자산을 포함하여 승인된 배치에 대한 캠페인 시각화를 만들거나 변형할 수 있습니다. | `generate-image` | Adobe Journey Optimizer (AJO) | &quot;승인된 브랜드 방향을 사용하여 이 봄 판매 이메일에 대한 프리미엄 영웅 이미지를 생성합니다.&quot; |
| [채널 콘텐츠 저장](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 승인된 캠페인 컨텐츠를 초안 자산으로 저장하거나 AJO 또는 지원되는 다른 작업 솔루션에서 소스 템플릿에 채웁니다. | `save-channel-content` | Adobe Journey Optimizer (AJO) | &quot;승인된 콘텐츠를 소스 템플릿에 입력하고 검토할 수 있도록 준비합니다.&quot; |
| [콘텐츠 수정 및 재생성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills#ce-channel-content){target="_blank"} | 문구, 색조, 번역, 제목 줄, 작업 호출 및 검토 결과를 포함하여 기존 캠페인 콘텐츠에 대해 확인된 변경 사항을 적용합니다. | `revise-regenerate-content` | Adobe Journey Optimizer (AJO) | &quot;승인된 오퍼와 CTA을 유지하면서 톤을 더 따뜻하게 합니다.&quot; |

**관련 정보**

* [AI를 사용하여 작업](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/get-started/ai-features#cx-coworker-skills){target="_blank"}에서는 Adobe Journey Optimizer의 동료 및 사용 가능한 기술에 대한 개요를 제공합니다.

## 마케팅 프로그램

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 프로그램 빌드 | 일반 언어 설명 또는 업로드한 개요에서 생성된 스마트 캠페인, 예약 및 자리 표시자 이메일을 사용하여 기존 프로그램 템플릿을 새 프로그램으로 조정 | `build-programs` | Adobe Marketo Engage | &quot;8월 제품 데모에 대한 웨비나 등록 프로그램을 만드십시오.&quot;<br><br>&quot;잠재 고객이 50점을 달성하면 트리거되는 프로그램을 만드십시오.<br><br>&quot;비활성 잠재 고객에 대한 3개의 이메일 재참여 시리즈를 만드십시오.&quot; |
| 간단한 것에서 프로그램을 시작하다 | 일반 언어 개요 또는 업로드된 캠페인 문서를 작업 프로그램으로 바꿉니다. 가장 일치하는 템플릿을 복제하고 스마트 캠페인과 토큰을 이월하고 이벤트 세부 정보를 업데이트합니다. 검토할 수 있도록 새 스마트 캠페인이 비활성화된 상태로 남음 | `build-programs` | Adobe Marketo Engage | &quot;저는 9월 10일 시카고에서 웨비나를 개최합니다. 나를 위해 프로그램을 설정합니다.&quot;<br><br>&quot;이 개요에서 다음 달의 로드쇼 프로그램을 설정하고 이벤트 토큰을 업데이트합니다.&quot; |
| 기존 프로그램 복제 및 조정 | 새 도시, 분기 또는 지역에 대한 이전 프로그램을 복사하고 날짜, 토큰 및 이름을 업데이트합니다. 하위 스마트 캠페인은 활성화될 때까지 이월되고 비활성화된 상태로 유지됩니다 | `build-programs` | Adobe Marketo Engage | &quot;10월 17일에 뉴욕에서의 마지막 분기 이벤트 프로그램을 복제하고 날짜와 토큰을 업데이트하십시오.&quot;<br><br>&quot;영국 대상의 시카고 로드쇼 프로그램을 복제합니다.&quot; |
| 자격 논리를 사용하여 스마트 캠페인 구축 | 트리거 또는 일괄 스마트 캠페인을 만들고, 양식 작성 또는 점수 도달과 같은 스마트 목록 규칙을 추가하고, 이메일 전송과 같은 흐름 단계를 구성합니다 | `build-programs` | Adobe Marketo Engage | &quot;잠재 고객이 연락처 양식을 작성할 때 환영 이메일을 보내는 트리거 캠페인을 만듭니다.&quot;<br><br>&quot;50점을 기록한 잠재 고객에 대한 일괄 캠페인을 작성하고 이메일 보내기 단계를 추가합니다.&quot; |

## 충성도

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [충성도 문제를 만들고, 편집하고, 관리합니다](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/loyalty-challenges/loyalty-coworker-skills#loyalty-challenge-management){target="_blank"} | 충성도 프로그램 관리 간소화 및 가속화 | `loyalty` | Adobe Journey Optimizer (AJO) | &quot;회원들이 새로운 계절 음료를 시도하도록 유도하는 문제를 만드십시오.&quot; <br> &quot;회원 감소율이 가장 높은 충성도 문제를 보여 주십시오.&quot; |
| [충성도 프로그램 성과 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/loyalty-challenges/loyalty-coworker-skills#loyalty-data-insight){target="_blank"} | 자연어를 사용하여 충성도 포인트, 멤버 계층, 환급 및 매출 지표를 쿼리하고 분석합니다. | `loyalty-insights` | Adobe Journey Optimizer (AJO) | &quot;2026년 8월 중에 충성도 포인트를 몇 개나 부여받았습니까?&quot; <br> &quot;충성도 프로그램의 총 수입을 2026년 8월 중 일별로 분류하여 표시합니다.&quot; |

**관련 정보**

* [AI를 사용하여 작업](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/get-started/ai-features#cx-coworker-skills){target="_blank"}에서는 Adobe Journey Optimizer의 동료 및 사용 가능한 기술에 대한 개요를 제공합니다.

## Journey Optimizer에서의 콘텐츠 제작

동료 채팅을 사용하여 캠페인 메시지 사본 및 이메일 HTML을 계획, 생성, 평가 및 세분화한 다음 승인된 콘텐츠를 Journey Optimizer에 직접 저장하거나 전달합니다.

### 메시지 복사

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [마케팅 개요 캡처](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 캠페인 전략을 캡처하고 크리에이티브 브리프를 진행합니다. | `capture-marketing-brief` | Adobe Journey Optimizer (AJO) | &quot;시즌 제품 출시에 대한 마케팅 개요를 만드세요&quot; <br> &quot;이 캠페인 전략을 마케팅 설명서로 바꾸세요&quot; |
| [Creative Brief 캡처](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 복사 실행 사양을 구조화하고 컨텐츠 계획 행렬을 작성합니다. | `capture-creative-brief` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 마케팅 설명서에서 크리에이티브 개요 만들기&quot; <br> &quot;전자 메일 및 SMS 캠페인에 대한 콘텐츠 계획 매트릭스 작성&quot; |
| [콘텐츠 전략 계획](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 복사 생성을 앞두고 메시지 맵, 이야기 호 및 채널 역할을 브레인스토밍 합니다. | `plan-content-strategy` | Adobe Journey Optimizer (AJO) | &quot;전자 메일 및 푸시에서 제품 출시에 대한 메시지 전략을 계획합니다.&quot; <br> &quot;환영 캠페인에 대한 설명 호 제안&quot; |
| [복사본 생성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 이메일, SMS, 푸시, WhatsApp, 소셜 및 배너에 대한 순 새로운 브랜드 내 사본을 생성합니다. | `generate-copy` | Adobe Journey Optimizer (AJO) | &quot;새 시즌 컬렉션을 발표하는 온-브랜드 이메일 작성&quot; <br> &quot;장바구니를 포기한 고객을 위한 SMS 알림 초안 작성&quot; |
| [이미지 생성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | Firefly을 사용하여 캠페인 이미지를 생성, 자르기, 오버레이, 다양화 및 서명합니다. | `generate-image` | Adobe Journey Optimizer (AJO) | &quot;시즌 캠페인 전자 메일에 대한 영웅 이미지 생성&quot; <br> &quot;이 승인된 캠페인 이미지에서 배너 변형 만들기&quot; |
| [복사본 평가](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 브랜드 및 채널 표준에 따라 기존 사본을 평가하고 점수를 매깁니다. | `evaluate-copy` | Adobe Journey Optimizer (AJO) | &quot;브랜드 지침에 따라 이 전자 메일 복사본을 평가하십시오.&quot; <br> &quot;이 푸시 메시지가 채널 표준을 충족하는지 확인하십시오.&quot; |
| [복사본 편집](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 평가 수정, 구문 변경, 번역 및 지시된 수정 버전 등 기존 사본을 즉각적으로 편집합니다. | `edit-copy` | Adobe Journey Optimizer (AJO) | &quot;평가 피드백을 처리하기 위해 이 전자 메일 복사본을 수정하십시오.&quot; <br> &quot;이 승인된 SMS 복사본을 프랑스어로 번역&quot; |
| [캠페인 콘텐츠 확장](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 승인된 콘텐츠 계획 매트릭스를 채널, 로케일, 대상자 및 변형 간에 있는 단위당 사본으로 팬합니다. | `expand-campaign` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 콘텐츠 플랜의 각 채널에 대한 복사본 생성&quot; <br> &quot;이 캠페인을 각 대상에 대한 영어 및 프랑스어 변형으로 확장&quot; |
| [시각적 HTML 분석](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 시각적 검사를 위해 HTML 사본을 스크린샷에 렌더링합니다. | `analyze-visual-html` | Adobe Journey Optimizer (AJO) | &quot;레이아웃을 검사할 수 있도록 이 전자 메일 HTML을 렌더링합니다.&quot; <br> &quot;이 Campaign HTML의 스크린샷 표시&quot; |
| [콘텐츠 저장](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 승인된 컨텐츠를 다시 Adobe Journey Optimizer, Adobe Campaign v8 또는 Marketo에 저장합니다. | `save-content` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 이메일 콘텐츠를 Journey Optimizer에 저장&quot; <br> &quot;승인된 SMS 사본을 Journey Optimizer에 저장&quot; |

### 이메일 디자인

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [전자 메일 작성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 플랜은 마케팅 목표 및 브랜드 입력에서 구조 및 스타일을 차단합니다. | `compose-email` | Adobe Journey Optimizer (AJO) | &quot;브랜드 지침을 사용하여 제품 출시에 대한 이메일 레이아웃을 계획합니다.&quot; <br> &quot;영웅 섹션, 제품 하이라이트 및 call to action으로 시작 이메일 구성&quot; |
| [전자 메일 작성](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 레이아웃 계획, 스크린샷 또는 그림 디자인 링크에서 이메일 HTML을 작성, 조정, 편집 및 정교화합니다. | `build-email` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 레이아웃 계획에서 이메일 HTML 작성&quot; <br> &quot;이 그림 디자인 링크에서 이메일 만들기&quot; |
| [디자인 시스템 유지](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 토큰, 레이아웃 패턴 및 브랜드 언어와 같은 브랜드의 재사용 가능한 이메일 디자인 시스템을 유지 관리합니다. | `maintain-design-system` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 브랜드 색상으로 이메일 디자인 시스템 업데이트&quot; <br> &quot;이 재사용 가능한 제품 레이아웃을 이메일 디자인 시스템에 추가&quot; |
| [준수 검토](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 브랜드 및 채널 지침 및 전달성 표준에 따라 조립된 이메일을 감사합니다. | `review-compliance` | Adobe Journey Optimizer (AJO) | &quot;브랜드 및 채널 지침에 따라 이 전자 메일을 검토하십시오.&quot; <br> &quot;전달 전에 이 전자 메일에서 전달성 문제를 검토하십시오.&quot; |
| [디자인 검토](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 계층, 간격, 이야기 흐름 및 브랜드 적합도에 대한 주관적인 디자인 피드백을 제공합니다. | `review-design` | Adobe Journey Optimizer (AJO) | &quot;이 전자 메일의 시각적 계층 구조 및 간격 검토&quot; <br> &quot;이 전자 메일 디자인이 브랜드에 맞는지 평가&quot; |
| [접근성 검토](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | WCAG 2.1 AA 접근성 감사를 실행합니다. | `review-accessibility` | Adobe Journey Optimizer (AJO) | &quot;WCAG 2.1 AA 접근성 문제에 대해 이 전자 메일 감사&quot; <br> &quot;이 전자 메일의 색상 대비 및 이미지 대체 텍스트 확인&quot; |
| [전자 메일 전달](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"} | 승인된 HTML을 Adobe Journey Optimizer 또는 Adobe Campaign으로 내보내고 전달합니다. | `handoff-email` | Adobe Journey Optimizer (AJO) | &quot;이 승인된 전자 메일 HTML을 Journey Optimizer으로 내보내기&quot; <br> &quot;승인된 전자 메일을 Journey Optimizer으로 전달&quot; |

**관련 정보**

* [콘텐츠 관리를 위한 동료](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-management-coworker-skills){target="_blank"}에서는 Adobe Journey Optimizer의 콘텐츠 관리 도구 및 사용 가능한 기술에 대한 세부 정보를 제공합니다.

## 최적화

동료 채팅을 사용하여 실험을 탐색, 분석 및 계획하고, Adobe Target 활동, 대상 및 권장 사항을 만들고, 실행하고, 문제를 해결할 수 있습니다.

### 실험 분석 및 전략

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 실험 검색 및 탐색 | 실험 개요, 목록, 카운트, 원시 결과, 통찰력 및 기회 조회 | `experiment-explorer` | ADOBE TARGET / ADOBE JOURNEY OPTIMIZER | &quot;내 실험 표시&quot; · &quot;활성 테스트 나열&quot; · &quot;얼마나 많은 실험이 실행되고 있습니까?&quot; |
| 실험 성능 분석 | 포트폴리오 실행, 단일 실험 상태 점검, 경영진 브리프 및 지표를 통한 교차 실험 보고서를 가져올 수 있으며 선택적으로 CJA 데이터로 보강할 수 있습니다. | `experiment-analysis` | ADOBE TARGET / ADOBE JOURNEY OPTIMIZER | &quot;A/B 테스트의 성과는 어떻습니까?&quot; · &quot;CJA 지표를 사용하여 내 활동에 대한 보고서를 생성합니다.&quot; · &quot;이 테스트가 정상입니까?&quot; |
| 실험 계획 및 설계 | 실행할 다음 테스트, 지정된 주제에 대한 디자인, 목표-지표 변환, 실패한 테스트에 대한 복구 지침 또는 순차적 다중 실험 로드맵 | `experiment-strategist` | ADOBE TARGET / ADOBE JOURNEY OPTIMIZER | &quot;다음에는 무엇을 테스트해야 합니까?&quot; · &quot;체크아웃 전환 개선을 위한 실험 설계 지원&quot; · &quot;3분기 테스트 로드맵 구축&quot; |
| 실험 내역 검색 | 이전 실험에서 가설, 학습, 결과 및 처리를 검색하거나, 주제별로 이전 실험을 찾거나, 외부 CSV를 수집하여 결과를 보강합니다 | `experiment-knowledge-base` | ADOBE TARGET / ADOBE JOURNEY OPTIMIZER | &quot;실험 X에 대해 우리가 아는 것은 무엇인가?&quot; · &quot;이 가설을 이전에 테스트했습니까?&quot; · &quot;이 CSV 수집&quot; |

### Target 활동 및 대상

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 대상 엔티티 찾아보기 | 활동, 오퍼, 대상, mbox, 속성, 작업 공간, AT.js 구성, 응답 토큰 및 개정 내역을 검색, 검사 및 카운트합니다. 활동의 강제 경험 스크린샷도 캡처할 수 있습니다 | `target-browse` | Adobe Target | &quot;내 A/B 테스트 나열&quot; · &quot;이번 달에 시작된 활동은 몇 개입니까?&quot; · &quot;활동 12345 세부 정보 표시&quot; |
| 활동 성능 분석 | 단일 활동에 대한 전환율, 상승도, 신뢰 구간, 매출 및 노출 수를 가져옵니다. 사실을 말하고 승자를 선언하지 않음 | `target-analyze` | Adobe Target | &quot;활동 X의 성과는 어떻습니까?&quot; · &quot;전환 상승도 표시&quot; · &quot;체크아웃 테스트를 위한 AOV는 무엇입니까?&quot; |
| 선적을 받거나 판결을 중지하다 | 원시 카운트 및 구성 결함 검사에서 두 비율 중요도로 계산된 활동에 대한 SHIP, WAIT, STOP 또는 FIX 권장 사항 가져오기 | `target-activity-verdict` | Adobe Target | &quot;이 테스트를 배송해야 합니까?&quot; · &quot;어떤 변형이 이겼습니까?&quot; · &quot;이것이 아직 중요한가?&quot; |
| 활동 만들기 및 구성 | 활동, 오퍼 및 응답 토큰을 생성, 업데이트 및 구성하고, QA 미리보기 URL을 생성하고, 오퍼 컨텐츠를 작성하거나 최적화합니다 | `target-design` | Adobe Target | &quot;홈 페이지에 대한 A/B 테스트 만들기&quot; · &quot;트래픽 분할 업데이트&quot; · &quot;이 오퍼의 JS 최적화&quot; |
| 시각적 경험 작성기 활동 만들기 | 라이브 페이지 URL에 대해 DOM 수정 사항으로 변형을 작성하는 VEC(시각적 경험 작성기) 활동과 이를 확장하는 페이지 전달 대상을 만들고 편집합니다 | `target-vec` | Adobe Target | &quot;홈 페이지에 대한 VEC A/B 테스트 만들기&quot; · &quot;시각적 편집기에서 영웅 헤드라인 변경&quot; |
| 처음부터 전체 테스트 설정 | A/B, XT 및 VEC 테스트에 대한 엔드투엔드 활동 만들기 안내서를 받아 요구 사항 수집, 사전 요구 사항, 만들기, 예약 및 우선 순위, QA 링크 및 선택적 활성화를 다룹니다 | `target-setup` | Adobe Target | &quot;전체 A/B 테스트 설정을 소개합니다.&quot; · &quot;Target을 처음 접했습니다. 첫 번째 테스트를 작성하는 데 도움을 주세요.&quot; |
| 프로그램 상태 감사 | 위험 및 충돌 감지, 잘못된 구성 결과, 대상 및 제공 위생, 신속한 성공 권장 사항을 다루는 프로그램 전반의 상태 감사 받기 | `target-intelligence` | Adobe Target | &quot;내 Target 활동 감사&quot; · &quot;위험하거나 잘못 구성된 테스트 찾기&quot; · &quot;정리해야 할 사항&quot; |
| 우승 패턴 찾기 | 우승 패턴, 효과적인 전략, 고성능 대상 또는 콘텐츠에 대한 Target 내역을 확인한 다음, 자신의 데이터에 기반을 두고 다음에 테스트할 항목에 대한 추천을 받습니다 | `target-strategist` | Adobe Target | &quot;우리에게 도움이 되는 것은 무엇입니까?&quot; · &quot;우승 패턴 표시&quot; · &quot;과거 결과를 기반으로 다음에 무엇을 테스트해야 합니까?&quot; |
| 샘플 크기 및 기간 계산 | Bonferroni 수정을 통해 A/B/n 샘플 크기, 테스트 기간 및 전환율 및 방문자당 매출 지표에 대한 감지 가능한 상승도를 계획합니다. | `target-test-calculator` | Adobe Target | &quot;A/B 테스트를 얼마 동안 실행해야 합니까?&quot; · &quot;어떤 샘플 크기가 필요합니까?&quot; · &quot;내 테스트에 아직 전원이 공급됩니까?&quot; |
| 프로그램 수준 성능 롤업 가져오기 | 개요 패널, 최근 실행 표, 모든 활동에 대한 총 승패/상승도 센서스, 단일 활동 트렌드 및 모멘텀 읽기를 확인하십시오 | `target-portfolio-report` | Adobe Target | &quot;내 Target 프로그램의 상태 검사를 제공합니다.&quot; · &quot;내 최고의 테스트와 최악의 테스트는 무엇입니까?&quot; · &quot;활동 X가 승리로 가는 트렌드입니까?&quot; |
| 자연어로 대상자 만들기 | 자연어 설명, 명시적 규칙 조건 또는 인라인 또는 업로드된 값 목록에서 Target 네이티브 대상을 만들거나 편집합니다. 요청을 규칙 문법에 매핑하고 쓰기 전에 규칙 트리의 유효성을 검사합니다 | `target-audience-composer` | Adobe Target | &quot;캘리포니아에서 재방문자 대상 만들기&quot; · &quot;이러한 우편번호에서 대상 만들기&quot; · &quot;재방문자로 대상 X 좁히기&quot; |

### 추천

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 권장 사항 엔티티 찾아보기 | 권장 사항 기준, 컬렉션, 디자인, 프로모션, 제외, 카탈로그 및 피드를 찾아보고 검사하며, 정리 권고 사항 및 카탈로그 속성 지침을 얻을 수 있습니다. | `target-recs` | Adobe Target | &quot;내 권장 사항 기준 나열&quot; · &quot;어떤 디자인이 있습니까?&quot; · &quot;어떤 recs를 정리할 수 있습니까?&quot; |
| 권장 사항 문제 진단 | 활동, 기준, 피드, 컬렉션 및 디자인 체인을 추적하여 권장 사항이 비어 있거나 오래되었거나 표시되지 않는 이유를 설명합니다 | `target-recs-diagnose` | Adobe Target | &quot;내 권장 사항이 비어 있는 이유는 무엇입니까?&quot; · &quot;왜 recs 활동이 48시간 동안 &#39;결과가 준비되지 않음&#39;입니까?&quot; |
| 작성자 권장 사항 | 한 번에 많은 활동에서 제어된 벌크 작업을 포함하여 권장 사항 기준, 컬렉션, 디자인, 제외, 프로모션, 피드 및 recs 활동을 만들고 업데이트합니다 | `target-recs-design` | Adobe Target | &quot;가장 많이 본 항목 기준 만들기&quot; · &quot;50달러 미만의 재고 제품 컬렉션 구축&quot; · &quot;모든 판매 활동에 블랙 프라이데이 날짜 적용&quot; |

## 기본 요소

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 제품 지식 및 설명서 | 공식 Adobe 문서에서 방법, 개념, 문제 해결 및 모범 사례 질문에 답변합니다 | `product-knowledge` | 모든 적격 지원 | &quot;스트리밍 대상을 설정하려면 어떻게 해야 합니까?&quot; <br> &quot;일괄 처리와 스트리밍 세분화 간의 차이점은 무엇입니까?&quot; |
| Experience Platform/Journey Optimizer 엔티티 쿼리 | 플랫폼 엔터티에 대한 질문을 위한 기본 진입점 역할을 합니다. 필요에 따라 KG, 필드 검색 또는 API로 라우팅합니다. | `operational-insights` | 모든 적격 지원 | &quot;보유한 데이터 세트가 몇 개입니까?&quot; <br> &quot;모든 활성 여정 표시&quot; <br> &quot;대상 나열&quot; |
| 지식 그래프 쿼리 | 단일 SQL 쿼리를 통한 집계 카운트, 교차 엔티티 조인, 관계 조회 및 메타데이터 탐색 | `knowledge-graph` | 모든 적격 지원 | &quot;이 데이터 집합을 사용하는 대상자는 누구입니까?&quot; <br> &quot;스키마와 데이터 세트 간 관계 표시&quot; |
| Experience Platform / Journey Optimizer / Customer Journey Analytics API 작업 | 지식 그래프에 없는 돌연변이, 실시간 상태 확인 및 엔티티 유형에 대한 직접 API 게이트웨이 제공 | `cxo-api` | 모든 적격 지원 | &quot;데이터 집합 X 삭제&quot; <br> &quot;내 일괄 처리 수집 작업의 상태 확인&quot; |
| 엔티티 해결 및 연결 | 의미 체계 및 어휘 검색을 사용하여 실제 Experience Platform 엔티티에 대한 엔티티 언급을 해결하고 XDM 필드를 검색할 수 있습니다 | `entity-linking` | Adobe Experience Platform | &quot;실제 대상자로 &#39;휴일 쇼핑객&#39; 해결&quot; <br> &quot;구매 내역과 관련된 필드 찾기&quot; |
| 사용자 정의 스킬 관리 | 세션 간에 지속되는 사용자 소유 재사용 가능한 스킬 저장, 수정 또는 삭제 | `manage-skill` | 모든 적격 지원 | &quot;해당 워크플로우를 스킬로 저장&quot; <br> &quot;내 주간 보고서 스킬 삭제&quot; <br> &quot;재사용 가능한 스킬로 전환&quot; |
| 스트리밍 용량 및 위반 모니터링 | 샌드박스 전체에서 현재 및 과거 스트리밍 사용량, 용량 및 위반 상태 확인 | `observability-streaming-capacity`, `observability-streaming-usage`, `observability-capacity-breaches` | Adobe Experience Platform | &quot;현재 샌드박스의 현재 스트리밍 용량은 얼마입니까?&quot; <br> &quot;현재 샌드박스가 지난 주에 용량 제한을 위반했습니까?&quot; |
| [상태 검사 평가 결과 보기](https://experienceleague.adobe.com/ko/docs/experience-platform/run-and-operate/health-checks/overview) | 샌드박스에 대한 최신 상태 검사 평가를 보고 실패한 검사를 드릴다운한 다음 영향을 받는 엔티티를 확인합니다 | `rao-view-latest-health-checks-assessment` | Adobe Experience Platform | &quot;내 샌드박스에 문제가 있습니까?&quot; <br> &quot;내 최신 상태 검사 평가에 대해 알려주세요.&quot; <br> &quot;사용자 지정 네임스페이스 설명 검사에 대한 문제는 무엇입니까?&quot; |
| 상태 검사 문제 수정 | 플래그가 지정된 ID 네임스페이스, 병합 정책 및 스키마 문제를 변경하기 전에 승인과 함께 채팅에서 직접 수정합니다 | `rao-remediate-identity-namespace-description`, `rao-remediate-merge-policy-duplicate-name`, `rao-remediate-missing-audit-field-group`, `rao-remediate-default-merge-policy-naming` | Adobe Experience Platform | &quot;ID 네임스페이스 설명 수정&quot; <br> &quot;중복 병합 정책 이름 수정&quot; <br> &quot;감사 필드 그룹이 누락된 스키마 수정&quot; <br> &quot;기본 병합 정책 이름 수정&quot; |

## 데이터 관리

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [최적화 또는 정리할 가치가 있는 데이터 찾기](./data-management/manage-data-lake-retention.md#find-data-worth-optimizing) | 가장 크거나, 가장 적게 사용되거나, 잊어버린 데이터 세트를 정리 후보 또는 데이터 레이크 보존 정책으로 표시하여 경험 이벤트 데이터를 최적화할 수 있는지 여부를 파악합니다 | `List datasets` | Adobe Experience Platform | &quot;내 데이터가 최적화될 수 있다고 생각합니다.&quot; <br> &quot;내 데이터의 가치를 이해할 수 있도록 도와줍니다.&quot; <br> &quot;내 샌드박스 데이터 최적화&quot; <br> &quot;내 샌드박스 데이터 세트 정리&quot; |
| [데이터 집합에 대한 사용 조사 및 유지 관리](./data-management/manage-data-lake-retention.md#check-how-actively-a-dataset-is-used) | 자세히 살펴볼 가치가 있는 데이터 세트를 찾으면 데이터 세트가 얼마나 활발하게 사용되는지 확인하고, 잠재적인 데이터 레이크 보존 정책의 영향을 모델링하고, 변경 전 검토 및 승인을 통해 준비가 되면 해당 정책을 설정, 변경 또는 제거합니다 | `Analyze dataset usage`, `Analyze dataset retention`, `Manage dataset retention` | Adobe Experience Platform | &quot;웹 이벤트 데이터 세트가 얼마나 활발하게 사용되고 있습니까?&quot; <br> &quot;이 데이터 세트에 60일 보존 기간을 설정하면 어떤 영향이 있습니까?&quot; |

## 샌드박스 도구

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| [샌드박스 간 개체 이동](/help/chat/use-cases/sandbox-tooling/sandbox-tooling.md) | 종속성 자동 해결을 통해 샌드박스 간에 스키마, 대상 및 기타 오브젝트 구성을 원활하게 마이그레이션할 수 있습니다. | `sandbox-tooling-workflow` | Adobe Experience Platform | &quot;스키마 Luma 충성도 멤버 Platinum을 현재 샌드박스에서 프로덕션 샌드박스로 이동&quot; <br> &quot;미국 Gold 충성도 멤버 대상을 단계로 승격&quot; |

## 고객 경고

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| 경고 구독 관리 | 자연어 대화를 통해 경고 구독을 보고 관리합니다. | `alerts-subscribe` | Adobe Experience Platform | &quot;어떤 경고를 구독했습니까?&quot;<br><br>&quot;이 경고에 구독하십시오.&quot;<br><br>&quot;이 경고에 대한 내 구독을 제거하십시오.&quot; |
| 경고 활동 검토 | 지정된 기간 동안 현재 경고 상태 및 내역 경고 활동을 검토합니다. | `alerts-list` | Adobe Experience Platform | &quot;지난 24시간 동안 무슨 일이 있었습니까?&quot;<br><br>&quot;지난 24시간 동안 어떤 경고가 트리거되었습니까?&quot;<br><br>&quot;지난 7일 동안의 활성 경고를 표시합니다.&quot; |
| 반복 경고 패턴 식별 | 경고 내역을 분석하여 자주 트리거되는 경고 유형과 운영 트렌드를 식별합니다. | `alerts-list` | Adobe Experience Platform | &quot;트리거된 상위 3개의 경고 유형을 표시합니다.&quot;<br><br>&quot;이번 달에 가장 많이 발생한 경고 유형은 무엇입니까?&quot;<br><br>&quot;지난 7일 동안 어떤 경고 패턴이 표시됩니까?&quot; |
| 우선 순위가 높은 문제에 집중 | 심각도별로 경고 활동을 필터링하여 조사 작업의 우선 순위를 지정합니다. | `alerts-list` | Adobe Experience Platform | &quot;심각도가 높은 경고만 표시합니다.&quot;<br><br>&quot;이번 주에 트리거된 중요한 경고는 무엇입니까?&quot;<br><br>&quot;지난 30일 동안의 중요한 경고를 표시합니다.&quot; |
| 경고의 영향 반경 이해 | 경고의 영향을 가장 많이 받는 객체를 식별하고 조사가 시작되는 위치를 결정합니다. | `alerts-list` | Adobe Experience Platform | &quot;영향을 받는 상위 5개의 개체는 무엇입니까?&quot;<br><br>&quot;가장 심각도가 높은 경고와 관련된 개체는 무엇입니까?&quot; |
| 영향을 받는 개체에 경고 유형 연결 | 경고 유형과 영향을 받는 리소스 간의 관계를 분석합니다. | `alerts-list` | Adobe Experience Platform | &quot;어떤 경고 유형이 이 데이터 세트에 가장 자주 영향을 미쳤습니까?&quot;<br><br>&quot;경고 유형과 영향을 받은 개체 간의 관계를 표시합니다.&quot;<br><br>&quot;영향을 가장 많이 받은 최상위 개체에 영향을 가장 많이 받은 경고 유형은 무엇입니까?&quot; |
| 내 경고에 집중 | 구독하고 모니터링을 담당하는 경고를 분석합니다. | `alerts-list` | Adobe Experience Platform | &quot;내가 구독하는 심각도가 높은 경고를 표시합니다.&quot;<br><br>&quot;이번 주에 트리거된 내 경고에서 어떤 경고가 발생합니까?&quot;<br><br>&quot;구독된 경고 중 주의가 필요한 것이 있습니까?&quot; |

## 워크플로우 및 계획

| 사용 사례 | 설명 | 스킬 | 애플리케이션 | 샘플 프롬프트 |
| --- | --- | --- | --- | --- |
| Planning 작업 영역 관리 | Workfront Planning 작업 공간, 섹션, 레코드 유형 및 필드를 구축하고 발전시켜 프로그램을 구성하고 작업을 추적합니다. | `manage-workfront-planning`, `wf-planning-solution-architect` | Workfront 계획 | &quot;MKG Hub라는 작업 영역을 만들고 지역별 프로그램을 추적할 레코드 종류를 설정하십시오.&quot; <br> &quot;채널 및 지역 전반에 걸쳐 MKG 프로그램을 추적하는 데 필요한 레코드 종류 및 관계를 설정하십시오.&quot; |
| 계획 레코드 관리 | 작업 공간 내에서 계획 레코드(캠페인, 브리프) 및 해당 필드 값을 생성하고 업데이트합니다. | `manage-workfront-planning` | Workfront 계획 | &quot;목표, 대상 및 주요 메시지를 사용하여 가을 Brand Launch 캠페인에 대한 간략한 만들기&quot; <br> &quot;예산 및 기본 채널을 사용하여 가을 Brand Launch 간략한 업데이트&quot; |
| 프로젝트 만들기 및 관리 | 프로젝트 회전 및 구성: 템플릿 적용, 우선 순위 및 예산 설정, 작업 순서 지정, 단계 및 종속성 추가, 사람 또는 역할 할당 | `manage-workfront-workflow` | Workfront 워크플로 | &quot;봄 캠페인을 만들고, 2억 달러 예산으로 우선 순위를 설정하고, 작업의 순서를 지정하십시오.&quot; <br> &quot;[프로젝트 템플릿]에서 [프로젝트 이름]&#x200B;(이)라는 Workfront 프로젝트 계획을 만듭니다.&quot; <br> &quot;Fall Launch에 대한 프로젝트 계획을 만듭니다. 개념, 디자인, 복사 및 검토를 위한 작업이 포함된 소셜 캠페인&quot; <br> &quot;새 이메일 마케팅 작업을 추가하고, Rachel Smith에게 할당하십시오.&quot; |
| 검토 및 승인 가속화 | 다단계 승인 설정, 승인 템플릿 적용, 승인자 추가/제거, 미리 알림 보내기 및 벌크 업데이트 | `manage-workfront-workflow` | Workfront 워크플로 | &quot;다단계 승인(복사, 디자인, 법적)을 만들고 승인하지 않은 사람에게 알림&quot; <br> &quot;모든 공개 승인에서 Chris Smith를 제거하고 Jane Francis로 바꾸기&quot; |
| 작업 및 작업 상태 업데이트 | 작업 완료 표시, 완료율 업데이트 및 작업 종료 | `manage-workfront-workflow` | Workfront 워크플로 | &quot;가을 실행에서 내 &#39;주요 아트 제작&#39; 작업을 완료로 표시&quot; <br> &quot;가을 실행 복사 작업을 100%로 닫기&quot; |
| 표면 작업 인사이트 | 프로젝트 전반에 걸쳐 위험 상태의 작업, 미할당 작업, 진행 중 문제 및 상태를 찾기 위해 탐색적 질문 | `query-workfront` | Workfront 워크플로 | &quot;누구에게도 할당되지 않고 이번 주까지 예정된 현재 프로젝트에서 미완료 작업을 찾아보세요.&quot; <br> &quot;현재 프로젝트에서 진행 중인 문제는 몇 개입니까?&quot; |
| 프로젝트 및 작업 요약 | 끌어오기 목록, 테이블 및 프로젝트, 작업, 문제 및 할당 수 | `query-workfront` | Workfront 워크플로 | &quot;프로젝트 이름, 작업 기한 및 할당된 사용자로 시작할 준비가 된 내 작업의 테이블을 표시합니다.&quot; <br> &quot;[사용자 이름]에 할당된 모든 작업 가져오기&quot; |
| 승인 및 포트폴리오 상태 추적 | 승인 상태를 확인하고 포트폴리오별로 미완료 작업을 롤업합니다. | `query-workfront` | Workfront 워크플로 | &quot;내 승인 상태 표시&quot; <br> &quot;[Portfolio 이름] 포트폴리오에 포함된 불완전한 문제가 있는 테이블 표시&quot; |
