---
layout: LandingPage
title: 도구 및 아키텍처 알아보기
description: HoloLens 및 몰입형 헤드셋에 대한 혼합 현실 개발자 설명서입니다.
author: grbury
ms.author: grbury
ms.date: 04/27/2020
ms.topic: overview
ms.localizationpriority: high
keywords: Mixed Reality, 개발, 개발, HoloLens, unity, unreal, directx
ms.openlocfilehash: 97a6e130af45a9444ead5e6ed40168351c4dbbf6
ms.sourcegitcommit: ba4c8c2a19bd6a9a181b2cec3cb8e0402f8cac62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82835292"
---
# <a name="learn-the-tools-and-architecture"></a>도구 및 아키텍처 알아보기

![추상 3D 구체](images/07_Development.png)

## <a name="expand-your-design-process"></a>[디자인 프로세스 확장](case-study-expanding-the-design-process-for-mixed-reality.md)

2016년 Microsoft에서 열정적인 개발자를 대상으로 하는 HoloLens를 시작함에 따라 팀에서 이미 Microsoft 내외부의 스튜디오와 제휴하여 디바이스의 시작 환경을 구축했습니다. 이러한 팀은 혼합 현실 디자인의 새로운 분야에서 기회와 과제를 모두 수행하고 찾아냄으로써 학습했습니다. [자세한 정보](case-study-expanding-the-design-process-for-mixed-reality.md)


<br>

---


## <a name="what-technology-path-are-you-interested-in"></a>관심이 있는 기술 경로는 무엇인가요? 


:::row:::   
    :::column:::    
       [![Unity](images/unity_logo.png)](development.md#unity)<br>
        **[Unity](development.md#unity)**<br>   
        Unity를 사용하여 플랫폼 간 전체 기능을 갖춘 혼합 현실 앱을 빌드하세요.
    :::column-end:::    
    :::column:::    
        [![Unreal](images/Unreal_logo.png)](development.md#unreal)<br>
        **[Unreal](development.md#unreal)**<br> 
        Unreal Engine의 프로덕션 준비 지원으로 멋진 혼합 현실 환경을 만듭니다. 
    :::column-end:::
    :::column:::    
        [![JavaScript](images/web-logo.png)](development.md#javascript)<br>
        **[JavaScript](development.md#javascript)**<br>
        JavaScript 및 WebXR Device API는 모든 플랫폼의 브라우저에서 혼합 현실 경험을 가능하게 하는 개방형 사양입니다.    
    :::column-end:::        
    :::column:::    
        [![네이티브](images/VisualStudio-small_logo.png)](development.md#native)<br>
        **[네이티브](development.md#native)**<br> 
        Windows Mixed Reality API로 직접 코딩하여 혼합 현실 앱을 만들 수 있습니다. 
    :::column-end:::    
:::row-end:::

<br>

---

## <a name="unity"></a>Unity


### <a name="unity-development-overview"></a>[Unity 개발 개요](unity-development-overview.md)
시간을 내어 Unity 자습서를 살펴보는 것이 좋습니다. 자산이 필요한 경우 Unity에는 포괄적인 자산 저장소가 있습니다. 

<br>

### <a name="microsofts-mixed-reality-toolkit-mrtk-for-unity"></a>[Microsoft의 Unity용 MRTK(Mixed Reality Toolkit)](mrtk-getting-started.md)
Unity가 포함된 MRTK v2는 혼합 현실 애플리케이션용 오픈 소스 플랫폼 간 개발 키트입니다. MRTK 버전 2는 Microsoft HoloLens, Windows Mixed Reality 몰입형(VR) 헤드셋 및 OpenVR 플랫폼을 대상으로 하는 애플리케이션의 개발을 가속화하기 위한 것입니다.

<br>

### <a name="open-source-sample-apps-and-step-by-step-tutorials"></a>[오픈 소스 샘플 앱 및 단계별 자습서](tutorials.md)
HoloLens 2 자습서는 개발자가 혼합 현실 애플리케이션을 개발하기 위한 기술과 모범 사례를 모두 익힐 수 있도록 설계되었습니다. 이 자습서는 MRTK 2.0(Mixed Reality Toolkit 2.0)을 기반으로 합니다.

<br>

### <a name="hand-interaction-examples-scene-mrtk-for-unity"></a>[Unity의 손 상호 작용 예시 장면(MRTK)](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/GettingStartedWithTheMRTK.html#open-and-run-the-handinteractionexamples-scene-in-editor)
HandInteractionExamples.unity 예시 장면에는 연결식 손 입력에 중점을 둔 다양한 유형의 상호 작용 및 UI 컨트롤이 있습니다.
>[!NOTE]
>MRTK Foundation 및 Example Unity 패키지를 설치해야 합니다.

### <a name="eye-tracking-examples-mrtk-for-unity"></a>[Unity의 시선 추적 예시(MRTK)](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/EyeTracking/EyeTracking_ExamplesOverview.html)
이 페이지에서는 제공된 MRTK 시선 추적 예제를 기반으로 MRTK에서 시선 추적을 빠르게 사용하기 시작하는 방법을 설명합니다.
>[!NOTE]
>MRTK Foundation 및 Example Unity 패키지를 설치해야 합니다.

<br>

---

## <a name="unreal"></a>Unreal

### <a name="unreal-development-overview"></a>[Unreal 개발 개요](unreal-development-overview.md)
Unreal을 사용하여 혼합 현실 앱을 빌드하는 방법을 알아봅니다.

<br>

### <a name="microsofts-mixed-reality-toolkit-mrtk-for-unreal"></a>[Microsoft의 Unreal용 MRTK(Mixed Reality Toolkit)](https://github.com/microsoft/MixedRealityToolkit-Unreal)
MRTK-Unreal(Unreal용 Mixed Reality Toolkit)은 플러그인, 샘플 및 설명서의 형태로 구성된 구성 요소 세트로, Unreal Engine을 사용하여 혼합 현실 애플리케이션의 개발을 가속화하도록 설계되었습니다.

<br>

### <a name="open-source-sample-apps-and-a-step-by-step-tutorial"></a>[오픈 소스 샘플 앱 및 단계별 자습서](unreal-uxt-ch1.md)
Unreal에서 혼합 현실 개발을 시작하기 위한 자습서는 [UX Tools for Unreal v0.8](https://github.com/microsoft/MixedReality-UXTools-Unreal)을 사용하여 HoloLens 2 앱을 생성하는 엔드투엔드 프로세스를 통해 개발자를 안내합니다.

<br>

---

## <a name="javascript"></a>JavaScript   

### <a name="javascript-development-overview"></a>[JavaScript 개발 개요](javascript-development-overview.md)   
모든 플랫폼에서 JavaScript를 사용하여 혼합 현실 앱을 빌드하는 방법을 알아봅니다.

<br>

---

## <a name="native"></a>네이티브


### <a name="native-development-overview"></a>[네이티브 개발 개요](directx-development-overview.md)
네이티브 혼합 현실 앱을 빌드하는 가장 빠른 길입니다.

<br>

### <a name="directx-uwp-app-templates-for-mixed-reality"></a>[혼합 현실용 DirectX UWP 앱 템플릿](https://marketplace.visualstudio.com/items?itemName=WindowsMixedRealityteam.WindowsMixedRealityAppTemplatesVSIX)
DirectX를 사용하여 혼합 현실 앱을 작성하는 데 필요한 모든 필수 정보를 포함합니다.

<br>

---


## <a name="what-would-you-like-to-do-next"></a>다음에 수행할 작업은 무엇인가요?


:::row:::
    :::column:::
       [![기본 사항 이해](images/icon-lightbulb.png)](index.md#understand-the-basics)<br>
        **[기본 사항 이해](index.md#understand-the-basics)**<br>
        혼합 현실을 정의하는 것이 무엇이며, 혼합 현실이 어떻게 사용되는지에 대해 더 잘 이해합니다.
    :::column-end:::
    :::column:::
        [![개발자 되기](images/icon-design.jpg)](design.md)<br>
         **[개발자 되기](design.md)**<br>
        디자인 및 프로토타입 생성을 시작하는 데 필요한 기본 개념을 알아봅니다.
    :::column-end:::
    :::column:::
        [![도구 설치](images/icon-developer.jpg)](install-the-tools.md)<br>
         **[도구 설치](install-the-tools.md)**<br>
        설치 체크리스트를 사용하여 HoloLens와 혼합 현실용 앱을 빌드하는 데 필요한 도구를 구합니다.
    :::column-end:::
    :::column:::
        [![이벤트 참가](images/icon-calendar.jpg)](sf-academy-events.md)<br>
         **[이벤트 참가](sf-academy-events.md)**<br>
        하드웨어를 살펴보고 첫 번째 HoloLens 2 애플리케이션을 만들기 위한 실습 자습서를 받으세요.
    :::column-end:::
:::row-end:::


<br>

<br>
