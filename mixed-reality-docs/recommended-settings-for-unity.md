---
title: Unity에 대 한 권장된 설정
description: Unity는 프로젝트 설정을 통해 전환할 수 있는 혼합 된 현실에 관련 된 몇 가지 동작을 제공 합니다.
author: Troy-Ferrell
ms.author: trferrel
ms.date: 03/26/2019
ms.topic: article
keywords: unity, 설정, 혼합된 현실
ms.openlocfilehash: a67c3a65819855be6d43941c05f9a0027abf2f6d
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600155"
---
# <a name="recommended-settings-for-unity"></a>Unity에 대 한 권장된 설정

Unity에는 모든 플랫폼에 대 한 평균 사례는 일반적으로 기본 옵션 집합을 제공 합니다. 그러나 Unity 프로젝트 설정을 통해 전환할 수 있는 혼합 된 현실에 관련 된 몇 가지 동작을 제공 합니다.

## <a name="performant-environment-set-up"></a>고성능 환경 설정

### <a name="low-quality-setting"></a>저품질 설정

수정 해야 합니다 **Unity 품질 설정을** 사용자 환경에 대 한 **"가장 빠른"** 합니다. 응용 프로그램에서 적절 한 framerate를 성능 기준에 맞게 실행 중인지 확인 하는 데 도움이 됩니다. 이 Hololens 개발에 대 한 매우 중요 합니다. 몰입 형 헤드셋, VR 환경을 강화 데스크톱의 사양에 따라 개발에 대 한 가장 낮은 품질 매개 변수 없이 framerate 여전히 얻을 수 있습니다. 

Unity 2018 LTS 이상, 프로젝트의 품질 수준 설정할 수 있습니다.

아래 **편집** > **프로젝트 설정** > **품질** > 설정 합니다 **기본** 클릭 하 여는 아래쪽 화살표를 **Fastest** 품질 수준

### <a name="single-pass-instancing-rendering-path"></a>단일 패스 인스턴스 렌더링 경로

혼합 현실 응용 프로그램에서 장면 렌더링 됩니다을 두 번 되 면 사용자에 게 눈 마다. 일반적인 3D 개발에 비해, 효과적으로 두 번이 작업량을 계산 해야 합니다. 따라서 CPU 및 GPU 시간에 모두 저장 하는 Unity에서 가장 효율적인 렌더링 패스를 선택 하는 것이 반드시 합니다. 단일 패스 인스턴스화된 렌더링 혼합 현실 앱에 대 한 Unity 렌더링 파이프라인을 최적화 하 고 따라서 것이 설정을 사용 하려면 모든 프로젝트에 대해 기본적으로 키를 누릅니다. 

Unity 프로젝트에서이 기능을 사용 하도록 설정 하려면
1)  오픈 **플레이어 xr 하이 설정을** (이동 **편집** > **프로젝트 설정** > **Player**  >  **Xr 하이 설정을**)
2) 선택 **단일 전달 인스턴스화된** 에서 합니다 **스테레오 렌더링 메서드** 드롭 다운 메뉴 (**지원 되는 가상 현실** 확인란을 선택 해야 합니다)

자세한 내용은이 렌더링 방법에 대 한 Unity에서 다음 문서를 읽어봅니다.
- [고급 스테레오 렌더링 AR 및 VR 성능을 최대화 하는 방법](https://blogs.unity3d.com/2017/11/21/how-to-maximize-ar-and-vr-performance-with-advanced-stereo-rendering/)
- [단일 패스 인스턴스 만들기](https://docs.unity3d.com/Manual/SinglePassInstancing.html) 

>[!NOTE]
> 개발자가 기존 사용자 지정 셰이더 용으로 작성 되지가 이미 있으면 단일 전달 렌더링 인스턴스화된 다음 한 가지 일반적인 문제가 발생 인스턴스. 개발자는이 기능을 사용 하도록 설정한 후 일부 Gameobject만 렌더링 한 눈에 알 수 있습니다. 사용자 지정 셰이더를 연결된에 대 한 적절 한 속성을 없기 때문에 이것이 인스턴스.
>
> 참조 [단일 전달 스테레오에 대 한 렌더링 HoloLens](https://docs.unity3d.com/Manual/SinglePassStereoRenderingHoloLens.html) 이 문제를 해결 하는 방법에 대 한 Unity에서

### <a name="enable-depth-buffer-sharing"></a>깊이 버퍼 공유 사용

사용자의 인식에서 홀로그램 안정성을 향상 시키려면 것이 좋습니다 사용 하도록 설정 합니다 **깊이 버퍼 공유** Unity의 속성입니다. 이 설정을 켜면, Unity Windows Mixed Reality 플랫폼을 사용 하 여 응용 프로그램에서 생성 된 깊이 맵을 공유 됩니다. 플랫폼 응용 프로그램에서 렌더링 되 고 지정 된 모든 프레임에 대 한 장면에 맞게 홀로그램 안정성을 최적화 하기 위해 됩니다.

Unity 프로젝트에서이 기능을 사용 하도록 설정 하려면
1) 오픈 **플레이어 xr 하이 설정을** (이동 **편집** > **프로젝트 설정** > **Player**  >  **Xr 하이 설정을**)
2) 에 대 한 확인란을 선택 **깊이 버퍼 공유 사용** 아래에서 **가상 현실 Sdk** > **Windows Mixed Reality** 확장 (**가상 실제로 지원** 확인란을 선택 해야 합니다)

또한 선택할 것 **16 비트 수준** 아래 합니다 **깊이 형식** Hololens 개발에 특히이 패널에서 설정 합니다. 적은 양의 데이터를 이동/처리 해야 할 24 비트 비교할 16 비트 선택 대역폭 요구 사항을 크게 줄일 합니다.

>[!NOTE]
> 개발자는 카메라의 가까운/먼 평면 설정과 함께 이러한 값을 변경 하는 경우 Z 싸 우기의 조심 해야 합니다. 두 개의 gameobject (즉, 깊이 버퍼의 충실도의 제한으로 인해 같은 픽셀을 렌더링 하려고 하는 경우 발생 Z 장애 해결 z 깊이) 개체가 다른 앞에 Unity 알 수 없습니다. 개발자는 해당 두 게임 개체 간의 깜박임 기록 됩니다 *막고* 같은 깊이 z 값입니다. 이 큰 카메라에서 z-깊이 대 한 계산 시 각 개체에 대 한 값의 범위를로 24 비트 수준 형식으로 전환 하 여 해결할 수 있습니다.
>
> 그러나 것이 좋습니다, 그리고 특히 hololens 개발, 카메라를 수정 하려면 근처의 훨씬 더 작은 범위 대신 평면 및 16 비트 깊이 유지 하 고 서식을 지정 합니다. Z-깊이 근거리 및 원거리 카메라를 따라 값의 범위에 매핑된 아닌 선형 평면입니다. 선택 하 여 수정할 수 있습니다는 *주 카메라* 장면에 아래 **검사기**, 변경 합니다 **가까운 & 훨씬 클리핑 평면** 값 (즉, 해당 범위를 줄이기 위해 x 값에는 1억 개 나 기타 1000 m에서 등.)

### <a name="building-for-il2cpp"></a>IL2CPP 용 빌드

Unity 스크립팅 백 엔드 및 활용 하는 것이 좋습니다 개발자가.NET에 대 한 지원 사용을 중단 했기 **IL2CPP** 해당 UWP 용 visual studio를 빌드합니다. 이렇게 하면 다양 한 장점, 있지만 용 Unity에서 visual studio 솔루션 빌드 **Il2CPP** 심각 하 게 이전.NET 방법을 보다 속도가 느릴 수 있습니다. 따라서 권장 구성에 대 한 모범 사례를 따르는 **IL2CPP** 개발 반복으로 저장 합니다.

1) 있습니다 미리 작성된 된 파일을 다시 사용 될 때마다 동일한 디렉터리에 프로젝트를 작성 하 여 활용 하 여 증분 빌드
2) 프로젝트에 대 한 맬웨어 방지 소프트웨어 검색을 사용 하지 않도록 설정 및 빌드 폴더
   - 오픈 **바이러스 및 위협 보호** Windows 10 설정 앱에서
   - 선택 **설정 관리** 아래에서 **바이러스 및 위협 방지 설정**
   - 선택 **추가 또는 제거 제외** 아래의 합니다 **제외** 섹션
   - 클릭 **제외 추가** 선택한 폴더에 Unity 프로젝트 코드를 포함 합니다. 빌드 출력
3) 빌드에 대해 SSD를 활용 합니다.

읽어보세요 [IL2CPP에 대 한 빌드 시간 최적화](https://docs.unity3d.com/Manual/IL2CPP-OptimizingBuildTimes.html) 자세한 정보에 대 한 합니다.

## <a name="publishing-properties"></a>게시 속성

### <a name="holographic-splash-screen"></a>Holographic 시작 화면

HoloLens에 mobile 클래스 CPU 및 GPU, 즉, 앱을 로드 하는 데는 약간 더 걸릴 수 있습니다. 앱 로드 되는 동안 사용자만 검정, 표시 및 하므로 이러한 궁금할 것입니다. 로드 하는 동안 해당를 원할 것, holographic 시작 화면을 추가할 수 있습니다.

holographic 시작 화면 설정/해제 합니다.
1) 로 이동 **편집할** > **프로젝트 설정** > **플레이어** 페이지
2) 클릭 합니다 **Windows 스토어** 연 탭의 **시작 이미지** 섹션
3) 아래에서 원하는 이미지를 적용 합니다 **Windows Holographic > Holographic 시작 이미지** 속성입니다.
    - 설정/해제 합니다 **Unity 시작 화면이 표시** 옵션을 사용 하도록 설정 또는 Unity 브랜드 시작 화면을 사용 하지 않도록 설정 됩니다. Unity Pro 라이선스가 없는 경우 시작 화면 브랜드 Unity은 항상 표시 됩니다.
    - 경우는 **Holographic 시작 이미지** 은 적용 항상 표시 되는 Unity 시작 화면이 표시 확인란을 사용 하도록 설정 되어 있는지 여부에 관계 없이 합니다. 만 holographic 시작 화면을 사용자 지정 이미지를 지정 하는 Unity Pro 라이선스를 사용 하 여 개발자에 게 제공 됩니다.

|  Unity 시작 화면을 표시  |  Holographic 시작 이미지  |  동작 |
|----------|----------|----------|
|  켜짐  |  없음  |  5 초 또는 더 오래 걸리는 작업이 앱이 로드 될 때까지 기본 Unity 시작 화면을 표시 합니다. | 
|  켜짐  |  사용자 지정  |  5 초 또는 더 오래 걸리는 작업이 앱이 로드 될 때까지 사용자 지정 시작 화면을 표시 합니다. | 
|  끄기  |  없음  |  앱이 로드 될 때까지 투명 한 검은색 (nothing)를 표시 합니다. | 
|  끄기  |  사용자 지정  |  5 초 또는 더 오래 걸리는 작업이 앱이 로드 될 때까지 사용자 지정 시작 화면을 표시 합니다. | 

읽어보세요 [Unity의 시작 화면 설명서](https://docs.unity3d.com/Manual/class-PlayerSettingsSplashScreen.html) 자세한 정보에 대 한 합니다.

### <a name="tracking-loss"></a>손실 추적

혼합된 현실 헤드셋 표시 생성 되도록 주변 환경에 따라 달라 집니다 [world 잠긴 좌표계](coordinate-systems-in-unity.md)를 그대로 두고 홀로그램을 허용 하는 합니다. 헤드셋 자체 세계에서 찾을 수 없는 경우 헤드셋 되었다고 *추적 손실*합니다. 이러한 경우 좌표 시스템 world 잠긴 공간 단계, 공간 앵커 공간 매핑 등 종속 기능 작동 하지 않습니다.

추적의 손실이 발생 하는 경우 Unity의 기본 동작은 렌더링 홀로그램 중지, 일시 중지 하는 [게임 루프](http://docs.unity3d.com/Manual/ExecutionOrder.html), 표시 알림은 편리 하 게 손실 추적 사용자 게이즈를 따릅니다. 추적의 형태로 사용자 지정 알림을 제공할 수도 있습니다 손실 이미지입니다. 전체 경험에 대 한 추적에 종속 된 앱에 대 한 것으로 충분 Unity 완전히 추적을 다시 얻게 될 때까지이 작업을 처리할 수 있도록 합니다. 개발자는 손실 추적 하는 동안 표시 될 사용자 지정 이미지를 제공할 수 있습니다. 

사용자 지정 하려면 추적 손실된 이미지:
1) 로 이동 **편집할** > **프로젝트 설정** > **플레이어** 페이지
2) 클릭 합니다 **Windows 스토어** 연 탭의 **시작 이미지** 섹션
3) 아래에서 원하는 이미지를 적용 합니다 **Windows Holographic > 추적 손실 이미지** 속성입니다.

#### <a name="opt-out-of-automatic-pause"></a>옵트아웃 자동 일시 중지

일부 앱에는 추적을 사용 해야 합니다. (예: [방향 으로만 이동 가능한 앱](coordinate-systems-in-unity.md) 360도 비디오 뷰어 등) 또는 처리를 추적 하는 동안 중단 없이 손실 됩니다. 계속 해야 할 수 있습니다. 이러한 경우 앱 동작을 추적 하는 기본 손실에서 선택할 수 있습니다. 이 옵션을 선택 하는 개발자는 추적 손실 시나리오에서 제대로 렌더링 되지는 모든 개체 숨기기/해제 하는 일을 담당 합니다. 콘텐츠 본문 잠긴 경우에 렌더링할 수 권장 되는 유일한 콘텐츠는 대부분의 경우에서 주 카메라 중심입니다.

자동 일시 중지 동작을 옵트아웃 합니다 하:
1) 로 이동 **편집할** > **프로젝트 설정** > **플레이어** 페이지
2) 클릭 합니다 **Windows 스토어** 연 탭의 **시작 이미지** 섹션
3) 수정 된 **Windows Holographic >에서 추적 손실 일시 중지 및 이미지 표시** 확인란을 선택 합니다.

#### <a name="tracking-loss-events"></a>손실 이벤트를 추적합니다.

파일을 추적 손실 될 때 사용자 지정 동작을 정의 하려면 전역 처리할 [손실 이벤트 추적](tracking-loss-in-unity.md)합니다.

### <a name="capabilities"></a>기능

특정 기능을 활용 하려면 앱 매니페스트에서 적절 한 기능 선언 해야 합니다. 매니페스트 선언 되므로 모든 후속 프로젝트 내보내기에 포함 된 Unity에서 만들 수 있습니다. 

혼합 현실 응용 프로그램에서 기능을 활성화할 수 있습니다.
1) 로 이동 **편집할** > **프로젝트 설정** > **플레이어** 페이지
2) 클릭 합니다 **Windows 스토어** 탭을 엽니다는 **게시 설정** 섹션을 찾습니다 합니다 **기능** 목록

Holographic 앱에 대 한 자주 사용 되는 Api를 사용 하도록 설정 하는 것에 대 한 해당 기능은 다음과 같습니다.
<br>

|  기능  |  기능을 요구 하는 Api |
|----------|----------|
|  SpatialPerception  |  SurfaceObserver | 
|  웹캠  |  PhotoCapture 및 VideoCapture | 
|  PicturesLibrary / VideosLibrary  |  PhotoCapture 또는 VideoCapture, 각각 (저장할 때 캡처된 콘텐츠) | 
|  마이크  |  VideoCapture (오디오 캡처) 하는 경우, DictationRecognizer, GrammarRecognizer, 및 KeywordRecognizer | 
|  InternetClient  |  DictationRecognizer (및 Unity Profiler 사용) | 

## <a name="see-also"></a>참조
* [Unity 개발 개요](unity-development-overview.md)
* [혼합 현실 용 Understaing 성능](understanding-performance-for-mixed-reality.md)
* [Unity에 대 한 성능 권장 사항](performance-recommendations-for-unity.md)