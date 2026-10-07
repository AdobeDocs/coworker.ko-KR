---
title: CX Coworker 게이트웨이의 Experience Platform 도구
description: CX Coworker Gateway를 통해 사용할 수 있는 Adobe Experience Platform 도구에 대해 알아봅니다.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1947'
ht-degree: 6%
---

# Adobe CX Coworker Gateway의 Adobe Experience Platform 도구 {#aep-mcp}

Adobe Experience Platform 제품 도구를 사용하여 MCP 호환 클라이언트에서 스키마, 데이터 세트, 데이터 거버넌스 구성, 쿼리 서비스 리소스 및 감사 이벤트를 검사할 수 있습니다. 이러한 도구는 조직이 활성화되고 사용자 계정에 필요한 Experience Platform 권한이 있는 경우 [Adobe CX Coworker 게이트웨이](overview.md)를 통해 사용할 수 있습니다.

>[!AVAILABILITY]
>
>Experience Platform 제품 도구는 Beta에 있습니다. 액세스는 초대를 통해서만 가능하며 Adobe 조직 활성화가 필요합니다. [CX Coworker 게이트웨이 도구 액세스](access.md)를 참조하십시오.

## 요약

| 도구 | 설명 | 리소스 | 기능 | 상태 |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | 쿼리 서비스 IP 액세스 제한 검색 | 데이터 Distiller 인증 · IP 범위 | list | 활성 |
| `search_audit` | Experience Platform의 사용자 활동 감사 이벤트 나열 | 쿼리 감사 · 이벤트 감사 | 목록, 자산 유형별 필터링, 작업, 상태, 시간 범위 | 활성 |
| `search_datasets` | 쿼리 데이터 세트 및 일괄 처리 수집 메타데이터 | 카탈로그 API · 데이터 세트, 배치 | list, get, filter, list last, list files | 활성 |
| `search_class_relations` | Experience Platform 비즈니스 클래스 관계 검색 | 클래스 관계 · 정적 YAML 인덱스 | 토큰, 다용어, 부분 일치로 검색 | 활성 |
| `search_data_access` | 실패한 수집 배치의 파일 나열 | 데이터 액세스 API · 실패한 일괄 처리 | 실패한 파일 나열 | 활성 |
| `search_data_lake` | 데이터 세트 메타데이터 및 일괄 처리 상태 검사 | Data Lake API · 데이터 세트, 배치 | 가져오기, 크기 가져오기, 실패한 일괄 처리 나열 | 활성 |
| `search_dule` | 쿼리 데이터 거버넌스 레이블, 정책, 작업 | 데이터 거버넌스 · 레이블, 정책, 마케팅 액션 | 목록, 가져오기, 목록 활성화, 평가 | 활성 |
| `search_query_service` | SQL 쿼리, 템플릿, 일정, 경고 쿼리 | 쿼리 서비스 · 쿼리, 템플릿, 일정, 경고 | 목록, 가져오기, 필터링, 연결 매개 변수 가져오기 | 활성 |
| `search_sandbox_health_assessment` | 현재 샌드박스에 대한 최신 실행 및 작업 상태 확인 평가 결과를 검색합니다. | 실행 및 운영 · 상태 점검 평가 | 목록, 확인 이름으로 가져오기 | 활성 |
| `search_schema_registry` | XDM 스키마, 필드 그룹, 클래스, 유형 쿼리 | 스키마 레지스트리 · 스키마, 필드 그룹, 클래스, 데이터 유형, 설명자 | 목록, 가져오기, 컨테이너별 필터링 | 활성 |
| `execute_observability_metrics_query` | 현재 샌드박스 또는 모든 샌드박스에 대해 [!DNL Observability Insights] 지표 쿼리 | 가시성 인사이트 · 지표 | 시계열 및 집계 쿼리, 다중 지표 요청, 태그 필터, groupBy/exclude, 지표별 다운샘플링 | 활성 |
| `inspect_observability_breaches` | 지표가 구성된 기준선을 초과하는 [!DNL Observability Insights] 위반 간격 감지 | 가시성 통찰력 · 위반 | 시리즈, 조직 및 샌드박스 범위별 위반 간격 나열 | 활성 |

## 도구 참조

### search_allowed_ip_ranges

**리소스:** 데이터 Distiller 인증 · IP 범위
**상태:** 활성

현재 샌드박스에서 쿼리 서비스에 대해 구성된 모든 IP 액세스 제한을 검색합니다. 조직 ID와 허용된 IP 범위 목록을 반환합니다. Data Distiller 추가 기능이 있는 고객만 사용할 수 있습니다.

**기능:** 쿼리 서비스에 대해 허용되는 IP 범위를 나열합니다.

매개 변수가 없습니다.

### search_audit

**리소스:** 감사 쿼리 · 감사 이벤트
**상태:** 활성

Experience Platform 서비스 전반에 걸쳐 사용자 활동에 대한 타임스탬프가 지정된 레코드를 나열합니다. 작업 유형, 사용자 이메일, 에셋 정보 및 이벤트 상태를 반환합니다. `asset_type` 및 `action`을(를) 사용하여 결과 범위를 좁히십시오. 시간 범위를 지정하지 않은 경우 기본값은 최근 7일로 설정됩니다. 지난 90일 동안의 마지막 1000개 레코드 및 이벤트로 제한됩니다.

**기능:** 목록 감사 이벤트, 자산 유형, 작업, 상태, 시간 범위, 페이지 번호를 기준으로 필터링

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `action` | 아니오 | 작업 유형별로 필터링합니다. 공통 값(OR의 경우 쉼표로 구분): `Create`, `Delete`, `Update`, `Enable`, `Disable` |
| `asset_type` | 아니오 | 자산 유형별로 필터링합니다. `Dataset`, `Schema`, `Segment`, `Destination`, `Source Data Flow`, `Merge Policy`, `Identity Namespace`, `Identity Graph`, `Sandbox`, `Role`, `Query`, `Scheduled Query`, `Datastream`, `Computed Attribute`, `Field Group`, `Class`, `Data Types`, `Account`, `Product Profile`, `Query Template`, `Work Order`, `Audit Logs`, `Access Control Policy` 중 하나여야 합니다. |
| `status` | 아니오 | 이벤트 상태별로 필터링합니다. 값: `Success`, `Failure`, `Allow`, `Deny`. OR의 경우 쉼표로 구분 |
| `start_time` | 아니오 | 가장 빠른 타임스탬프입니다. ms가 포함된 ISO 8601 UTC, 예: `2024-01-15T00:00:00.000Z` |
| `end_time` | 아니오 | 최신 타임스탬프. ISO 8601 UTC(ms 포함) |
| `property_filter` | 아니오 | 원시 필터 식(예: `action==create`). 위의 전용 매개 변수 선호 |
| `orderby` | 아니오 | 정렬 순서: `timestamp`(asc) 또는 `-timestamp`(desc) |
| `limit` | 아니오 | 최대 결과 수(3~1000, 기본값 50) |
| `start` | 아니오 | 페이지 매김 오프셋입니다. 각 페이지에 대해 제한 값만큼 증가 |
| `query_id` | 아니오 | 동일한 쿼리를 반복하기 위한 이전 응답의 쿼리 ID |

### search_dataset

**리소스:** 카탈로그 API · 데이터 세트, 배치
**상태:** 활성

Experience Platform 카탈로그 서비스를 위한 통합 디스패치 도구. 쿼리 데이터 세트 메타데이터(스키마 참조, 태그, 생성 정보) 또는 배치 수집 레코드(상태, 지표, 파일 목록)입니다. 데이터 집합을 검색하려면 `dataset/list`을(를) 사용하고, 수집 상태를 확인하려면 `batch/list`을(를) 사용하고, 특정 일괄 처리 내용을 검사하려면 `batch/list_files` 또는 `batch/get_meta_files`을(를) 사용합니다. 모든 작업은 읽기 전용입니다.

**기능:** 데이터 세트 나열, 데이터 세트 가져오기, 배치 나열, 데이터 세트당 마지막 배치 나열, 배치 파일 나열, 배치 메타 파일 가져오기(행 오류, 입력 파일)

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `entity_type` | 예 | `dataset` 또는 `batch` |
| `operation` | 예 | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. 유효한 조합: 데이터 세트 → 목록, 가져오기, 5개 모두→ 일괄 처리 |
| `resource_id` | 아니오 | 데이터 세트 또는 배치 ID. `dataset/get`, `batch/get`, `batch/list_files`, `batch/get_meta_files`에 필요 |
| `query_params.limit` | 아니오 | 페이지당 최대 결과 수(최대 100개). 모든 목록 작업에 적용됩니다. |
| `query_params.start` | 아니오 | 페이지 매김 오프셋입니다. 모든 목록 작업에 적용됩니다. |
| `query_params.order_by` | 아니오 | 정렬 방향(예: `asc:created,updated`). 모든 목록 작업에 적용됩니다. |
| `query_params.properties` | 아니오 | 쉼표로 구분된 속성. 데이터 세트/목록, 데이터 세트/get, batch/list, batch/list_last에 적용 |
| `query_params.name` | 아니오 | 이름별로 데이터 세트 필터링(데이터 세트/목록만) |
| `query_params.tags` | 아니오 | 태그로 데이터 세트 필터링(예: `unifiedProfile:enabled:true`) (데이터 세트/목록만) |
| `query_params.property_filter` | 아니오 | 응답 개체(데이터 세트/목록 및 배치/목록)에 대한 정규 표현식 필터 |
| `query_params.status` | 아니오 | 상태별로 일괄 처리 필터링: `success`, `failed`, `loading`, `active`(일괄 처리/목록만) |
| `query_params.dataset_id` | 아니오 | 특정 데이터 세트(batch/list 및 batch/list_last)에 배치 범위 지정 |
| `query_params.created_after` | 아니오 | Unix 타임스탬프 이후 생성된 일괄 처리 필터링(ms)(일괄 처리/목록만 해당) |
| `query_params.created_before` | 아니오 | Unix 타임스탬프 전에 생성된 일괄 처리 필터링(밀리초)(일괄 처리/목록만 해당) |
| `query_params.last_batch_status` | 아니오 | 마지막 배치 상태로 필터링(batch/list_last만) |
| `query_params.aggregate` | 아니오 | 루트 수준에서 집계된 지표 반환(일괄 처리/가져오기 전용) |
| `query_params.path` | 아니오 | 다운로드할 Meta 파일: `row_errors`, `input_files`, `row_errors_sample.json`(batch/get_meta_files만 해당) |

### search_class_relations

**리소스:** 클래스 관계 · 정적 YAML 인덱스
**상태:** 활성

정적 `class_relations_v1.yaml` 인덱스를 사용하여 이름별로 Experience Platform 비즈니스 클래스 관계를 검색합니다. Experience Platform API 호출이 수행되지 않습니다. 하나의 용어나 쉼표로 구분된 용어를 허용합니다. 부분 토큰 일치를 사용하여 각 용어를 클래스 이름에 대해 일치시킵니다. 정방향 관계(각 클래스가 가리키는 대상) 및 역방향 관계(해당 클래스를 다시 가리키는 대상)와 일치하는 클래스를 반환합니다. 쿼리, 데이터 흐름 또는 스키마 구성을 작성하기 전에 엔티티 관계를 이해하려면 이 함수를 사용하십시오.

**기능:** 토큰별 검색, 여러 단어로 이루어진 쉼표로 구분된 검색, 부분 토큰 일치, 양방향 동의어 확장

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `query` | 예 | 검색할 비즈니스 클래스 이름 또는 개체 유형입니다. 부분 토큰 일치(`dat`개가 `dataset`, `data_type`개 등)를 지원합니다. 여러 클래스를 한 번에 검색하려면 쉼표로 구분된 여러 용어를 전달하십시오(예: `dataset, schema`). |
| `n` | 아니오 | 반환할 일치하는 최대 결과 수(기본값 5, 최소 1) |

### search_data_access

**리소스:** 데이터 액세스 API · 실패한 일괄 처리
**상태:** 활성

실패한 Experience Platform 데이터 수집 배치에서 파일에 액세스합니다. `failed_batch/list_failed`을(를) 사용하여 실패 진단을 위해 실패한 일괄 처리에 속하는 파일을 나열합니다. 모든 작업에 일괄 처리 ID가 필요합니다. 참고: `file/get` 및 `dataset/preview`은(는) 실제 레코드 데이터를 노출하므로 비활성화됩니다. 모든 작업은 읽기 전용입니다.

**기능:** 실패한 수집 배치의 파일을 나열합니다.

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `entity_type` | 예 | `failed_batch` — 실패한 수집 배치의 파일 나열 |
| `operation` | 예 | `list_failed` — 유일하게 지원되는 작업 |
| `resource_id` | 예 | 실패한 일괄 처리의 일괄 처리 ID |
| `query_params.start` | 아니오 | 페이징 시작 인덱스(예: `1`) |
| `query_params.limit` | 아니오 | 페이지당 결과 수(예: `10`) |
| `query_params.path` | 아니오 | 전체 파일 이름 필터(예: `profiles.csv`) |


### search_data_lake

**리소스:** Data Lake API · 데이터 세트, 배치
**상태:** 활성

데이터 레이크 레이어에서 데이터 세트 및 배치 메타데이터를 검사합니다. 전체 메타데이터에 `get`, 저장소 및 수집 크기 지표에 `get_size`, 기간 내에 수집 실패를 모니터링하려면 `list_failed`을(를) 사용합니다. `list_failed`에 대한 시간 범위가 제공되지 않은 경우 기본값은 지난 7일로 설정됩니다. 모든 작업은 읽기 전용이며 리소스 ID가 필요합니다.

**기능:** 데이터 세트/일괄 처리 메타데이터 가져오기, 저장소 크기 지표 가져오기, 실패한 일괄 처리 나열 시간 내

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `entity_type` | 예 | `dataset` 또는 `batch` |
| `operation` | 예 | `get`, `get_size`, `list_failed`. `list_failed`은(는) `batch` 엔터티 형식만 지원합니다. |
| `resource_id` | 예 | 데이터 세트 ID 또는 배치 ID. `list_failed`의 경우: 데이터 세트 ID에서 범위 오류 |
| `query_params.created_after` | 아니오 | 기간 시작. Unix 타임스탬프(밀리초) |
| `query_params.created_before` | 아니오 | 기간 종료. Unix 타임스탬프(밀리초) |
| `query_params.limit` | 아니오 | 페이지당 최대 결과 수(최대 100개) |
| `query_params.order_by` | 아니오 | 정렬 방향(예: `desc:created`) |

### search_dule

**리소스:** 데이터 거버넌스 · 레이블, 정책, 마케팅 액션
**상태:** 활성

데이터 사용 레이블, 정책 및 마케팅 작업에 대해 Policy Service API 를 쿼리합니다. 특정 레이블이 있는 데이터에 대한 마케팅 작업이 거버넌스 정책을 위반하는지 여부를 테스트하려면 `marketing_action/evaluate`을(를) 사용합니다. 모든 작업은 읽기 전용입니다.

**기능:** 목록/데이터 사용 레이블 가져오기, 목록/정책 가져오기, 목록 사용 정책, 목록/마케팅 작업 가져오기, 레이블에 대한 마케팅 작업 평가

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `entity_type` | 예 | `label`, `policy` 또는 `marketing_action` |
| `operation` | 예 | `list`, `get`, `list_enabled`(정책만), `evaluate`(marketing_action만). `list_enabled`에는 범위가 필요하지 않습니다. |
| `scope` | 아니오 | `core`(Adobe 정의) 또는 `custom`(org 정의). `list`, `get`, `evaluate`에 필요; `list_enabled`에 사용되지 않음 |
| `resource_id` | 아니오 | 레이블 이름, 정책 ID 또는 마케팅 작업 이름입니다. `get` 및 `evaluate`에 필요 |
| `query_params.dule_labels` | 아니오 | 쉼표로 구분된 레이블(예: `C1,C3`). `marketing_action/evaluate`에 필요; `policy/list`에 대한 선택적 필터 |
| `query_params.limit` | 아니오 | 최대 결과 |
| `query_params.start` | 아니오 | 이전 응답의 `_page.next` 값에서 페이지 매김 커서 |
| `query_params.orderby` | 아니오 | 쉼표로 구분된 정렬 필드 |
| `query_params.property_filter` | 아니오 | 필터 식(예: `name==C1`) |
| `query_params.marketing_action` | 아니오 | 이 마케팅 액션을 참조하는 정책으로 정책 목록 제한(정책/목록만) |
| `query_params.include_draft` | 아니오 | `marketing_action/evaluate`에 초안 정책 포함(기본값: ENABLED 정책만) |

### search_query_service

**리소스:** 쿼리 서비스 · 쿼리, 템플릿, 일정, 일정 실행, 연결, 경고 구독
**상태:** 활성

쿼리 서비스 리소스를 위한 통합 도구입니다. 임시 쿼리, 저장된 SQL 템플릿, 예약된 쿼리 및 실행, 대화형 연결 매개 변수(psql/JDBC 클라이언트의 경우) 및 경고 구독을 나열하고 검색합니다. 쿼리 목록의 경우 내부 트래픽을 필터링하려면 기본적으로 `isService==false,isParentLevel==true`입니다. 모든 작업은 읽기 전용입니다.

**기능:** 목록/가져오기 쿼리, 목록/가져오기 템플릿, 목록/가져오기 일정, 목록/가져오기 일정 실행, 연결 매개 변수 가져오기, 경고 구독 나열

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `entity_type` | 예 | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | 예 | `list`, `get`, `get_connection_params`, `list_by_u...` |

### execute_observability_metrics_query

**리소스:** Observability Insights · 지표
**상태:** 활성

현재 샌드박스 또는 조직의 모든 샌드박스에 대해 [!DNL Observability Insights] 지표를 쿼리합니다. 단일 요청, 태그 기반 필터 및 지표별 다운샘플링에서 여러 지표를 지원합니다. `scope=org`의 경우 모든 지표에 하나 이상의 `groupBy` 필터를 포함하십시오. 모든 작업은 읽기 전용입니다.

**기능:** 쿼리 지표 데이터 포인트, 시계열 또는 집계, 다중 지표 요청, 태그 필터, groupBy/exclude, 지표별 다운샘플링

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `metrics` | 예 | 지표 사양의 배열입니다. 각각 `name`(정규화된 지표 이름), `aggregator`(`sum`, `avg`, `min`, `max`, `count`, `last`, `p50`, `p95`, `p99`, 히스토그램 변형 또는 `absent`), 선택적 `filters` 및 선택적 `downsample`을(를) 포함합니다. |
| `start` | 예 | 창 시작, ISO 8601(예: `2026-01-15T00:00:00.000Z`). `end`보다 이전이어야 합니다. 최대 기간: 31일 |
| `end` | 예 | 창 끝, ISO 8601. `start`보다 이후여야 합니다. |
| `granularity` | 아니오 | 시간 버킷 크기: `MINUTE`, `FIVE_MINUTE`, `TEN_MINUTE`, `FIFTEEN_MINUTE`, `THIRTY_MINUTE`, `HOUR`, `FOUR_HOUR`, `TWELVE_HOUR`, `DAY`, `TWO_DAY`, `WEEK`, `MONTH` 또는 `ALL`(창을 단일 집계로 축소). 을 생략하여 서버가 선택하도록 합니다. |
| `scope` | 아니오 | `sandbox`(기본값) 현재 샌드박스를 쿼리합니다. `org`에서 조직의 모든 샌드박스를 쿼리하고 모든 지표에 대해 `groupBy` 필터를 권장합니다. |

`metrics[].filters`의 각 필터에는 `name`(태그 이름), `value`(완전 일치, 와일드카드 또는 정규 표현식 일치) 및 선택적 `groupBy` 및 `exclude` 부울이 포함됩니다.

### inspect_observability_breaches

**리소스:** 가시성 인사이트 · 위반
**상태:** 활성

현재 샌드박스 또는 조직의 모든 샌드박스에 대해 지표가 구성된 기준선을 초과하는 시간 범위인 [!DNL Observability Insights] 위반 간격을 감지합니다. 계열당 미리 일치된 간격을 반환합니다. 창 끝에 아직 진행 중인 끝이 열린 위반이 `end: null`과(와) 함께 반환됩니다. 모든 작업은 읽기 전용입니다.

**기능:** 계열, 조직 및 샌드박스 범위별 위반 간격 나열

**매개 변수:**

| 매개 변수 | 필수 | 설명 |
| --- | --- | --- |
| `metrics` | 예 | 위반 사양 배열. 여기에는 `name`(정규화된 지표 이름)과 선택적 `filters`이(가) 포함됩니다. |
| `start` | 예 | 창 시작, ISO 8601. `end`보다 이전이어야 합니다. 최대 기간: 31일 |
| `end` | 예 | 창 끝, ISO 8601 |
| `granularity` | 아니오 | 시간 버킷 크기입니다. `ALL`을(를) 제외하고 `execute_observability_metrics_query`과(와) 동일한 값입니다. 각 버킷은 기준선에 대해 독립적으로 평가됩니다 |
| `scope` | 아니오 | `sandbox`(기본값) 또는 `org`. 샌드박스 필터가 없는 `org`에서 지표당 `groupBy: true`이(가) 있는 필터를 하나 이상 포함하면 조직 전체에 걸쳐 축소되는 대신 해당 차원으로 결과가 분할됩니다 |

`inspect_observability_breaches`이(가) `metrics[]`의 `aggregator` 또는 `downsample`을(를) 허용하지 않습니다. 도구는 위반 상태를 평가하기 위해 내부적으로 설정합니다.

>[!NOTE]
>
>두 가시성 통찰력 도구 모두 요청당 예상 10,000개의 데이터 포인트로 제한됩니다. 이 제한을 초과하여 요청이 거부되면 시간 범위를 좁히거나 필터를 추가하거나 `granularity`을(를) 사용합니다.

### search_sandbox_health_assessment

**리소스:** 실행 및 운영 · 상태 검사 평가
**상태:** 활성

현재 샌드박스에 대한 최신 실행 및 작업 상태 검사 평가 결과를 검색합니다. 스키마 및 ID, 세분화, 수집 및 프로필을 포함하여 지원되는 모든 카테고리에 대한 결과를 반환합니다. 별도의 조회 없이 근본 원인을 식별하기 위해 각 결과에는 실패한 검사 뒤에 영향을 받는 자산이 포함됩니다. 사람이 읽을 수 있는 게시된 이름이 있는 검사만 반환됩니다. 모든 작업은 읽기 전용입니다.

>[!NOTE]
>
>이 도구는 평가 결과만 검색합니다. 플래그가 지정된 문제를 수정하려면 [!DNL Experience Platform] UI의 상태 검사 세부 정보 패널을 사용하십시오. [상태 확인](https://experienceleague.adobe.com/en/docs/experience-platform/run-and-operate/health-checks)을 참조하세요. 지원되는 상태 검사에 대한 자동 수정 지침은 [CX Coworker 채팅](../chat/overview.md)에서 기술로 사용할 수 있습니다.

**기능:** 현재 샌드박스에 대한 모든 상태 검사 결과를 나열하고 명명된 검사 결과를 가져옵니다.

매개 변수가 없습니다.
