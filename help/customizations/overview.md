---
title: Adobe CX Enterprise Coworker 사용자 지정 개요
description: 스킬, 통합, 플러그인 및 메모리를 포함한 Adobe CX Enterprise Coworker의 사용자 정의와 사용자가 경험을 어떻게 확장 및 개인화하는지 알아봅니다.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2d4922c334bcc2ec93dec46098a9c021623034ad
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 28%
---
# 동료 사용자 지정 개요 {#overview}

맞춤화를 통해 팀 작업 방식에 맞게 동료를 확장하고 개인화할 수 있습니다. 스킬을 사용하여 반복 가능한 워크플로를 표준화하고, 통합 기능을 사용하여 Coworker를 다른 시스템에 연결하고, 플러그인을 사용하여 관련 기능을 설치 가능한 패키지에 번들로 제공하고, 메모리를 사용하여 대화 간에 기본 설정과 작업 스타일을 전달합니다.

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/skills/what-are-skills
  {title = What are skills?}
  {description = Learn about skills in Adobe CX Coworker, reusable playbooks that standardize workflows and deliver consistent results across conversations and users.}
  {cta = Watch}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/integrations/understanding-integrations-in-coworker
  {title = What are integrations?}
  {description = Get a quick tour and overview of integrations in Coworker, including what an integration is, why you'd use one, and how to use the interface.}
  {cta = Watch}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/plugins/what-are-plugins
  {title = What are plugins?}
  {description = Learn about Adobe CX Coworker plugins, installable packages that bundle skills and MCP servers to extend functionality for a specific business need.}
  {cta = Watch}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/memory/what-is-memory
  {title = What is memory?}
  {description = Learn how Coworker CX Memory helps personalize AI interactions by remembering preferences, work styles, and reporting defaults across conversations.}
  {cta = Watch}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="What are skills?">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/skills/what-are-skills" title="기술이란?" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3502322/?format=jpeg&nocache=1790273741021" alt="기술이란?"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/skills/what-are-skills" target="_blank" rel="referrer" title="기술이란?">스킬이란?</a>
                    </p>
                    <p class="is-size-6">워크플로우를 표준화하고 대화 및 사용자 간에 일관된 결과를 제공하는 재사용 가능한 플레이북인 Adobe CX Coworker의 기술에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/skills/what-are-skills" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="What are integrations?">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/integrations/understanding-integrations-in-coworker" title="통합이란 무엇입니까?" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3503744/?format=jpeg&nocache=1790273741207" alt="통합이란 무엇입니까?"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/integrations/understanding-integrations-in-coworker" target="_blank" rel="referrer" title="통합이란 무엇입니까?">통합이란?</a>
                    </p>
                    <p class="is-size-6">통합이 무엇인지, 통합을 사용해야 하는 이유, 인터페이스 사용 방법을 포함하여 Coworker의 통합에 대한 간략한 둘러보기 및 개요를 확인하십시오.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/integrations/understanding-integrations-in-coworker" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="What are plugins?">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/plugins/what-are-plugins" title="플러그인이란 무엇입니까?" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3503656/?format=jpeg&nocache=1790273741022" alt="플러그인이란 무엇입니까?"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/plugins/what-are-plugins" target="_blank" rel="referrer" title="플러그인이란 무엇입니까?">플러그인이란?</a>
                    </p>
                    <p class="is-size-6">특정 비즈니스 요구 사항에 맞게 기능을 확장하기 위해 기술과 MCP 서버를 번들로 제공하는 Adobe CX Coworker 플러그인, 설치 가능한 패키지에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/plugins/what-are-plugins" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="What is memory?">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/memory/what-is-memory" title="메모리란 무엇입니까?" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3503657/?format=jpeg&nocache=1790273741019" alt="메모리란 무엇입니까?"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/memory/what-is-memory" target="_blank" rel="referrer" title="메모리란 무엇입니까?">메모리란 무엇입니까?</a>
                    </p>
                    <p class="is-size-6">Coworker CX Memory를 통해 대화 전반에 걸쳐 환경 설정, 작업 스타일 및 보고 기본값을 기억하여 AI 상호 작용을 개인화하는 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/customizations/memory/what-is-memory" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
