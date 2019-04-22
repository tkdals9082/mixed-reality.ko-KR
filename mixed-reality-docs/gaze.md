---
title: 응시
description: 응시 입력의 첫 번째 형태 이며 혼합된 현실 내에서 대상으로 하는 데 필요한 기본 형태의.
author: thetuvix
ms.author: alexturn
ms.date: 02/24/2019
ms.topic: article
keywords: 혼합된 현실 게이즈, 상호 작용 디자인
ms.openlocfilehash: 9a12a5a3b3a583477fd98caeaa2f6890c67e2655
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604972"
---
# <a name="gaze"></a>응시

**Gaze** 입력의 첫 번째 형태 이며 기본 형식의 혼합된 현실 내에서 대상으로 합니다. 응시 여기서 사용자는 전 세계를 찾고 의도 확인할 수 있습니다이 알려 줍니다. 실제 환경에서 일반적으로 상호 작용 하려는 개체 찾아 보겠습니다. 응시와 동일 합니다.

혼합된 현실 헤드셋 위치 및 사용자의 헤드의 방향을 사용 하 여 해당 헤드 게이즈 벡터를 결정. 사용자의 눈 간에 직접에서 직선 레이저 포인터로이 벡터의 생각할 수 있습니다. 응용 프로그램 모두 자체 홀로그램와이 광선과 교차할 수 전시실 사용자가에 따라 합니다 [공간 매핑](spatial-mapping.md) 메시 사용자 일 수 있습니다 하는 가상 또는 실제 개체를 결정할 수 있습니다.

HoloLens 2에서 상호 작용 통해 근처 또는 훨씬 상호 작용을 제공할 사용자의 헤드 게이즈 대상이 될 수 있습니다.  HoloLens에 (첫 번째 gen) 해당 사용자의 헤드 게이즈를에서 타기 팅 하기 보다는 동안 렌더링 또는 손 모양 아이콘이 위치에 직접 작용 상호 작용 파생 일반적으로 해야 합니다. 손 모양 아이콘이의 상대적 동작 상호 작용을 시작 되 면 컨트롤에 사용할 수 있습니다 합니다 [제스처](gestures.md)와 마찬가지로 합니다 [조작 또는 탐색](gestures.md#composite-gestures) 제스처입니다. 몰입 형 헤드셋을 사용 하 여 대상을 지정할 수 있습니다 하거나 게이즈를 사용 하 여 또는 가리키고 가능한 [컨트롤러 동작](motion-controllers.md)합니다.

<br>

>[!VIDEO https://www.youtube.com/embed/zCPiZlWdVws]

## <a name="device-support"></a>장치 지원

<table>
<tr>
<th>기능</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens (첫 번째 범용)</a></th><th style="width:150px">HoloLens 2</th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">몰입 형 헤드셋</a></th>
</tr><tr>
<td> 헤드 응시</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> ✔️</td>
</tr><tr>
<td> 응시</td><td></td><td style="text-align: center;">✔️</td><td></td>
</tr>
</table>

> [!NOTE]
> HoloLens 2 관련 된 자세한 지침 [예정](index.md#news-and-notes)합니다.


## <a name="uses-of-gaze"></a>응시 사용

혼합된 현실 개발자가 할 수 있는 많은 게이즈를 사용 하 여:
* 앱은 사용자의 이목을 위치를 확인 하려면 장면에서 홀로그램으로 응시를 교차 수 있습니다.
* 제스처와 사용자의 게이즈를 사용자가 선택, 활성화, 가져오기, 스크롤 또는 그렇지 않은 경우 해당 홀로그램 상호 작용에 따라 컨트롤러 누름 앱 대상으로 지정할 수 있습니다.
* 앱 사용자 공간 매핑 메시를 사용 하 여 해당 게이즈 광선과 교차 하 여 홀로그램 실제 화면에 배치 하도록 할 수 있습니다.
* 앱은 사용자가 알 수 *되지* visual 및 오디오 신호 개체 방향으로 변환할 수 있도록 앱을 야기할 수 있는 중요 한 개체의 방향을 확인 합니다.

## <a name="cursor"></a>Cursor

대부분의 앱을 사용할지는 [커서](cursors.md) (또는 다른 시각적 개체/청각 표시)에 사용자의 신뢰를 부여 하려면 아마도 상호 작용 합니다. 일반적으로 전 세계를 홀로그램 또는 실제 화면 일 수 있는 개체에 해당 게이즈 광선 먼저 작용이 커서를 놓습니다.

![게이즈를 표시 하는 예제 visual 커서](images/cursor.jpg)<br>
*게이즈를 표시 하는 예제 visual 커서*

## <a name="giving-action-to-the-users-gaze"></a>사용자의 게이즈를 작업을 제공합니다.

사용자가 홀로그램 또는 해당 게이즈를 사용 하 여 실제 개체를 대상으로 지정 되 면 해당 개체에 대해 작업을 수행 하는 다음 단계가입니다. 사용자 작업을 수행 하는 주요 수단을 통해 됩니다 [제스처](gestures.md)를 [컨트롤러 동작](motion-controllers.md) 하 고 [음성](voice-input.md)합니다.

## <a name="see-also"></a>참조
* [MR 입력 210: 응시](holograms-210.md)
* [응시, 제스처 및 DirectX에서 동작 컨트롤러](gaze,-gestures,-and-motion-controllers-in-directx.md)
* [Unity에서 gaze](gaze-in-unity.md)