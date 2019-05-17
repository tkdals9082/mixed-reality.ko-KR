---
title: 직접 조작
description: 입력된을 직접 조작 모델의 개요
author: caseymeekhof
ms.author: cmeekhof
ms.date: 04/02/2019
ms.topic: article
keywords: 실제로, 게이즈 상호 작용을 대상으로 응시 mixed 디자인, near 바늘 HoloLens
ms.openlocfilehash: 803157bb248a5541ed524ac4f828ccbba9d59ce1
ms.sourcegitcommit: 82d4e5cf4ad46bfdc44d0606844e28c75b6e67ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65730509"
---
# <a name="direct-manipulation"></a>직접 조작

HoloLens 2에 터치를 손으로 홀로그램 dircly 있습니다를 직접 조작 입력된 모델이 있습니다. 직접 조작 하는 목적 실제에서 것 처럼 동작 하는 개체입니다. 있습니다 수 단추를 눌러서, 활성화 및도 및 승차를 잡은 개체를 이동 합니다. 이러한 시나리오에서 2D 콘텐츠 가상 터치 스크린이 처럼 동작합니다.

조작이 사용자가 쉽게 배울 수 있고 직접 너무 재미 있는 예입니다. Arm의 범위 내에 있는 콘텐츠를 사용 하 여 상호 작용 하기 위한 가장 적합 의미 하는 "거의 전달" 입력된 모델을 간주 됩니다.

직접 조작은 유도성을 기반으로 사용자 친숙을 의미 합니다. 사용자를 교육 하려면 기호화 된 제스처 없음 있습니다. 모든 상호 작용 터치 하거나 가져오는 수 있는 시각적 요소 중심으로 구축 됩니다.

## <a name="device-support"></a>장치 지원

| 입력된 모델 | [HoloLens (첫 번째 범용)](https://review.docs.microsoft.com/en-us/windows/mixed-reality/hololens-hardware-details?branch=master) | HoloLens 2 |[몰입 형 헤드셋](https://review.docs.microsoft.com/en-us/windows/mixed-reality/immersive-headset-hardware-details?branch=master)|
|:-------- | :-------| :--------| :------------|
| 직접 조작 | 지원 되지 않습니다 ❌ | 권장 ✔️ | ➕ 대안 [가리키고 커밋](https://review.docs.microsoft.com/en-us/windows/mixed-reality/point-and-commit?branch=master) 것이 좋습니다.

직접 조작은 HoloLens 2에서 기본 입력된 모델 및 새 명확 하 고 직접 추적 시스템을 활용 합니다. 입력된 모델도 동작 컨트롤러를 사용 하 여 몰입 형 헤드셋에서 사용할 수 있지만 개체 조작 외부 상호 작용 하는 기본 수단으로 권장 되지 않습니다.  직접 manipluation HoloLens v1에서 제공 되지 않습니다.

## <a name="collidable-fingertip"></a>Collidable 손끝

HoloLens 2에서 사용자의 실제 손은 인식 및 기본 모델을 왼쪽 및 오른쪽으로 해석 합니다. 홀로그램 바늘와 직접 접촉 하는 아이디어를 구현 하려면 이상적으로 5 colliders 수에 연결할 수 각 직접 기본 모델의 5 손쉽게. 그러나 실질적으로 tactile 피드백 부족 10 collidable 손쉽게 발생 한 예기치 않은 및 예측할 수 없는 충돌 홀로그램을 사용 하 여 합니다. 

따라서 각 집게 손가락으로는 collider 작업만 좋습니다. 아래 이미지 에서처럼에 여전히 collidable 인덱스 손쉽게 1 손가락 누르고 1 손가락 탭, 2 손가락 키를 눌러 손가락 5 press와 같은 다른 손가락을 포함 하는 다양 한 터치 제스처에 대 한 활성 터치 지점으로 사용할 수 있습니다.

![Collidable 손끝 이미지](images/Collidable-Fingertip-720px.jpg)

### <a name="sphere-collider"></a>구체 collider

임의의 일반 셰이프를 사용 하는 대신 구체 collider를 사용 하 고 시각적으로 거의 대상 지정을 위한 더 나은 신호를 제공 하도록를 렌더링 하는 것이 좋습니다. 구의 지름 집게 손가락 터치 정확도를 높이의 두께 일치 해야 합니다. 쉽게 API 직접 호출 하 여 손가락 두께의 변수를 검색할 수 있습니다.

### <a name="fingertip-cursor"></a>손끝 커서

인덱스 손끝에서 collidable 구 렌더링 하는 것 외에도 거의 타기 팅 나은 대화형으로 달성 하기 위해 손끝 커서 고급 솔루션을 만들었습니다. 도넛 모양 커서 인덱스 손끝에서 연결 된 경우 근접성에 따라 동적으로 반응 하는지 방향 및 아래 설명 된 대로 크기를 기준으로 대상:

* 홀로그램으로 집게 손가락을 움직이면 커서는 항상 홀로그램의 화면에 병렬 및 점진적으로 그에 따라 크기를 축소 합니다.
* 손가락 터치 화면을 즉시 커서 점을 축소 하 고 터치 이벤트를 내보냅니다.

대화형 피드백을 사용자 웹 콘텐츠에 대 한 하이퍼링크를 트리거 또는 아래 그림과 같이 단추를 누르면 같은 태스크를 대상으로 하는 거의 고정밀을 달성할 수 있습니다. 

![손끝 커서 이미지](images/Fingertip-Cursor-720px.jpg)

## <a name="bounding-box-with-proximity-shader"></a>근접 셰이더를 사용 하 여 경계 상자

자체 홀로그램 tactile 피드백이 부족 하다 보정을 위해 visual 및 오디오 피드백을 제공할 수가 있어야 합니다. 이 위해 근접 셰이더를 사용 하 여 개념이 경계 상자를 생성합니다. 경계 상자에는 3D 개체를 포함 하는 최소 대규모 영역입니다. 경계 상자에 근접 셰이더를 호출 하는 대화형 렌더링 메커니즘이 있습니다. 근접 셰이더 동작합니다.

* 집게 손가락 범위의 경우 경계 상자의 표면의 손끝 추천 캐스팅 됩니다.
* 화면에 끝 가까워질수록, 추천 그에 따라 압축 합니다.
* 손끝 터치 화면, 즉시 경계 상자 전체 색을 변경 하거나 터치 상태를 반영 하도록 시각 효과 생성 합니다.
* 한편 visual 터치 피드백이 향상 시키기 위해 소리 효과 활성화할 수 있습니다.

![근접 셰이더 이미지를 사용 하 여 경계 상자](images/Bounding-Box-With-Proximity-Shader-720px.jpg)

## <a name="pressable-button"></a>Pressable 단추

collidable 손끝으로 사용자가 매우 기본적인 holographic UI 구성 요소를 pressable 단추와 상호 작용할 준비가 됩니다. Pressable 단추에 맞게 구성 된 키를 눌러 직접 손가락 holographic 단추가입니다. 마찬가지로 tactile 피드백의 부족 pressable 단추 갖추도록 tactile 피드백 관련 문제를 해결 하는 몇 가지 메커니즘입니다.

* 첫 번째 메커니즘에는 이전 섹션에서에서 자세히 설명 하는 셰이더를 근접을 사용 하 여 경계 상자입니다. 근접 접근 하 고 사용자가 더 잘 이해를 제공 하는 데 사용 되는 단추를 사용 하 여 연락처입니다.
* 두 번째는 깊이입니다. 단추를 연결 하는 손끝 후 press, 이해를 만듭니다. 메커니즘은 단추 깊이 축의 손끝 긴밀 하 게 이동 하는 것입니다. (누름)에서 지정 된 깊이 도달 하면 통해 전달한 후 (릴리스)에 깊이 벗어날 때 단추를 트리거할 수 있습니다.
* 소리 효과 단추 트리거될 때 피드백을 강화 하기 위해 추가 되어야 합니다.

![Pressable 단추 이미지](images/Pressable-Button-720px.jpg)

## <a name="2d-slate-interaction"></a>2D 슬레이트 상호 작용

2D 슬레이트는 holographic 컨테이너 2D 앱 콘텐츠를 웹 브라우저와 같은 호스팅. 디자인 개념을 직접 조작 통해 2D 슬레이트를 상호 작용 하기 위한 실제 터치 스크린을 사용 하 여 상호 작용의 멘 탈 모델을 활용 하는 것입니다.

슬레이트 연락처와 상호 작용 합니다.

* 하이퍼링크 또는 단추를 눌러 집게 손가락을 사용 합니다.
* 아래로 스크롤하려면 슬레이트 콘텐츠 집게 손가락을 사용 합니다.
* 사용자에 손가락의 상대적 동작에 따라 슬레이트 콘텐츠 확대/축소 하려면 두 인덱스 손가락을 사용 합니다.

![2D 슬레이트 이미지](images/2D-Slate-Interaction-720px.jpg)

2D 조작 하기 위한 자체를 슬레이트:

* 모서리와 가장 가까운 조작 affordances 표시할 가장자리 쪽으로 손이 접근 합니다.
* 조작 affordances 및 잡고 모퉁이 affordances 통해 균일 한 크기 조정을 수행 edge affordances 통해 원래 대로 되돌릴 수 있습니다.
* 전체 슬레이트를 이동할 수는 2D 슬레이트의 맨 위에 있는 holobar를 가져옵니다.

![슬레이트 조작의 이미지](images/Manipulate-2d-slate-720px.jpg)

## <a name="3d-object-manipulation"></a>3D 개체 조작

HoloLens 2에는 경계 상자 각 3D 개체에 적용 하 여 3D hologramphic 개체를 조작 하면을 사용자가 바늘을 사용 하도록 설정할 수 있습니다. 경계 상자 근접 셰이더를 통해 더 나은 깊이 perception를 제공합니다. 경계 상자를 사용 하 여 두 가지 디자인 3D 개체 조작에 대 한 합니다.

### <a name="affordance-based-manipulation"></a>유도성 기반 조작

이 경계 상자 및 묶어 조작 affordances 통해 3D 개체를 조작할 수 있습니다. 사용자의 직접 가까운 3D 개체를 즉시 경계 상자와 가장 가까운 유도성 표시 여부가 결정 됩니다. 사용자가 전체 개체, 회전 하려면 edge affordances 및 균일 하 게 확장 모퉁이 affordances 이동 하는 경계 상자를 나옵니다.

![3D 개체 조작 이미지](images/3D-Object-Manipulation-720px.jpg)

### <a name="non-affordance-based-manipulation"></a>비-유도성 기반된 조작

이 메커니즘에 없는 유도성 경계 상자에 연결 됩니다. 사용자만 경계 상자를 표시 하 다음 직접 상호 작용할 수 있습니다. 경계 상자는 한 손으로 놓은, 번역 및 회전 개체의 경우 동작 및 방향 손 모양 아이콘이의 연결. 개체는 두 가지 실습을 사용 하 여 놓은, 하는 경우 사용자 수 변환, 확장 및 두 손의 상대적 동작에 따라 회전 합니다.

특정 조작 해야 전체 자릿수를 사용 하는 것이 좋습니다 **유도성 기반 조작**이므로 높은 수준의 세분성을 제공 합니다. 유연한 조작에 대 한 것을 권장 합니다는 **유도성 아닌 조작** 은 즉각적이 고 재미 환경용 수 있습니다.

## <a name="instinctual-gestures"></a>Instinctual 제스처

HoloLens와 달리 (첫 번째 gen)에서는 수업 사용자 Bloom 및 Air 탭과 같은 몇 가지 미리 정의 된 제스처를 합니다. HoloLens 2에 대 한 모든 기호 제스처를 기억 하는 사용자 요청 하지 않습니다. 모든 필요한 사용자 제스처를 홀로그램 및 콘텐츠를 사용 하 여 상호 작용 해야 하는 사용자는 instinctual 합니다. Instinctual 제스처를 달성 하는 방법은 UI affordances의 설계를 통해 제스처를 수행 하는 사용자를 안내 하는 경우

예를 들어 좋습니다 잡기 개체 또는 두 손가락의 축소를 사용 하 여 제어점을 하는 경우 개체 또는 제어점 작아야 합니다. 5 개의 손가락 잡기를 수행할 수 있습니다, 원하는 경우에 개체 또는 제어점 비교적 큰 이어야 합니다. 단추와 마찬가지로, 작은 단추 큰 단추 키를 눌러 해당 손바닥이 사용 하 여 사용자가 권장 하는 동안 손가락을 사용 하 여 키를 사용자 제한 됩니다.

![](images/Instinctual-Gestures-720px.jpg)

## <a name="symmetric-design-between-hands-and-6-dof-controllers"></a>실습 6 DoF 컨트롤러 사이의 대칭 디자인

상호 작용 parallels VR에 AR 및 중인 컨트롤러에 게 사이 그릴 수에서는 이제는 것을 알 수 있습니다. 입력이 모두 해당 환경에서 직접 조작을 트리거하는 데 사용할 수 있습니다. HoloLens 2 위치와 방향을 잃기 닫기 거리 작동 시 실습을 사용 하 여 동일한 방식으로 잡기 단추에서 가능한 한 많은 WMR 동작 컨트롤러에서 수행 합니다. 이 두 플랫폼 간의 상호 작용 경험을 사용 하 여 사용자에 게 제공 하 고 아주 유용 해야 하려는 다른 간에 앱을 포팅 합니다.

## <a name="optimize-with-eye-tracking"></a>시선 추적 최적화

직접 조작 의도 대로 작동 하지만 실수로 홀로그램을 트리거하지 않고 어디서 나 직접을 더 이상 이동할 수 없는 경우에 불편 함을 느끼게 될 신속 하 게 테스트할 수 있습니다 마법 느낄 수 있습니다.
시선 추적 이란 사용자의 의도 더 나은 식별에 도움이 될 수 있습니다.

* **때**: 거짓 조작 응답 트리거를 줄입니다. 어떤 사용자가 현재 참여 하 고 더 나은 이해 하는 데 시선 추적 수 있습니다.
예를 들어, 실제 작업 도구를 얻을 개에 도달 하면 holographic (지침) 텍스트를 읽어는 한다고 가정 합니다.

  이렇게 하면 실수로 (또는 사용자의 필드의 측면 (FOV) 외부 에서도 것) 하기 전에 눈치채는 몇 가지 대화형 holographic 단추에서 손을 이동 합니다.

  요컨대: 사용자 잠시를 홀로그램 살펴보지 않은 아직 터치 또는 감각을 이벤트에 대 한 감지 가능성이 사용자 의도 해당 홀로그램 상호 작용 하는 한 실제로 되지 않았습니다.

* **어느**:  또 다른 예로 false 양의 활성화의 주소를 지정 하는 것 외 더 잘 잡고 또는 여러 홀로그램 가깝게 배치 하는 경우에 특히 정확한 교차 지점 관리자의 관점에서의 선택을 취소 되지 않을 수 있습니다 하는 대로 포크는 홀로그램 식별을 포함 다른 합니다.

  HoloLens 2 눈 추적에 특정 제한 방법을 정확 하 게 하는 동안 게이즈를 시각,이 도움이 될 수 있습니다 매우에 대 한 깊이 불일치가 인해 상호 작용 거의 입력 직접 상호 작용할 때 결정할 수 있습니다.  이를 정확 하 게 조작 위젯 예를 들어 홀로그램 앞 또는 뒤에 손 모양 인지 여부를 확인 하기 어려울 경우에 따라 것을 의미 합니다.

* **위치**: 빠른-척 제스처를 사용 하 여 사용자에 대 한 정보를 사용 하 여 보고 합니다. 홀로그램 잡고 거의 없이 버려도 의도 한 대상으로 합니다.  

    이 경우에 따라 수 있지만 항상 정확 하지 않은 대상 문제 없이 신속 하 게 손 제스처를 수행 하는 작동 될 수 있습니다. 이것이 손 모양 아이콘이 원하는 위치에 벡터를 다시 throw에 대해 설명 하는 데 시선 추적 도움이 될 지 위치입니다.

## <a name="see-also"></a>참조

* [응시 및 커밋](gaze-and-commit.md)
* [지점 및 커밋](point-and-commit.md)
* [상호 작용 기본 사항](interaction-fundamentals.md)