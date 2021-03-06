---
title: 사용자 고유의 몰입 형 환경 디자인
description: Microsoft에서 제공 하는 Windows Mixed Reality 홈 환경 외에도 사용자 고유의을 만들고 사용 하 여 시험해 볼 수 있습니다.
author: thmignon
ms.author: thmignon
ms.date: 04/30/2018
ms.topic: article
keywords: Windows Mixed Reality, Mixed Reality, 가상 현실, VR, MR, 홈, 사용자 지정 환경, 장소, 절벽 집, skyloft, 사용자, 만들기
ms.openlocfilehash: e133e1438410540592a51f54ed136aecd04c6244
ms.sourcegitcommit: 6bc6757b9b273a63f260f1716c944603dfa51151
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73437074"
---
# <a name="design-your-own-immersive-environments"></a>사용자 고유의 몰입 형 환경 디자인

>[!NOTE]
>이는 실험적 기능입니다. 시도 하 고 재미 있게 해 주지만, 모든 것이 예상 대로 작동 하지 않을 경우에는 걱정할 필요가 없습니다. 이 기능의 실행 가능성을 평가 하 고 사용 하는 데 관심이 있기 때문에 [개발자 포럼](https://forums.hololens.com/categories/custom-home-environments)에서 사용자 환경 및 발견 한 버그를 알려 주세요.

[Windows 10 4 월 2018 업데이트](release-notes-april-2018.md)부터 [windows Mixed Reality 홈](navigating-the-windows-mixed-reality-home.md)으로 사용할 수 있는 사용자 지정 환경을 시작 메뉴의 위치 선택기에 추가할 수 있는 실험적 기능을 사용 하도록 설정 했습니다. Windows Mixed Reality에는 집으로 선택할 수 있는 두 가지 기본 환경인 절벽 집과 Skyloft가 있습니다. 사용자 지정 환경을 만들면 직접 만든 목록을 사용 하 여 해당 목록을 확장할 수 있습니다. 작성자와 개발자의 관심을 평가 하는 초기 상태로이 기능을 사용할 수 있도록 하 고, 어떤 종류의 사용자를 만드는 지 확인 하 고, 다양 한 제작 도구를 사용 하는 방법을 이해 하 고 있습니다.

사용자 지정 환경을 사용 하는 경우 teleporting, 앱과의 상호 작용 및 holograms 배치는 절벽 집 및 Skyloft에서와 같이 작동 하는 것을 알 수 있습니다. 판타지에서 웹을 찾아보거나 holograms를 사용 하 여 futuristic 도시를 채울 수 있습니다. 가능성은 무한 합니다.

## <a name="device-support"></a>장치 지원

<table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tr>
        <td><strong>기능과</strong></td>
        <td><a href="hololens-hardware-details.md"><strong>HoloLens</strong></a></td>
        <td><a href="immersive-headset-hardware-details.md"><strong>몰입형 헤드셋</strong></a></td>
    </tr>
     <tr>
        <td>사용자 지정 홈 환경</td>
        <td>❌</td>
        <td>✔️</td>
    </tr>
</table>

## <a name="trying-a-sample-environment"></a>샘플 환경 시도

사용자 지정 홈 환경의 독창적인 기능 중 일부를 보여 주는 샘플 환경을 만들었습니다. 다음 단계를 수행 하 여 사용해 보세요.
1. [샘플 판타지 섬 환경](https://download.microsoft.com/download/B/2/5/B25C1AEF-40CD-4B03-A596-4BCA3D33035A/Fantasy_Island.exe) (링크 지점과 자동 압축 풀기 실행 파일)을 다운로드 합니다.

    ![판타지 섬 샘플 환경](images/FantasyLand.jpg)<br>
    *판타지 섬 샘플 환경*<br>

2. 방금 다운로드 한 **Fantasy_Island** 파일을 실행 합니다.

    > [!NOTE]
    > 웹에서 다운로드 한 .exe 파일을 실행 하려고 할 때 (예:) "Windows 보호 된 PC" 팝업이 발생할 수 있습니다. 이 팝업에서 Fantasy_Island를 실행 하려면 **추가 정보** 를 선택 하 고 **실행**을 클릭 합니다. 이 보안 설정은 신뢰 하지 않을 수 있는 파일을 다운로드 하는 것을 방지 하기 위한 것 이므로 파일 원본을 신뢰 하는 경우에만이 옵션을 선택 하십시오.

3. **파일 탐색기** 를 열고 주소 표시줄에 다음을 붙여 `%LOCALAPPDATA%\Packages\EnvironmentsApp_cw5n1h2txyewy\LocalState`환경 폴더로 이동 합니다.
4. 다운로드 한 샘플 환경을이 폴더에 복사 합니다.
5. **혼합 현실 포털**을 다시 시작 합니다. 그러면 위치 선택기에서 환경 목록이 새로 고쳐집니다.
6. 헤드셋에 배치 합니다. 홈에 있으면 컨트롤러의 Windows 단추를 사용 하 여 **시작 메뉴** 를 엽니다.
7. 고정 된 앱 목록 위의 **장소** 아이콘을 선택 하 여 홈 환경을 선택 합니다.
8. 위치 목록에서 다운로드 한 판타지 섬 환경을 찾을 수 있습니다. 새 사용자 지정 홈 환경을 입력 하려면 **판타지 섬** 를 선택 합니다.

## <a name="creating-your-own-custom-environment"></a>사용자 고유의 사용자 지정 환경 만들기

샘플 환경을 사용 하는 것 외에도 즐겨 사용 하는 3D 편집 소프트웨어를 사용 하 여 사용자 지정 환경을 내보낼 수 있습니다. 

### <a name="modeling-guidelines"></a>모델링 지침

환경을 모델링할 때 다음 권장 사항을 염두에 두어야 합니다. 이렇게 하면 사용자가 believably 크기의 세계에서 올바른 방향으로 생성 하는 데 도움이 됩니다.

1. 사용자는 0, 0, 0을 생성 하므로 원본 주위에서 원하는 생성 위치를 중앙에 배치 합니다.
2. 자산을 전 세계 규모로 제작할 수 있도록 작업 단위를 미터로 설정 해야 합니다.
3. 위쪽 축을 "Y"로 설정 해야 합니다.
4. 자산은 양의 Z 축에 "전달" 해야 합니다.
5. 모든 메시를 결합할 필요는 없지만 리소스가 제한 된 장치를 대상으로 하는 경우에는 권장 됩니다.

### <a name="exporting-your-environment"></a>환경 내보내기

Windows Mixed Reality는 환경에 대 한 자산 배달 형식으로 이진 글 Tf (.bb)를 사용 합니다. 글 Tf는 Khronos 그룹에서 유지 관리 되는 3D 자산 배달에 대 한 무료 무료 오픈 표준입니다. 인 글 Tf는 상호 운용할 수 있는 3D 콘텐츠에 대 한 업계 표준으로 진화 하므로 Microsoft는 Windows 앱과 환경에서 형식을 지원 합니다.

사용자 지정 홈 환경으로 사용할 자산을 내보내는 첫 번째 단계는 글 2.0 모델을 생성 하는 것입니다. 내보내기 Tf 작업 그룹은 [지원 되는 및 변환기의 목록을](https://github.com/KhronosGroup/glTF/blob/master/README.md#converters-and-exporters) 유지 관리 하 여 글 2.0 모델을 만듭니다. 시작 하려면이 페이지에 나열 된 프로그램 중 하나를 사용 하 여 글 2.0 모델을 만들거나 내보내거나 지원 되는 변환기 중 하나를 사용 하 여 기존 모델을 변환 합니다.

또한 Blender 및 3DS Max에서 직접 인 글 록 모델을 내보내기 위한 art 워크플로의 개요를 제공 하는 [이 유용한 문서](https://www.khronos.org/blog/art-pipeline-for-gltf) 를 확인 하세요. 

### <a name="environment-limits"></a>환경 제한

모든 환경은 256 < 이어야 합니다. 256 mb 보다 큰 환경은 로드 되지 않고 사용자를 둘러싼 기본 skybox을 사용 하 여 빈 환경으로 대체 됩니다. 모델을 만들 때이 파일 크기 제한을 염두에 두세요. 또한 아래에 설명 된 대로 WindowsMRAssetConverter를 사용 하 여 환경을 최적화 하려는 경우 최적화 프로그램에서 더 큰 파일 크기의 질감을 만들지만 더 빠르게 로드 하므로 텍스처 크기가 cognizant 합니다. 

### <a name="optimizing-your-environment"></a>환경 최적화

Windows Mixed Reality는 환경의 로드 시간을 크게 줄일 수 있는 다양 한 선택적 최적화를 지원 합니다. 이러한 기능은 많은 질감이 있는 환경에서 로드 하는 동안 시간이 초과 되는 경우에 특히 중요할 수 있습니다. 일반적으로 모든 자산에 대해이 단계를 수행 하는 것이 좋지만 거의 또는 저해상도 질감이 있는 소규모 환경에서는 항상 필요 하지 않습니다. 

이 프로세스를 더 쉽게 수행 하기 위해 최적화를 수행 하기 위해 [Windows Mixed Reality 자산 변환기 (GitHub에서 사용 가능)](https://github.com/Microsoft/glTF-Toolkit/releases) 를 만들었습니다. 이 도구는 Microsoft 글 Tf 도구 키트에서 제공 되는 일련의 유틸리티를 사용 하 여 추가 텍스처 압축, 압축 및 해상도 축소를 수행 하 여 표준 2.0 글 Tf 또는. 글 2를 최적화 합니다. 

변환기는 현재 최적화의 정확한 동작을 조정 하기 위해 여러 플래그를 지원 합니다. 최상의 결과를 위해 다음 플래그를 사용 하 여를 실행 하는 것이 좋습니다.

Flag|권장 값|설명
---|---|---
-최대 질감-크기|1024 또는 2048| 이를 조정 하 여 질감의 품질을 향상 시킵니다. 기본값은 512x512입니다. 값이 클수록 환경의 파일 크기에 크게 영향을 주므로 256 mb 제한을 염두에 두십시오.
-최소 버전|1803|사용자 지정 환경은 windows > = 1803 버전 에서만 지원 됩니다. 이 플래그는 이전 버전의 질감을 제거 하 고 최종 자산의 파일 크기를 줄입니다.

예를 들어 다음과 같은 가치를 제공해야 합니다.

```cmd
WindowsMRAssetConverter FileToConvert.gltf -max-texture-size 1024 -min-version 1803
```

### <a name="testing-your-environment"></a>환경 테스트

최종 .bb 환경을 준비 하 고 나면 헤드셋에서 테스트할 준비가 된 것입니다. ["샘플 환경 시도"](#trying-a-sample-environment) 섹션의 2 단계에서 시작 하 여 사용자 지정 환경을 혼합 현실 홈으로 사용 합니다. 

## <a name="feedback"></a>Feedback

이 실험적 기능을 평가 하는 동안 사용자 지정 환경을 사용 하는 방법, 발생할 수 있는 버그 및 기능을 원하는 방법을 배우는 데 관심이 있습니다. [개발자 포럼](https://forums.hololens.com/categories/custom-home-environments)에서 사용자 지정 홈 환경을 만들고 사용 하기 위한 모든 피드백을 공유 해 주세요.

## <a name="troubleshooting-and-tips"></a>문제 해결 및 팁

### <a name="how-do-i-change-the-name-of-the-environment"></a>환경 이름을 변경 어떻게 할까요??

환경 폴더의 파일 이름은 위치 선택에 사용 됩니다. 환경 이름을 변경 하려면 환경 파일 이름 이름을 바꾸고 Mixed Reality 포털을 다시 시작 합니다.

### <a name="how-do-i-remove-custom-environments-from-my-places-picker"></a>내 위치 선택기에서 사용자 지정 환경을 제거할 어떻게 할까요? 있나요?

사용자 지정 환경을 제거 하려면 PC에서 환경 폴더 (`%LOCALAPPDATA%\Packages\EnvironmentsApp_cw5n1h2txyewy\LocalState`)를 열고 환경을 삭제 합니다. Mixed Reality 포털을 다시 시작한 후에는이 환경이 더 이상 장소 선택기에 표시 되지 않습니다. 

### <a name="how-do-i-default-to-my-favorite-custom-environment"></a>즐겨 사용 하는 사용자 지정 환경에 기본값 어떻게 할까요??

현재 기본 환경을 변경할 수 없습니다. Mixed Reality 포털을 다시 시작할 때마다 절벽 집 환경으로 돌아옵니다. 

### <a name="i-spawn-into-a-blank-space"></a>빈 공간을 생성 합니다.

Windows Mixed Reality [는 256 mb를 초과 하는 환경을 지원 하지 않습니다](#environment-limits). 환경에서이 한도를 초과 하면 모델 없이 빈 하늘 상자가 표시 됩니다.

### <a name="it-takes-a-long-time-to-load-my-environment"></a>환경을 로드 하는 데 시간이 오래 걸립니다.

환경에 선택적 최적화를 추가 하 여 부하를 더 빠르게 만들 수 있습니다. 자세한 내용은 ["환경 최적화"](#optimizing-your-environment) 를 참조 하세요.

### <a name="the-scale-of-my-environment-is-incorrect"></a>내 환경의 소수 자릿수가 잘못 되었습니다.

Windows Mixed Reality는 환경을 로드 하는 경우 글 Tf 단위를 1 미터로 변환 합니다. 환경에서 예기치 않은 규모를 로드 하는 경우 내보내기를 다시 확인 하 여 1 미터 단위로 모델링 하는지 확인 합니다. 

### <a name="the-spawn-location-in-my-environment-is-incorrect"></a>내 환경의 생성 위치가 잘못 되었습니다.

기본 생성 위치는 환경에서 0, 0, 0에 위치 합니다. 현재이 위치를 사용자 지정할 수 없으므로 원하는 생성 지점에 배치 된 원본을 사용 하 여 환경을 내보내 생성 지점을 수정 해야 합니다.

### <a name="the-audio-doesnt-sound-correct-in-the-environment"></a>오디오는 환경에서 제대로 작동 하지 않습니다.

사용자 지정 환경을 만들 때 만든 실제 공간과 일치 하지 않는 acoustics 렌더링 시뮬레이션을 사용 합니다. 소리는 잘못 된 방향에서 제공 될 수 있으며 소리가 muffled 수 있습니다. 

## <a name="see-also"></a>참고 항목
* [Windows Mixed Reality 자산 변환기 (GitHub)](https://github.com/Microsoft/glTF-Toolkit/releases)

