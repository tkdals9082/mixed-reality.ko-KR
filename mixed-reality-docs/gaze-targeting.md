---
title: 대상으로 응시
description: 모든 상호 작용은 입력된 형식에 관계 없이 상호 작용 하려는 요소를 대상 하는 사용자의 기능을 기반으로 합니다.
author: cre8ivepark
ms.author: jennyk
ms.date: 02/24/2019
ms.topic: article
keywords: 실제로, 게이즈 상호 작용을 대상으로 응시 mixed 디자인
ms.openlocfilehash: c3225e27331f8afcda65469eb84fe5470bf6ee8c
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59600680"
---
# <a name="gaze-targeting"></a>대상으로 응시

모든 상호 작용은 입력된 형식에 관계 없이 상호 작용 하려는 요소를 대상 하는 사용자의 기능을 기반으로 합니다. Windows Mixed Reality에서 일반적으로 이렇게 사용자 게이즈를 사용 하 여 합니다.

사용자는 환경에서 성공적으로 작업할 수 있도록 사용자의 의도 한 사용자의 실제 의도 시스템의 계산된 이해 최대한 가깝게 정렬 되어야 합니다. 수준에 해당 하는 시스템에서 사용자의 의도 한 동작을 해석 하는 올바르게 만족도 증가 하 고 성능 향상 됩니다.

## <a name="device-support"></a>장치 지원

<table>
<tr>
<th>기능</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (첫 번째 범용)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">몰입 형 헤드셋</a></th>
</tr><tr>
<td> 대상으로 응시</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;">✔️ </td>
</tr><tr>
<td> 모니터링 대상</td><td style="text-align: center;"></td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"></td>
</tr>
</table>

> [!NOTE]
> HoloLens 2 관련 된 자세한 지침 [예정](index.md#news-and-notes)합니다.

## <a name="target-sizing-and-feedback"></a>대상 크기 조정 및 피드백

응시 벡터 세밀 하 게 대상에 대 한 사용 가능 하도록 반복적으로 표시 된 있지만 gross 타기 팅 (획득 크며 대상)에 대 한 가장 잘 작동 합니다. 1 ~ 1.5도 최소 대상 크기 3도의 대상을 더 크거나 속도가 종종 허용 하지만 대부분의 시나리오에서 사용자 작업을 허용 해야 합니다. 참고는 3D 요소에 대 한도 2D 영역이 효과적으로 사용자 대상 크기 어떤 프로젝션은 연결 하는 대상 지정이 가능 영역 이어야 합니다. 요소는 "활성" (사용자가 대상으로 하는지 것)는 몇 가지 두드러진 큐는 매우 유용한-포함 될 수 있습니다이 제공 처리가 표시 "가리키기" 효과, 오디오 강조 표시 하거나 클릭 또는 요소를 사용 하 여 커서의 맞춤을 선택 취소 합니다.

![2 개의 미터 거리에 최적의 대상 크기](images/gazetargeting-size-1000px.jpg)<br>
*2 개의 미터 거리에 최적의 대상 크기*

![응시 대상된 개체를 강조 표시의 예](images/gazetargeting-highlighting-640px.jpg)<br>
*응시 대상된 개체를 강조 표시의 예*

## <a name="target-placement"></a>대상 배치

사용자가 해당 필드의 뷰에서 매우 높음 또는 매우 낮은 배치 되는 UI 요소를 찾을 수 없습니다 종종 대부분의 영역 (일반적으로 약 눈 수준) 주요 초점 주위에 주의가 집중 합니다. 일부 적절 한 밴드 눈 모양 수준에서 대부분의 대상과 배치 하면 도움이 됩니다. 경향이 많기 사용자에 대 한 지정 된 상대적으로 적은 visual 영역에 언제 든 지 (비전 attentional 원뿔 약 10도), 그룹화 UI 요소 수준 개념적으로 관련는 초점을 활용할 수 있습니다에서 주의 연결 동작 사용자로 항목을 영역을 통해 해당 게이즈를 이동합니다. UI를 디자인할 때 염두 HoloLens 및 몰입 형 헤드셋 간에 뷰 필드의에서 잠재적인 대규모 변형 합니다.

![그룹화 된 UI 요소에 대해 쉽게 게이즈 Galaxy 탐색기에서 대상으로 하는 예제](images/gazetargeting-grouping-1000px.jpg)<br>
*그룹화 된 UI 요소에 대해 쉽게 게이즈 Galaxy 탐색기에서 대상으로 하는 예제*

## <a name="improving-targeting-behaviors"></a>대상 동작 개선

대상 작업으로 사용자의 의도 또는 수 있으면 결정 (밀접 하 게 근사화), "near miss" 올바르게 대상 지정 된 것 처럼 상호 작용에서 시도 허용 하도록 하는 데 매우 유용할 수 있습니다. 혼합된 현실 환경에 통합할 수 있는 성공적인 방법 중 몇 가지가 있습니다.

### <a name="gaze-stabilization-gravity-wells"></a>응시 안정화 ("중력 웰")

이 켤 것인지 대부분 또는 모든 시간입니다. 이 기술은 사용자가 있을 수 있는 자연 스러운 head/목 jitter를 제거 합니다. 또한 이동 사용 하 여 확인 하 고 말하기 동작으로 인해입니다.

### <a name="closest-link-algorithms"></a>가장 가까운 링크 알고리즘

이러한 스파스 대화형 콘텐츠를 사용 하 여 영역에서 가장 잘 작동 합니다. 사용 하 여 상호 작용을 시도 하는 사용자가 결정할 수 있도록 가능성이 높은 경우 단순히 일정 수준의 의도 가정 하 여 해당 타기 팅 기능을 보완할 수 있습니다.

### <a name="backdatingpostdating-actions"></a>Backdating postdating 작업

이 메커니즘은 속도 요구 하는 작업에 유용 합니다. 사용자가 일련의 속도로 활성화 대상으로 사용 하는 전략을 통해 이동 인 경우 몇 가지 의도 가정 하 고 유용할 수 있습니다 *단계를 누락* 대상 있던 사용자 포커스가 약간 전후 약간 tap (작업을 적용할 50ms 앞/뒤은 유효 초기 테스트에서).

### <a name="smoothing"></a>다듬기

이 메커니즘은 경로 지정 이동을 줄이는 약간의 지터/비틀 거리 면 서 자연 스러운 헤드 이동 특성 때문에 유용 합니다. 경로 동작을 통해 다듬기, 하는 경우 이동이 아닌 시간에 따른 크기/간격 만큼 부드러운

### <a name="magnetism"></a>자기

이 메커니즘 "link 가장 가까운" 알고리즘-대상 방향으로 커서를 도출 하거나 (할지 여부) 여부 hitboxes 단순히 증가의 보다 일반적인 버전으로 간주할 수 가능성이 대상으로 하는 방법을 사용자에 대화형 레이아웃에 대 한 지식을 사용 더 나은 방법은 사용자의 의도. 특히 작은 대상에 대 한 강력한 수 있습니다.

### <a name="focus-stickiness"></a>포커스 연결 유지

근처의 대화형 요소에 포커스를 결정 하는 경우에 바이어스는 현재 포커스가 있는 요소를 제공 합니다. 이 자연 스러운 노이즈를 사용 하 여 두 요소 사이의 중간점에서 부동 때 동작을 전환 하는 불규칙 포커스를 줄일 수 있습니다.

## <a name="see-also"></a>참조
* [제스처](gestures.md)
* [음성 디자인](voice-design.md)
* [커서](cursors.md)