---
title: 커서
description: 커서 또는 대상으로 하 여 벡터의 표시기 HoloLens 의도 대 한 이해 하는 하 이해 하려면 사용자에 대 한 지속적인 피드백을 제공 합니다.
author: thetuvix
ms.author: alexturn, thgable
ms.date: 02/24/2019
ms.topic: article
keywords: HoloLens (첫 번째 gen) HoloLens 2, 혼합 현실, 커서, 대상, 게이즈, 제스처
ms.openlocfilehash: cdedcaffabe0f90e7956fdb19a7b85e202fcf403
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59604657"
---
# <a name="cursors"></a>커서

> [!NOTE]
> HoloLens 2 관련 된 자세한 지침 [예정](index.md#news-and-notes)합니다.


커서 또는 표시기에 현재 대상 벡터의 해당 시점에는 HoloLens가 중점을 판단 하는 위치를 이해 하려면 사용자에 대 한 지속적인 피드백을 제공 합니다. 커서에는 사용자가 현재 대상으로 이해를 가리키고 역할 어떤 영역, 홀로그램, 또는 지점 나타내기 위해 피드백을 입력에 응답할 수 있습니다. 디지털 표현과 장치 (아닐 수 확인 의도 대 한 항목 동일)를 사용자의 주의 이해 하는 위치입니다.

커서에서 제공 하는 피드백 시스템에 응답 하는 방식을 예측할 수를 사용자에 게 제공 피드백으로 해당 신호를 사용 하 여 장치에 해당 의도 보다 잘 설명 하 여 궁극적으로 상호 작용 하는 방법에 대 한 확신을 수 있습니다.

## <a name="hololens-1st-gen"></a>HoloLens (첫 번째 범용)

HoloLens에서 콘텐츠를 대상으로 하 (첫 번째 gen) 사용 하 여 주로 수행 됩니다 합니다 [gaze](gaze.md) 벡터 (위치 및 회전 헤드의 제어 하는 빛). 거의 강의 사용자에 대 한 두 가지 형태의 직접 입력을 제공 합니다. 그러나 사용자가 커서를 통해 사용자는 현재 대상으로 하는 시점을 알 수 있으므로 정확한 대상 지정에 대 한 표시 되지 않은 원의 게이즈를 원활 하 게 합니다. 


## <a name="positioning"></a>위치 지정

일반적으로 표시기는 헤드 이동 약 1:1 비율에서 이동 해야 합니다. 향상 (추가 또는 이동 눈에 띄게 됐습니다)을 의도적으로 정비공으로 사용 될 수 있고 예기치 않게 사용 하는 경우 사용자에 대 한 문제 발생 있는 경우도 있습니다 (짤막한 'lag' 커서를 사용 하 여 문제를 방지 하기에 적합 한지 확인 완전히 표시 고정 콘텐츠)입니다. 가장 중요 한 점은 그러나 환경을 해야 솔직히 ""-커서 위치의 표현에 다듬기, 자기를 향상 하는 경우 또는 다른 효과 포함, 시스템은 계속 표시 커서와 위치의 시스템의 이해는 아무 곳에 나 효과 포함 합니다. 커서를 시스템의이 알리는 수 있는 방식의 되었거나 시스템의 하지 사용자의 방식으로 상호 작용할 수 없습니다.

표시기는 사용자 해당 대상으로 지정할 수는 모든 요소에 대 한 방어에서 이상적 잠가야 합니다. 일부 경우 화면 잠금 해야 할 수도 있습니다 [공간 매핑](spatial-mapping.md) 메시에 참여 하거나 모든 "부동" UI 요소의 깊이에 대 한 잠금이 사용자 이해 하는 데 도움이 상호 작용할 수를 실시간으로 합니다.

## <a name="cursor-design-principles"></a>커서 디자인 원칙

### <a name="always-present"></a>항상 있음
* 커서는 항상 존재 하는 것이 좋습니다.
* 사용자가 커서를 찾을 수 없으면 다음 경우 손실 합니다.
* 여기서 커서 있는 사용자에 대해 최적이 아닌 환경을 제공 하는 인스턴스는 예외입니다. 예에는 사용자가 비디오를 시청 하는 경우입니다. 이므로 비디오 중간 항상 커서가이 시점에서 바람직하지 않은 됩니다. 사용자가 작업을 수행 하기 때문에 나타내는 속속들이 경우 커서에만 표시 하기를 고려할 수 있습니다 하는 시나리오입니다. 그렇지 않은 경우 비디오에서 표시 되지 않습니다.

### <a name="cursor-scale"></a>커서 확장
* 커서는 사용자가 쉽게 상호 작용 하 고 콘텐츠를 볼 수 있도록 하는 경우 사용 가능한 대상에 이하의 해야 합니다.
* 만든 환경에 따라 사용자가에 따라 커서 확장 이기도 중요 합니다. 예를 들어 사용자가 추가 하는 대로 환경에서 자리 비움 아마도 커서 상태가 되지 않아야 너무 작아서 되도록 해당 손실 합니다.
* 커서의 크기를 조정 하는 경우에 유기적는 느낌을 제공 하면 규모에 따라를 부드러운 애니메이션을 적용 하는 것이 좋습니다.
* 콘텐츠를 방해 하지 않습니다. 홀로그램 환경 기억 하기 쉬운 게 이며 하에서 커서를 지양 해야 합니다.

### <a name="directionless-cursor"></a>간접 커서
* 오른쪽 커서 모양을 없는 경우에 원환와 같은 다른 간접 셰이프를 사용 하는 것이 좋습니다. 일부 방향을 가리키는 커서 (예: 기존 화살표 커서를) 항상 이런 방식으로 표시 하 여 사용자 혼동을 줄 수 있습니다.
* 커서를 사용 하 여 사용자에 게 상호 작용 명령에 전달할 경우이 예외가입니다. 예를 들어 Windows Holographic 셸에서 홀로그램 크기 조정 하는 경우 커서를 홀로그램 확장 하도록 해당 직접 이동 하는 방법을 사용자에 게 하는 데 도움이 되는 화살표 일시적으로 포함 합니다.

### <a name="look-and-feel"></a>모양과 느낌
* 도넛형 또는 원환체 많은 응용 프로그램에 대 한 커서 works 모양입니다.
* 색 및 만드는 환경에 가장 잘 나타내는 셰이프를 선택 합니다.
* 커서는 특히 발생 하기 쉽습니다 [분리 색](hologram-stability.md#color-separation)합니다.
* 분산 된 불투명도 사용 하 여 작은 커서 유지 정보 없이 시각적 개체 계층 구조를 지배 합니다.
* 콘텐츠를 방해 하 고 용도에서 방해가 될 수 있습니다 그림자 나 강조 표시 뒤에 커서를 사용 하 여 인식 해야 합니다.
* 이렇게 하면 사용자 시스템에 원하는 위치를 볼 수 있는지 미치게 뿐만 아니라는 커서에 정렬 되며 앱의 화면 안, 시스템은 해당 운전자를 인식 합니다.
* 예를 들어 Windows Holographic OS에서 커서 사용자의 환경에서 사용자를 홀로그램 직접 확인 되지 경우에 전 세계에 대 한 인식 느낌 만들기의 화면에 맞도록...
* 근접 범위 내에 없을 때 대화형 요소에 커서를 자기적 잠금. 이 선택 작업을 수행할 때 해당 사용자는 해당 요소와 상호 작용할 신뢰도 높일 수 있습니다.

### <a name="visual-cues"></a>시각 신호
* 세계에서 정보가 많이 되며 홀로그램을 사용 하 여 자세한 내용은 추가 됩니다. 커서는 중요 한 사용자에 게 통신할 수 있는 좋은 방법입니다.
* 환경을 단일 홀로그램에 포커스 된 경우 아마도 커서 맞춥니다 고 마음데 홀로그램 및 변경 셰이프는 홀로그램에서 볼 때만 합니다. 이 값은 홀로그램은 특별 하 고 상호 작용할 수는 사용자에 게 전달할 수 있습니다.
* 응용 프로그램 공간 매핑에서는 그런 다음 커서 정렬 하 고 발견 하는 모든 표면 허 그 수 없습니다. 이 기능을 사용자에 게는 HoloLens 및 응용 프로그램은 공간을 볼 수 있습니다.
* 이러한 작업 제공 되며 실제 세계에서 있다는 사실을 데 도움이 됩니다. 실제 및 가상 간의 격차를 극복 하는 데 도움이 됩니다.
* 아이디어가의 커서가 있을 때 화면 없거나 홀로그램 보기에서 수행 해야 합니다. 옵션 중 하나는 사용자 앞에 미리 지정 된 거리에 배치 합니다.

## <a name="cursor-feedback"></a>커서 피드백

언급 했 듯이 항상 수 있는 커서를 사용 하 여 몇 가지 중요 정보를 전달 하기 위해 커서 할 것이 좋습니다.

### <a name="possible-actions"></a>가능한 작업
* 사용자가를 홀로그램에서 gazing와 해당 홀로그램에 커서가 해당 홀로그램으로 가능한 작업에 전달할 커서를 사용할 수 있습니다.
* 항목 또는 해당 홀로그램 규모가 조정 되는 사용자 예를 들어 구입할 수 있는 커서에서 아이콘을 표시할 수 있습니다. 또는 홀로그램으로 탭 할 수와 같은 간단한 것도 합니다.
* 사용자에 게 의미로 커서에만 추가 정보를 추가 합니다. 이 고, 그렇지 사용자 상태가 변경 하거나 느끼지 못할 수 또는 커서를 혼동 합니다.

### <a name="input-state"></a>입력된 상태
* 사용자의 입력된 상태를 표시 하려면 커서를 사용 수 있습니다. 예를 들어, 직접 상태일 경우 시스템을 확인 하 여 사용자에 게 아이콘을 표시 수 없습니다. 이 사용자는 응용 프로그램 사용자가 조치를 취할 준비를 알고를 확인할 수 있습니다.
* 사용할 음성 명령을 사용자에 커서를 사용할 수도 있습니다 했습니다. 또는 아마도 일시적으로 사용자에 게 알리고 시스템에서 음성 명령 들은는 커서의 색을 변경 합니다.

이러한 다른 커서 상태는 다른 방법으로 구현할 수 있습니다. 상태 시스템 같은 커서를 모델링 하 여 이러한 여러 상태를 구현할 수 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.
* 유휴 상태는 기본 커서를 표시 하는 위치입니다.
* 준비 위치에서 사용자의 직접 되었습니다 준비 상태가입니다.
* 사용자가 특정 상호 작용을 수행 하는 상호 작용 상태가입니다.
* 홀로그램으로 수행할 수 있는 가능한 작업을 전달 가능한 작업 상태가입니다.

다른 상태 감지 되 면 다른 아트 자산을 표시할 수 있도록 이러한 상태 스킨 수 방식으로 구현할 수도 있습니다.

## <a name="going-cursor-free"></a>"커서 무료" 이동

집중 교육의 의미는 환경의 핵심 구성 요소 이며 게이즈 및 제스처) (통해 대상으로 포함 하는 상호 작용 하지 않아도 더욱 정밀 하는 경우에 커서 없이 디자인을 사용 하는 것이 좋습니다. 여전히 시스템에는 일반적으로 충족 되는 커서에서 하지만-해당 대상으로 하는 시스템의 이해에 대 한 지속적인 피드백을 사용 하 여 사용자에 게 제공 하 고 시스템에 의도 확실히 전달할 수 있도록 하는 요구 사항을 충족 해야 합니다. 다른 눈에 띄는 상태 변경을 통해 달성할 수 있는 것 같습니다.

## <a name="see-also"></a>참조
* [제스처](gestures.md)
* [대상으로 응시](gaze-targeting.md)