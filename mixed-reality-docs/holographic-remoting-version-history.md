---
title: Holographic 원격 버전 기록
description: HoloLens 2의 Holographic Remoting에 대 한 버전 기록입니다.
author: NPohl-MSFT
ms.author: nopohl
ms.date: 10/21/2019
ms.topic: article
keywords: HoloLens, 원격 서비스, Holographic 원격 작업
ms.openlocfilehash: 75e7c276560b4efbbdcbf2ea7579ed5ad7aadb4d
ms.sourcegitcommit: 6bc6757b9b273a63f260f1716c944603dfa51151
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73439234"
---
# <a name="holographic-remoting-version-history"></a>Holographic 원격 버전 기록

> [!IMPORTANT]
> 이 지침은 HoloLens 2의 Holographic Remoting에만 적용 됩니다.

## 버전 2.0.14 (2019 년 10 월 26 일)<a name="v2.0.14"></a>
* 새 PerceptionDevice Api에 대 한 지원 (Windows 10 11 월 2019 업데이트).
* SpatialGestureRecognizer에 의해 트리거되는 고정 제스처 이벤트를 방지 하는 문제를 해결 했습니다.
* SpatialSurfaceObserver. SetBoundingVolume를 사용할 때 theading 문제가 해결 되었습니다.

## 버전 2.0.12 이상을 (2019 년 10 월 18 일)<a name="v2.0.12"></a>
* NavigationRail (X/Y/Z)을 사용 하는 경우 SpatialGestureRecognizer의 충돌이 수정 되었습니다.

## 버전 v2.0.10 (2019 년 10 월 10 일)<a name="v2.0.10"></a>
* VR 컨트롤러의 트리거 단추를 사용할 때 충돌이 해결 되었습니다. Holographic Remoting은 컨트롤러를 완전히 지원 하지 않습니다. HoloLens 2와 연결 된 경우에는 트리거 단추와 Windows 단추만 작동 합니다.

## 버전 2.0.9 (2019 년 9 월 19 일)<a name="v2.0.9"></a>
* [SpatialAnchorExporter](https://docs.microsoft.com/uwp/api/windows.perception.spatial.spatialanchorexporter) 에 대 한 지원이 추가 됨
* 다음 멤버를 제공 하는 새 인터페이스 ```IPlayerContext2``` (```PlayerContext```에서 구현 됨)를 추가 했습니다.
  - [BlitRemoteFrameTimeout](holographic-remoting-create-player.md#BlitRemoteFrameTimeout) 속성입니다.
* ```Failed_RemoteFrameTooOld``` 값이에 추가 되었습니다 ```BlitResult```
* 안정성 및 안정성 향상

## 버전 2.0.8 이상이 필요 (2019 년 8 월 20 일)<a name="v2.0.8"></a>

* [IDXGISurface2](https://docs.microsoft.com/windows/win32/api/dxgi1_2/nn-dxgi1_2-idxgisurface2) 를 매개 변수로 사용 하 여 [HolographicCameraRenderingParameters. CommitDirect3D11DepthBuffer](https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.commitdirect3d11depthbuffer) 를 호출할 때 충돌이 해결 되었습니다.
* 안정성 및 안정성 향상

## 버전 2.0.7 (2019 년 7 월 26 일)<a name="v2.0.7"></a>

* HoloLens 2에 대 한 Holographic 원격 작업의 첫 번째 공개 릴리스입니다.

## <a name="see-also"></a>참고 항목
* [사용자 지정 Holographic Remoting 플레이어 앱 작성](holographic-remoting-create-player.md)
* [Holographic 원격 호스트 앱 작성](holographic-remoting-create-host.md)
* [Holographic 원격 문제 해결 및 제한 사항](holographic-remoting-troubleshooting.md)
* [홀로그램 원격 소프트웨어 사용 조건](https://docs.microsoft.com/legal/mixed-reality/microsoft-holographic-remoting-software-license-terms)
* [Microsoft 개인 정보 취급 방침](https://go.microsoft.com/fwlink/?LinkId=521839)