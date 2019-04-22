---
title: 공간 매핑 디자인
description: HoloLens 내 공간 매핑의 효과적으로 사용 다양 한 요인의 신중 하 게 고려해 야 합니다.
author: cre8ivepark
ms.author: dongpark
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality를 디자인, 공간 매핑, HoloLens, surface 재구성, 메시
ms.openlocfilehash: d2ddcbf9458769a60cd3ed2871c5f3405c75f10c
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59597885"
---
# <a name="spatial-mapping-design"></a>공간 매핑 디자인

HoloLens 내 공간 매핑의 효과적으로 사용 다양 한 요인의 신중 하 게 고려해 야 합니다.

## <a name="device-support"></a>장치 지원

<table>
<tr>
<th>기능</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens</a></th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">몰입 형 헤드셋</a></th>
</tr><tr>
<td> 공간 매핑</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"></td>
</tr>
</table>

## <a name="why-is-spatial-mapping-important"></a>공간 매핑 중요 한 이유는 무엇입니까?

공간 매핑 실제 화면에서 개체를 배치할 수 있습니다. 이 사용자의 환경에서 앵커 개체를 사용 하면 실제 깊이 신호를 활용 합니다. 다른 홀로그램 및 실제 개체에 기반 하 여 홀로그램 occluding 이러한 홀로그램 자신의 공간에서 실제로 사용자를 유도 하는 데 도움이 됩니다. 홀로그램 공간에서 부동 또는 사용자를 사용 하 여 이동 생각 하지는 실시간으로 합니다. 가능한 경우 위치 편안 함에 대 한 항목입니다.

배치 하거나 홀로그램 (간단한 투영 된 모눈 사용)를 이동할 때 화면을 시각화 합니다. 이 인해 해당 홀로그램을 배치할 최상의 수 고를 홀로그램을 배치 하려는 위치 아직 매핑된 하지 않은 경우 사용자를 표시 하면을 도움이 됩니다. 있습니다 수 "빌보드 항목" 원통이 사용자는 종료 각도의 너무 많은 경우.

## <a name="what-influences-spatial-mapping-quality"></a>공간 매핑 품질을 영향을 줍니다 무엇입니까?

최상의 사용자 환경을 제공 하기 위해 HoloLens에서 수집 된 공간 매핑 데이터의 품질에 영향을 주는 요인을 이해 하는 것이 반드시 합니다.

공간 매핑 데이터의 오류는 세 가지 범주 중 하나에 속합니다.
* **구멍**: 실제 화면 공간 매핑 데이터에서 누락 되었습니다.
* **Hallucinations**: 화면 실제로 존재 하지 않는 공간 매핑 데이터에 존재 합니다.
* **바이어스**: 화면 공간 매핑 데이터에 거 나 끌어오면 실제 표면의 빨라질 맞춥니다.

여러 가지 요인 빈도 이러한 오류의 심각도 영향을 줄 수 있습니다.:

* **사용자 동작**
   * 사용자가 환경을 통해 이동 하는 방법을 환경 검색 수는 얼마나 잘 결정 적절 한 검색을 위해서는 사용자가 지침 필요할 수 있습니다.
   * 검색에 사용 되는 카메라 카메라에서 3.1 미터 거리의 최대 0.8 미터의 최소값에서은 70 수준의 원뿔 내에서 데이터를 제공 합니다. 이 필드의 보기 내에서 실제 화면만 검색 됩니다. 이러한 값은 이후 버전에서 변경 될 수 있습니다 하는 참고 합니다.
   * 사용자 개체의 3.1 미터 내 되지가 다음이 검색 되지 않습니다.
   * 사용자만 미만 0.8 미터 거리에서 개체를 볼 경우 검색 되지 것입니다 (이렇게 하면 사용자의 손에 검색).
   * 표시 되 면 사용자 되지 상향 합니다 (매우 일반적인) 다음 최대값 가능성이 검색 되지 않습니다.
   * 사용자는 되지 가구 또는 벽 뒤에 표시 되는 경우 이들에 의해 폐색 개체는 검색 되지 않습니다.
   * 화면 할애 것이 아니라 단순 각도에서 볼 때 더 높은 품질로 때 검색 해야 하는 경향이 있습니다.
   * HoloLens 헤드 추적 시스템 (있습니다 발생 신속 하 게 사용자 동작, 잘못 된 조명, 특징 없는 벽 또는 카메라 인해 되기 포함 됨)는 일시적으로 실패 하는 경우 공간 매핑 데이터에서 오류가 발생할 수 있습니다. 이러한 오류 사용자 계속 이동 하 고 자신의 환경 검색 시간이 지남에 따라 수정 될 예정입니다.

* **Surface 자료**
   * 실제 화면에 자료를 매우 다양 합니다. 이러한 영향 품질 공간 매핑 데이터 적외선 하는 방법에 영향을 미치므로 반영 됩니다.
   * 어두운 화면에는 작은 빛을 반영 하므로 해당 카메라에 나올 때까지 검색할 수 없습니다.
   * 일부 화면은 초래 화면의 및 경우에 따라 위치 구멍 오류도 화면 뒤 되므로 어떤 거리에서 검색할 너무 적은 빛을 반사 하는 이러한 어두운 될 수 있습니다.
   * 할애를 볼 때 및 단순 각도에서 볼 때가 아니라 특히 표면이 검색만 될 수 있습니다.
   * 미러, 실제 공간 및 표면의 illusory 반사를 만들기 때문에 발생할 수 있습니다 구멍 오류 및 hallucination 오류.

* **장면 동작**
   * 공간 매핑 사용자 이동 또는 열고 닫는 문 같은 환경의 변경 사항에 신속 하 게 대응 합니다.
   * 그러나 공간 매핑 수만 변경 내용에 맞게 영역에서 해당 영역 검색에 사용 되는 카메라를 명확 하 게 표시 되는 경우.
   * 이 인해이 적응 실제로 허점이 나 hallucination 오류가 발생할 수 있는 보다 뒤쳐질 수 됩니다.
   * 예를 들어 사용자 친구를 검색 하 고 회전 친구 여지가 있지만. Friend (hallucination 오류) 'ghost' 표현을 사용자 다시 회전 하 고 공간 친구를 준비 하는 위치를 다시 검색 될 때까지 공간 매핑 데이터에 유지 됩니다.

* **조명 간섭**
   * 장면에서 앰비언트 적외선 검색, 예를 들어: 창을 통해 제공 되는 강력한 햇빛 방해할 수 있습니다.
   * 특히 표면이 검사 주변 표면의 그 원인이 편차 오류를 반사 조명이 방해할 수 있습니다.
   * 표면이 광원을 직접 다시 카메라에 반영 부동 중간 air hallucinations 시켜 또는 적응 장면 및 움직임을 지연 시켜 주변의 공간을 방해할 수 있습니다.
   * 동일한 대화방에 두 개의 HoloLens 장치, 서로 방해 하지 않아야 하지만 있으면 5 개가 넘는 HoloLens 장치 간섭을 일으킬 수 있습니다.

방지 하거나 이러한 오류 중 일부에 대해 수정할 수 있습니다. 그러나 사용자가 오류 공간 매핑 데이터의 경우에 해당 목표를 달성할 수 있도록 응용 프로그램을 디자인 해야 합니다.

## <a name="the-environment-scanning-experience"></a>환경을 검색 환경

HoloLens는 사용자가 해당 하는 대로 해당 환경에서 화면에 대 한 알아냅니다. 시간이 지남에 따라는 HoloLens 검사를 관찰 한 환경의 모든 부분 중 생성 됩니다. 또한 환경에서 변경 내용이 관찰 된 대로 검색을 업데이트 합니다. 이 검색 앱 시작 수 간에 자동으로 유지 됩니다.

공간 매핑을 사용 하는 각 응용 프로그램 환경을 제공 하는 ' 검사 '; 좋습니다. 프로세스는 응용 프로그램 검색 올바르게 작동 하려면 응용 프로그램에 필요한 화면에 사용자를 안내 합니다.

![검색의 예](images/sr-mixedworld-140429-8pm-00068-1000px.png)<br>
*검색의 예*

이 검색 환경의 특성은 각 응용 프로그램의 요구에 따라 크게 달라질 수 있습니다 하지만 두 가지 기본 원칙 디자인 가이드는 합니다.

먼저 **사용자와의 통신 주요 사안은 명확한**합니다. 사용자 응용 프로그램의 요구 사항이 충족 되는지 여부를 인식 해야 합니다. 충족 되지 않는 중인 경우 것이 적절 한 조치를 신속 하 게 진행 해야 이유와 사용자에 게 즉시 명확 해야 합니다.

둘째로 **응용 프로그램은 효율성과 안정성 간의 균형을 시도해 야**합니다. 이렇게 하려면 가능한 경우 **안정적으로**, 응용 프로그램 사용자 시간 절약을 위해 공간 매핑 데이터를 자동으로 분석 해야 합니다. 안정적으로 이렇게 할 수 없는 경우 응용 프로그램 신속 하 게 필요한 추가 정보를 사용 하 여 응용 프로그램을 제공 하도록 사용자를 대신 사용 해야 합니다.

디자인 환경을 검색 오른쪽을 위해을 응용 프로그램에 적용할 수 있는 다음 가능성을 고려 합니다.

* **사용해 본 경험은 없어도 검사**
   * 응용 프로그램 모든 단계별된 검색 환경이; 없이 완벽 하 게 작동할 수 있습니다. 이 자연 스러운 사용자 이동 하는 과정에서 관찰 되는 화면에 알아봅니다.
   * 예를 들어 사용자가 holographic spraypaint 사용 하 여 화면에 그릴 수 있는 응용 프로그램 사용자에 게 현재 표시 화면만 지식이 필요 합니다.
   * 환경을 검색 될 수 있습니다 완전히 이미 사용자는 HoloLens를 사용 하 여 시간이 많이 소요 이미가 하나인 경우.
   * 염두에 있지만 매핑 공간에서 사용 하는 카메라만 볼 수는 사용자 앞에 3.1 m 공간 매핑 사용자가 관찰 하는 가까운 거리에서 과거에서 하지 않는 한 모든 더 멀리 떨어져 있는 화면에 대해 알지 못합니다.
   * 사용자를 노출 하는 검색 된 인식 하므로이 효과를 시각적 피드백을 제공 해야 하는 응용 프로그램, 예를 들어 가상 그림자 스캔 한 표면에 캐스팅 홀로그램 해당 화면에 배치 하면 도움이 될 수 있습니다.
   * 이 경우 공간 표면 관찰자의 경계 볼륨 이어야 합니다 각 프레임 업데이트 본문 잠긴 [공간 좌표계](coordinate-systems.md)사용자 뒤에 오도록, 합니다.

* **적합 한 위치 찾기**
   * 응용 프로그램 특정 요구 사항이 있는 위치에 사용 하기 위해 디자인 됩니다.
   * 예를 들어, 응용 프로그램은 안전 하 게 holographic 둘러싼-fu를 연습해 볼 수 있도록 사용자 중심 빈 영역이 필요할 수 있습니다.
   * 응용 프로그램을 사용자에 게 특정 요구 사항이 통신 하 고 명확한 시각적 피드백을 사용 하 여이 보강 해야 합니다.
   * 이 예제에서는 응용 프로그램 범위의 필요한 빈 영역을 시각화 하 고이 영역 내에서 원치 않는 개체의 현재 상태를 시각적으로 강조 표시 해야 합니다.
   * 이 경우 경계 볼륨 공간 표면 관찰자의 세계 잠긴 사용 해야 [공간 좌표계](coordinate-systems.md) 선택한 위치에 있습니다.

* **Surfaces의 적합 한 구성을 찾기**
   * 응용 프로그램 구성이 필요할 수 있습니다는 특정 예를 들어 두 대형 화면의 flat 미러의 holographic hall 만들려면 벽을 반대입니다.
   * 이러한 경우 응용 프로그램 공간에 적합 한 화면을 검색 하 고 해당 방향으로 사용자를 직접 매핑하여 제공 화면을 분석 해야 합니다.
   * 사용자는 응용 프로그램의 영역 분석을 완전히 신뢰할 수 없는 경우 대체 옵션이 있어야 합니다. 예를 들어, 응용 프로그램에서 플랫 벽 출입구가 올바르게 식별, 사용자는이 오류를 해결 하는 간단한 방법은 필요 합니다.

* **환경의 일부를 검색 합니다.**
   * 응용 프로그램 사용자가 지정한 대로 환경의 일부를 캡처 할 수도 있습니다.
   * 예를 들어, 응용 프로그램 스캔을 대화방의 일부 사용자는 판매 하고자 가구 holographic 분류 광고를 게시할 수 있습니다.
   * 이 경우 응용 프로그램 공간 매핑 데이터는 검사 중에 사용자가 관찰 되는 지역 내에서 캡처해야 합니다.

* **전체 공간 검색**
   * 응용 프로그램 사용자 뒤 포함 하 여 현재 방에 화면의 모든 검색을 필요할 수 있습니다.
   * 예를 들어 게임에서 수백 개의 모든 방향에서 접근 하 고 작은 Lilliputians 포위 Gulliver의 역할에 사용자를 넣을 수 있습니다.
   * 이러한 경우 응용 프로그램 현재에서 화면에 얼마나 많은 공간을 확인 하려면 해야 이미 검색 되 고 중요 한 격차를 사용자의 게이즈를 직접.
   * 이 프로세스에 키를 노출 하는 아직 검색 되지 않은 사용자의 선택을 취소 합니다 시각적 피드백을 제공 합니다. 응용 프로그램 예를 들어 사용할 수 없습니다 [거리 기반 안개](https://msdn.microsoft.com/library/windows/desktop/bb173401%28v=vs.85%29.aspx) 를 시각적으로 공간 매핑 화면에서 다루지 않는 지역 강조 표시 합니다.

* **환경의 초기 스냅숏을 생성**
   * 응용 프로그램을 초기 '스냅숏'을 고려한 후 환경의 모든 변경 내용을 무시 하고자 할 수 있습니다.
   * 이 사용자가 만든 환경을 초기 상태로 긴밀 하 게 결합 된 데이터의 중단을 방지 하려면 적절 한 수 있습니다.
   * 이 경우 응용 프로그램 검사가 완료 되 면 초기 상태로 공간 매핑 데이터의 복사본이 확인 해야 합니다.
   * 응용 프로그램 제공 하려는 경우 여전히 환경에서 폐색 올바르게 될 공간 매핑 데이터에 대 한 업데이트를 받는 계속 해야 합니다.
   * 공간 매핑 데이터에 대 한 지속적인된 업데이트는 또한 환경의 이전 및 현재 상태 간의 차이점을 사용자에 게 명확히 발생 한 모든 변경 내용을 시각화 수 있습니다.

* **환경의 스냅숏을 사용자 시작**
   * 응용 프로그램 에서만 사용자가 지시 하는 경우의 환경 변화에 응답할 수도 있습니다.
   * 예를 들어 사용자 여러 순간에 해당 동작을 표현 하 여 여러 3D의 친구 ' 동상'를 만들 수 있습니다.

* **사용자가 환경을 변경 하도록 허용**
   * 응용 프로그램에 사용자의 환경에서 실시간으로 변경한 내용이 응답 디자인 됩니다.
   * 예를 들어, 그리기를 위해 사용자는 다른 쪽에서 수행 하는 holographic 재생에 대 한 ' 장면 변경'을 트리거할 수 있습니다.

* **매핑 공간 데이터에서 오류를 방지 하려면 사용자 가이드**
   * 응용 프로그램 환경을 스캔 하는 해당 하는 동안 사용자에 게 지침을 제공 하고자 할 수 있습니다.
   * 이 특정 종류를 방지 하려면 사용자는 데 도움이의 [공간 매핑 데이터의 오류](spatial-mapping-design.md#what-influences-spatial-mapping-quality), sunlit windows 또는 미러에서 유지 하는 여 예를 들어 있습니다.

알아야 할 하나의 추가 세부 정보 공간 매핑 데이터의 '범위' 무제한 인지 됩니다. 공간 매핑에 큰 공백 영구 데이터베이스 빌드 시만 해당 데이터에 사용할 수 있는 응용 프로그램에서 사용자 중심 크기가 제한 된 '거품'. 따라서 긴 복도 워크 멀리 떨어져 시작 부분에 먼저 경우 시작 부분에 다시 공간 표면 결국 사라집니다. 사용 가능한 공간 매핑 데이터에서 사라진 것 처럼 후 응용 프로그램에서 이러한 화면을 캐시 하 여 물론 줄일 수 있습니다.

## <a name="mesh-processing"></a>메시 처리

도움이 될 수 표면에서 일반적인 유형의 오류를 검색 하 고 필터링, 제거 또는 적절 하 게 공간 매핑 데이터를 수정 합니다.

해당 공간 매핑 데이터를 실제 화면을 최대한으로 충분히 반영 하지는 것에 주의 해야, 변화 하는 '전혀' 화면에 위험 적용 하므로 모든 처리 합니다.

유용 하다는 메시를 처리 하는 다양 한 유형의 몇 가지 예는 다음과 같습니다.

* **구멍 채우기**
   * 어두운 재질 이루어진 작은 개체를 검색 하지 못하면 주변 화면에 구멍이 남게 될 것입니다.
   * 구멍 폐색에 영향을 줄: '-'는 화면이 불투명 실제 화면에 구멍이 홀로그램을 볼 수 있습니다.
   * 구멍 raycasts에 영향을 줄: raycasts 화면 상호 작용할 수 있도록를 사용 하는 경우이 적절 하지 않을 구멍을 통과 하도록 이러한 광선에 대 한 합니다. 완화 적절 한 크기의 영역을 다루는 여러 raycasts의 번들을 사용 하는 것입니다. 이렇게 하면 '이상 값' 결과 필터링 하려면 하나 raycast 작은 구멍을 통과할 경우에 집계 결과은 여전히 유효할 수 있도록 합니다. 그러나이 방법은 계산 비용에는 대가가 따릅니다 주의 합니다.
   * 구멍 물리학 충돌에 영향을 줄: 물리학 시뮬레이션에 의해 제어 되는 개체 바닥에 빈틈을 통해 삭제 하 고 손실 될 수 있습니다.
   * 알고리즘 방식으로 이러한 표면 메시 구멍을 채우기는 것이 가능 합니다. 그러나 windows 입구 등 실제 공간 채워지지 않습니다 있도록 알고리즘을 조정 해야 합니다. '크기'와 같은 다른 추론을 사용 하 여 실험 해야 하므로 안정적으로 '허수 구멍'에서 ' 실제 구멍'를 구분 하기 어려울 수 있습니다 및 '경계 셰이프'.

* **Hallucination 제거**
   * 반사, 밝은 광원 및 이동 개체는 작은 느린 'hallucinations' 부동 중에 유지할 수 있습니다.
   * Hallucinations 폐색에 영향을 줄: hallucinations 앞의 이동 하 고 다른 홀로그램 occluding 어두운 모양으로 표시 될 수 있습니다.
   * Hallucinations raycasts에 영향을 줄: raycasts 화면 상호 작용할 수 있도록를 사용 하는 이러한 광선 뒤 화면 대신 hallucination에 도달할 수 있습니다. 구멍을 완화 하는 것을 단일 raycast 많은 raycasts 대신 있지만 다시 계산 비용 것입니다.
   * 영향을 물리학 충돌 hallucinations: 물리학 시뮬레이션에 의해 제어 되는 개체는 hallucination에 대해 고정 될 수 있습니다 및 공간의 겉보기 일반 영역을 이동할 수 없습니다.
   * 이러한 hallucinations 표면 메시에서 필터링 할 가능성이 있습니다. 그러나 구멍 마찬가지로 lamp은 같은 실제 작은 개체 및 문 핸들 제거 되지 않습니다 있도록 알고리즘을 조정 해야 합니다.

* **Smoothing**
   * 공간 매핑 대략적인 또는 '잡음이 있는' 실제 대응을 비교 하 여 표시 되는 화면을 반환할 수 있습니다.
   * 다듬기 물리학 충돌에 영향을 줍니다: 바닥 대략적인 경우 물리적으로 시뮬레이션 된 골프 볼 수 있습니다 롤백하지 원활 하 게 가로질러 직선에서입니다.
   * 다듬기 렌더링에 영향을 줍니다: 대략적인 표면 법선의 표면을 직접 시각화는 경우 해당 모양에 영향을 줄 수 있으며 중단 '정리'를 참조 합니다. 화면을 렌더링 하는 데 사용 되는 셰이더에 적절 한 조명 및 질감을 사용 하 여이 문제를 완화 하는 것이 가능 합니다.
   * 거친 표면 메시에서를 평준화 하는 것이 가능 합니다. 그러나 해당 실제 화면에서 추가 화면을 푸시할 수 있습니다이 있습니다. 닫기 관계를 유지 관리 하는 것이 정확한 홀로그램 폐색을 생성 하는 데 holographic 화면을 사용 하 여 정확 하 고 예측 가능한 상호 작용을 위해 사용자가 중요 합니다.
   * 디자인 변경만 필요한 경우에 꼭 짓 점 위치를 변경 하지 않고 꼭 짓 점 법선 완만 하 게 충분할 수 있습니다.

* **평면 찾기**
   * 다양 한 형식의 응용 프로그램 공간 매핑을 통해 제공 되는 화면에서 수행할 수 있는 분석 있습니다.
   * 한 가지 간단한 예는 '찾기 평면'; 화면의 제한, 주로 평면 영역을 식별합니다.
   * 평면 지역 holographic 작업-표면의 holographic 내용을 배치할 수 있는 자동으로 응용 프로그램에서 지역으로 사용할 수 있습니다.
   * 평면 지역에 가장 필요에 맞게는 화면을 사용 하 여 상호 작용 하는 사용자를 안내 하는 사용자 인터페이스를 제한할 수 있습니다.
   * 평면 지역 LCD 화면, 테이블 또는 화이트 보드와 같은 함수 개체에 해당 하는 holographic에 대 한 실제 세계에서와 같이 사용할 수 있습니다.
   * 평면 지역은 플레이 영역에 비디오 게임기 수준의 기반을 형성을 정의할 수 있습니다.
   * 평면 지역 floor 진짜 사람 방법을 가능성이 있는 영역을 식별 하 여 실제 세계를 이동할 가상 에이전트 도움이 될 수 있습니다.

## <a name="prototyping-and-debugging"></a>프로토타입 및 디버깅

### <a name="useful-tools"></a>유용한 도구
* 합니다 [HoloLens 에뮬레이터](using-the-hololens-emulator.md) 실제 HoloLens에 액세스할 수 없는 공간 매핑을 사용 하 여 응용 프로그램을 개발할 수 있습니다. 실제 환경에서 HoloLens에 라이브 세션을 시뮬레이션할 수 있습니다, 그리고 모든 데이터를 사용 하 여 응용 프로그램은 일반적으로 사용, HoloLens 동작, 공간 좌표계 및 공간 매핑 메시를 포함 하 여 합니다. 이 수 할 문제를 디버깅 하 고 코드 변경 내용을 계산 유용할 수 있는 안정적이 고 반복 가능한 입력을 제공 합니다.
* 시나리오를 재현 하려면 라이브 HoloLens에서 네트워크를 통해 공간 매핑 데이터를 캡처한 다음 디스크와 다음 디버깅 세션에 다시 사용 하도록 저장 합니다.
* 합니다 [Windows 장치 포털 3D 뷰](using-the-windows-device-portal.md#3d-view) 공간 매핑 시스템을 통해 현재 사용 가능한 공간 표면의 모두 표시 하는 방법을 제공 합니다. 응용 프로그램 내에서 공간 표면에 비교 기준 제공 예를 들어 모든 공간 표면 누락 되거나 잘못 된 위치에 표시 되는 경우 쉽게 확인할 수 있습니다.

### <a name="general-prototyping-guidance"></a>일반 프로토타입 지침
* 때문에 [오류](spatial-mapping-design.md#what-influences-spatial-mapping-quality) 공간 매개 변수 매핑에서 데이터 강력한 영향을 줄 수 사용자의 환경, 다양 한 환경에서에서 응용 프로그램을 테스트 하는 것이 좋습니다.
* 항상 동일한 위치, 예를 들어 책상에서에서 테스트 하는 습관에서 없는 가져오기 트랩 됩니다. 다른 위치, 모양, 크기 및 자료의 다양 한 화면에서 테스트 해야 합니다.
* 마찬가지로, 가상 또는 기록 된 데이터는 디버깅을 위해 유용할 수도 있지만, 되지 동일한 몇 가지 테스트 사례에 너무 의존 합니다. 이 이전 포착할 수는 더 다양 한 테스트는 중요 한 문제를 찾는 지연 될 수 있습니다.
* 사용할 수 없습니다는 HoloLens 또는 응용 프로그램에서 수행 하는 동일한 방식 때문에 실제 (및 해제 coached 이상적) 사용자를 사용 하 여 테스트를 수행 하는 것이 좋습니다. 실제로 다소 놀라운 분기 하는 방법을 사람들의 동작, 기술 및 가정 될 수 있습니다!

## <a name="see-also"></a>참조
* [대화방 검색 시각화](room-scan-visualization.md)
* [공간 적절 하 게 디자인](spatial-sound-design.md)
* [Unity의 지 속성](persistence-in-unity.md)