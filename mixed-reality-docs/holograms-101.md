---
title: MR 기본 사항 101-장치를 사용 하 여 전체 프로젝트
description: Windows Mixed Reality의 기본 사항을 알아보려는 Unity, Visual Studio 및 HoloLens를 사용 하 여이 코딩 연습을 수행 합니다.
author: keveleigh
ms.author: kurtie
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality, HoloLens, 실제로 혼합 홀로그램 academy, 자습서
ms.openlocfilehash: 043ffac8f30a4e29586478b5dca6ecccc2b5afd3
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59599360"
---
>[!NOTE]
>혼합 현실 Academy 자습서 HoloLens로 설계 되었습니다 (첫 번째 gen) 및 혼합 현실 몰입 형 헤드셋 유의 해야 합니다.  따라서 해당 장치에 대 한 개발에 대 한 지침 여전히 알아보려는 개발자를 위한이 자습서를 그대로 둘을 고려해 야 하는 것이 생각 합니다.  이 자습서는 **_없습니다_** 최신 도구 집합 또는 HoloLens 2에 사용 되는 상호 작용을 사용 하 여 업데이트할 수 있습니다.  지원 되는 장치에서 작업을 계속 유지 됩니다. 새 자습서 시리즈의 나중에 게시는 HoloLens 2에 대 한 개발 하는 방법을 보여주는 됩니다.  게시 된 경우이 알림은 이러한 자습서에 대 한 링크를 사용 하 여 업데이트 됩니다.

<br>

# <a name="mr-basics-101-complete-project-with-device"></a>MR 101의 기초: 장치를 사용 하 여 전체 프로젝트

<br>

>[!VIDEO https://www.youtube.com/embed/XKIIEC5BMWg]

이 자습서에서는 안내 완벽 한 프로젝트를 Unity HoloLens 포함 하 여 핵심 Windows Mixed Reality 기능을 보여 주는 기본 제공 [gaze](gaze.md)하십시오 [제스처](gestures.md), [입력음성](voice-input.md), [공간 소리](spatial-sound.md) 하 고 [공간 매핑](spatial-mapping.md)합니다.

이 자습서를 완료 하려면 약 1 시간이 걸립니다.

## <a name="device-support"></a>장치 지원

<table>
<tr>
<th>과정</th><th style="width:150px"> <a href="hololens-hardware-details.md">HoloLens</a></th><th style="width:150px"> <a href="immersive-headset-hardware-details.md">몰입 형 헤드셋</a></th>
</tr><tr>
<td>MR 101의 기초: 장치를 사용 하 여 전체 프로젝트</td><td style="text-align: center;"> ✔️</td><td style="text-align: center;"> </td>
</tr>
</table>

## <a name="before-you-start"></a>시작하기 전 주의 사항

### <a name="prerequisites"></a>사전 요구 사항

* 올바른를 사용 하 여 구성 하는 Windows 10 PC [도구가 설치 되어](install-the-tools.md)입니다.
* HoloLens 장치 [개발에 대해 구성 된](using-visual-studio.md#enabling-developer-mode)합니다.

### <a name="project-files"></a>프로젝트 파일

* 다운로드 합니다 [파일](https://github.com/Microsoft/HolographicAcademy/archive/Holograms-101.zip) 프로젝트에서 필요 합니다. Unity 2017.2 이상이 필요합니다.
  * Unity 5.6 지원이 계속 필요한 경우 사용 하세요 [이 릴리스에서](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.6-101.zip)합니다.
  * Unity 5.5 지원 해야 하는 경우 사용 하세요 [이 릴리스에서](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.5-101.zip)합니다.
  * Unity 5.4 지원이 계속 필요한 경우 사용 하세요 [이 릴리스에서](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.4-101.zip)합니다.
* 취소 보관 파일을 데스크톱 또는 기타 쉽게 달성할 수 있습니다 위치 합니다. 폴더 이름을 변수로 유지 **Origami**합니다.

>[!NOTE]
>을 다운로드 하기 전에 소스 코드를 확인 하려는 경우 있기 [GitHub에서 사용할 수 있는](https://github.com/Microsoft/HolographicAcademy/tree/Holograms-101)합니다.

## <a name="chapter-1---holo-world"></a>1 장-"Holo" world

>[!VIDEO https://www.youtube.com/embed/PmtZGjYFroY]

이 챕터에 첫 번째 Unity 프로젝트 및 빌드를 단계별로 설치 및 배포 프로세스에서는 했습니다.

### <a name="objectives"></a>목표

* Holographic 개발에 대 한 Unity를 설정 합니다.
* 홀로그램을 확인 합니다.
* 만든 홀로그램을 참조 하세요.

### <a name="instructions"></a>지침

* Unity를 시작 합니다.
* 선택 **열려**합니다.
* 위치를 입력 합니다 **Origami** 폴더 되지 않은 보관 된 이전에 있습니다.
* 선택 **Origami** 누릅니다 **폴더 선택**합니다.
* 하므로 **Origami** 프로젝트에 사용 하 여 새 파일에 비어 있는 기본 장면 저장 장면에 없습니다. **파일** / **으로 장면 저장**합니다.
* 새 장면 이름을 **Origami** 누릅니다 합니다 **저장** 단추입니다.

#### <a name="setup-the-main-virtual-camera"></a>주 가상 카메라를 설정 합니다.

* 에 **계층 패널**를 선택 **주 카메라**합니다.
* 에 **검사기** 변환 위치로 설정 **0,0,0**합니다.
* 찾을 합니다 **플래그 지우기** 속성에서 드롭다운을 변경 하 고 **Skybox** 에 **단색**.
* 클릭 합니다 **백그라운드** 필드를 색 선택기를 엽니다.
* 설정할 **R, G, B 및 A** 하 **0**합니다.

#### <a name="setup-the-scene"></a>장면 설치

* 에 **계층 패널**, 클릭 **만들기** 하 고 **빈 항목 만들기**합니다.
* 새을 마우스 오른쪽 단추로 클릭 **GameObject** 고 이름 바꾸기를 선택 합니다. GameObject 이름 바꾸기 **OrigamiCollection**합니다.
* **홀로그램** 프로젝트 패널에서 폴더 (자산을 확장 하 고 홀로그램을 선택 하거나 프로젝트 패널에서 홀로그램 폴더를 두 번 클릭).
  * 끌기 **스테이지** 의 자식 계층 구조로 **OrigamiCollection**합니다.
  * 끌기 **Sphere1** 의 자식 계층 구조로 **OrigamiCollection**합니다.
  * 끌기 **Sphere2** 의 자식 계층 구조로 **OrigamiCollection**합니다.
* 마우스 오른쪽 단추로 클릭 합니다 **Directional Light** 개체를 **계층 패널** 선택한 **삭제**합니다.
* **홀로그램** 폴더를 끌어서 **광원** 의 루트에는 **계층 패널**합니다.
* 에 **계층**를 선택 합니다 **OrigamiCollection**합니다.
* 에 **검사기**, 변환 위치를 설정 **0,-0.5, 2.0**합니다.
* 키를 눌러 합니다 **재생** 여 홀로그램 미리 보기에 Unity에서 단추입니다.
* Origami 개체 미리 보기 창에 표시 됩니다.
* 키를 눌러 **재생** 미리 보기 모드를 중지 됩니다.

#### <a name="export-the-project-from-unity-to-visual-studio"></a>Visual studio에서 Unity 프로젝트 내보내기

* Unity select에서 **파일 > 빌드 설정**합니다.
* 선택 **유니버설 Windows 플랫폼** 에 **플랫폼** 클릭 **플랫폼 전환**합니다.
* 설정 **SDK** 하 **유니버설 10** 하 고 **빌드 형식** 를 **D3D**합니다.
* 확인할 **Unity C# 프로젝트**합니다.
* 클릭 **열기 장면 추가** 장면에 추가 합니다.
* **빌드**를 클릭합니다.
* 표시 되는 파일 탐색기 창에서 만들기를 **새 폴더** 이름을 "App"입니다.
* 한 번 클릭 합니다 **앱 폴더**합니다.
* 키를 눌러 **폴더 선택**합니다.
* Unity 완료 되 면 파일 탐색기 창이 나타납니다.
* 엽니다는 **앱** 폴더입니다.
* (두 번 클릭) 오픈 **Origami.sln**합니다.
* 에 디버그 대상 변경 맨 위의 도구 모음을 사용 하 여 Visual Studio에서 **릴리스** 들어오고를 ARM **X86**합니다.
* 선택한 장치 단추 옆의 화살표를 클릭 **원격 컴퓨터** Wi-fi 상에 서 배포할 수 있습니다.
  * 설정 된 **주소** 이름 또는 IP 주소에 HoloLens 합니다. 장치 IP 주소를 모르는 경우 찾는 위치 **설정 > 네트워크 및 인터넷 > 고급 옵션** Cortana 요청 또는 **"Hey Cortana, 내 IP 주소는 무엇 인가요?"**
  * 대신 선택할 수는 HoloLens USB를 통해 연결 되 면 **장치** USB를 통해 배포 합니다.
  * 유지 된 **인증 모드** 로 설정 **유니버설**합니다.
  * 클릭 **선택**

* 클릭 **디버그 > 디버깅 없이 시작** 누르거나 **ctrl+f5**합니다. 처음으로 장치에 배포할 경우 해야 [Visual Studio를 사용 하 여 쌍](using-visual-studio.md#pairing-your-device-hololens-(1st-gen))합니다.

* Origami 프로젝트는 이제, 프로그램 HoloLens 배포 빌드하고 실행 합니다.
* 에 HoloLens에 놓고에 새 홀로그램을 살펴보겠습니다.

## <a name="chapter-2---gaze"></a>2 장-응시

>[!VIDEO https://www.youtube.com/embed/MSO2BoFSQbM]

이 챕터에 하겠습니다 상호 작용 하는 세 가지 중 첫 번째를 도입 하 여 홀로그램-를 사용 하 여 [gaze](gaze.md)합니다.

### <a name="objectives"></a>목표

* 전 세계 잠긴 커서를 사용 하 여 게이즈를 시각화 합니다.

### <a name="instructions"></a>지침

* Unity 프로젝트에 돌아가서 계속 열려 있는 경우 빌드 설정 창을 닫습니다.
* 선택 된 **홀로그램** 폴더에는 **프로젝트 패널**합니다.
* 끌어서 합니다 **커서** 개체를 **계층 패널** 루트 수준에서.
* 두 번 클릭 합니다 **커서** 개체에 자세히 살펴보겠습니다.
* 마우스 오른쪽 단추로 클릭 합니다 **스크립트** 프로젝트 패널의 폴더입니다.
* 클릭 합니다 **만들기** 하위 메뉴.
* 선택  **C# 스크립트**합니다.
* 스크립트 이름을 **WorldCursor**합니다. 참고: 이름은 대/소문자 구분입니다. .Cs 확장명을 추가할 필요가 없습니다.
* 선택 된 **커서** 개체를 **계층 패널**합니다.
* 끌어서 놓기 합니다 **WorldCursor** 으로 스크립팅 하는 **검사기 패널**합니다.
* 두 번 클릭 합니다 **WorldCursor** 스크립트 Visual Studio에서 엽니다.
* 이 코드를 붙여넣습니다 **WorldCursor.cs** 하 고 **모두 저장**합니다.

```cs
using UnityEngine;

public class WorldCursor : MonoBehaviour
{
    private MeshRenderer meshRenderer;

    // Use this for initialization
    void Start()
    {
        // Grab the mesh renderer that's on the same object as this script.
        meshRenderer = this.gameObject.GetComponentInChildren<MeshRenderer>();
    }

    // Update is called once per frame
    void Update()
    {
        // Do a raycast into the world based on the user's
        // head position and orientation.
        var headPosition = Camera.main.transform.position;
        var gazeDirection = Camera.main.transform.forward;

        RaycastHit hitInfo;

        if (Physics.Raycast(headPosition, gazeDirection, out hitInfo))
        {
            // If the raycast hit a hologram...
            // Display the cursor mesh.
            meshRenderer.enabled = true;

            // Move the cursor to the point where the raycast hit.
            this.transform.position = hitInfo.point;

            // Rotate the cursor to hug the surface of the hologram.
            this.transform.rotation = Quaternion.FromToRotation(Vector3.up, hitInfo.normal);
        }
        else
        {
            // If the raycast did not hit a hologram, hide the cursor mesh.
            meshRenderer.enabled = false;
        }
    }
}
```

* 앱을 다시 빌드해야 **파일 > 빌드 설정**합니다.
* 이전에 배포 하는 데에 HoloLens Visual Studio 솔루션에 반환 합니다.
* ' 모두 다시 로드 ' 메시지가 표시 되 면 선택 합니다.
* 클릭 **디버그-> 디버깅 없이 시작** 누르거나 **ctrl+f5**합니다.
* 이제 장면 살펴보겠습니다 및 커서 개체의 모양을 상호 작용 하는 방법을 확인할 수 있습니다.

## <a name="chapter-3---gestures"></a>3 장-제스처

>[!VIDEO https://www.youtube.com/embed/kW3ThJ2MbvQ]

이 챕터에서는 대 한 지원을 추가 했습니다 [제스처](gestures.md)합니다. 사용자가 문서 구체를 선택 하면 중력 Unity의 물리 엔진을 사용 하 여 설정 하 여 대체 구체를 만들 수 것입니다.

### <a name="objectives"></a>목표

* 선택 제스처를 사용 하 여 홀로그램 사용자를 제어 합니다.

### <a name="instructions"></a>지침

스크립트를 만들어서 시작 하 고 선택 제스처를 검색할 수 있습니다.

* 에 **스크립트** 폴더를 라는 스크립트를 만듭니다 **GazeGestureManager**합니다.
* 끌기 합니다 **GazeGestureManager** 에 스크립트를 **OrigamiCollection** 개체 계층 구조에서.
* 엽니다는 **GazeGestureManager** Visual Studio에서 스크립트 및 다음 코드를 추가 합니다.

```cs
using UnityEngine;
using UnityEngine.XR.WSA.Input;

public class GazeGestureManager : MonoBehaviour
{
    public static GazeGestureManager Instance { get; private set; }

    // Represents the hologram that is currently being gazed at.
    public GameObject FocusedObject { get; private set; }

    GestureRecognizer recognizer;

    // Use this for initialization
    void Awake()
    {
        Instance = this;

        // Set up a GestureRecognizer to detect Select gestures.
        recognizer = new GestureRecognizer();
        recognizer.Tapped += (args) =>
        {
            // Send an OnSelect message to the focused object and its ancestors.
            if (FocusedObject != null)
            {
                FocusedObject.SendMessageUpwards("OnSelect", SendMessageOptions.DontRequireReceiver);
            }
        };
        recognizer.StartCapturingGestures();
    }

    // Update is called once per frame
    void Update()
    {
        // Figure out which hologram is focused this frame.
        GameObject oldFocusObject = FocusedObject;

        // Do a raycast into the world based on the user's
        // head position and orientation.
        var headPosition = Camera.main.transform.position;
        var gazeDirection = Camera.main.transform.forward;

        RaycastHit hitInfo;
        if (Physics.Raycast(headPosition, gazeDirection, out hitInfo))
        {
            // If the raycast hit a hologram, use that as the focused object.
            FocusedObject = hitInfo.collider.gameObject;
        }
        else
        {
            // If the raycast did not hit a hologram, clear the focused object.
            FocusedObject = null;
        }

        // If the focused object changed this frame,
        // start detecting fresh gestures again.
        if (FocusedObject != oldFocusObject)
        {
            recognizer.CancelGestures();
            recognizer.StartCapturingGestures();
        }
    }
}
```

* 명명 된이 이번 Scripts 폴더에서 다른 스크립트를 만들 **SphereCommands**합니다.
* 확장을 **OrigamiCollection** 계층 뷰에서 개체입니다.
* 끌기 합니다 **SphereCommands** 에 스크립트를 **Sphere1** 계층 패널에서 개체입니다.
* 끌기 합니다 **SphereCommands** 에 스크립트를 **Sphere2** 계층 패널에서 개체입니다.
* 편집을 위해 Visual Studio에서 스크립트를 열거나 및이 사용 하 여 기본 코드를 바꿉니다.

```cs
using UnityEngine;

public class SphereCommands : MonoBehaviour
{
    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // If the sphere has no Rigidbody component, add one to enable physics.
        if (!this.GetComponent<Rigidbody>())
        {
            var rigidbody = this.gameObject.AddComponent<Rigidbody>();
            rigidbody.collisionDetectionMode = CollisionDetectionMode.Continuous;
        }
    }
}
```

* 내보내기 빌드하고 HoloLens에 앱을 배포 합니다.
* 구 중 하나를 살펴봅니다.
* 선택 제스처를 수행 하 고 아래의 화면에 끌어 구체를 관찰 합니다.

## <a name="chapter-4---voice"></a>4 장-음성

>[!VIDEO https://www.youtube.com/embed/1-Aq0VVtHM8]

이 챕터에서는 두 가지에 대 한 지원을 추가한 [음성 명령](voice-input.md): "재설정된 world"를 원래 위치로 삭제 구 돌아간 "구 Drop" 대체 구체를 확인 합니다.

### <a name="objectives"></a>목표

* 백그라운드에서 항상 수신 대기 하는 음성 명령을 추가 합니다.
* 음성 명령에 반응 하는 홀로그램을 만듭니다.

### <a name="instructions"></a>지침

* 에 **스크립트** 폴더를 라는 스크립트를 만듭니다 **SpeechManager**합니다.
* 끌기 합니다 **SpeechManager** 에 스크립트를 **OrigamiCollection** 계층 구조의 개체
* 엽니다는 **SpeechManager** Visual Studio의 스크립트입니다.
* 이 코드를 붙여넣습니다 **SpeechManager.cs** 하 고 **모두 저장**:

```cs
using System.Collections.Generic;
using System.Linq;
using UnityEngine;
using UnityEngine.Windows.Speech;

public class SpeechManager : MonoBehaviour
{
    KeywordRecognizer keywordRecognizer = null;
    Dictionary<string, System.Action> keywords = new Dictionary<string, System.Action>();

    // Use this for initialization
    void Start()
    {
        keywords.Add("Reset world", () =>
        {
            // Call the OnReset method on every descendant object.
            this.BroadcastMessage("OnReset");
        });

        keywords.Add("Drop Sphere", () =>
        {
            var focusObject = GazeGestureManager.Instance.FocusedObject;
            if (focusObject != null)
            {
                // Call the OnDrop method on just the focused object.
                focusObject.SendMessage("OnDrop", SendMessageOptions.DontRequireReceiver);
            }
        });

        // Tell the KeywordRecognizer about our keywords.
        keywordRecognizer = new KeywordRecognizer(keywords.Keys.ToArray());

        // Register a callback for the KeywordRecognizer and start recognizing!
        keywordRecognizer.OnPhraseRecognized += KeywordRecognizer_OnPhraseRecognized;
        keywordRecognizer.Start();
    }

    private void KeywordRecognizer_OnPhraseRecognized(PhraseRecognizedEventArgs args)
    {
        System.Action keywordAction;
        if (keywords.TryGetValue(args.text, out keywordAction))
        {
            keywordAction.Invoke();
        }
    }
}
```

* 엽니다는 **SphereCommands** Visual Studio의 스크립트입니다.
* 스크립트를 다음과 같이 업데이트 합니다.

```cs
using UnityEngine;

public class SphereCommands : MonoBehaviour
{
    Vector3 originalPosition;

    // Use this for initialization
    void Start()
    {
        // Grab the original local position of the sphere when the app starts.
        originalPosition = this.transform.localPosition;
    }

    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // If the sphere has no Rigidbody component, add one to enable physics.
        if (!this.GetComponent<Rigidbody>())
        {
            var rigidbody = this.gameObject.AddComponent<Rigidbody>();
            rigidbody.collisionDetectionMode = CollisionDetectionMode.Continuous;
        }
    }

    // Called by SpeechManager when the user says the "Reset world" command
    void OnReset()
    {
        // If the sphere has a Rigidbody component, remove it to disable physics.
        var rigidbody = this.GetComponent<Rigidbody>();
        if (rigidbody != null)
        {
            rigidbody.isKinematic = true;
            Destroy(rigidbody);
        }

        // Put the sphere back into its original local position.
        this.transform.localPosition = originalPosition;
    }

    // Called by SpeechManager when the user says the "Drop sphere" command
    void OnDrop()
    {
        // Just do the same logic as a Select gesture.
        OnSelect();
    }
}
```

* 내보내기 빌드하고 HoloLens에 앱을 배포 합니다.
* 구 중 하나를 확인 하 고 "**Drop 구체**"입니다.
* 예를 들어 "**다시 설정 전 세계**"를 초기 위치로 전환 합니다.

## <a name="chapter-5---spatial-sound"></a>5 장-공간 소리

>[!VIDEO https://www.youtube.com/embed/Aj4de5Ncbfo]

이 챕터에서는에서는 음악 앱을 추가 하 고 특정 작업에 음향 효과 트리거해야 합니다. 사용할 예정 [공간 소리](spatial-sound.md) 소리 3D 공간에서 특정 위치를 제공 합니다.

### <a name="objectives"></a>목표

* 사용자 환경에서 홀로그램 들어보세요.

### <a name="instructions"></a>지침

* 위쪽 메뉴에서 Unity에서에서 **편집 > 프로젝트 설정 > 오디오**
* 오른쪽에 있는 검사기 창에서 찾을 합니다 **입체 음향 플러그 인** 설정 하 고 선택 **MS HRTF 입체 음향**합니다.
* **홀로그램** 프로젝트 창에서 폴더를 끌어 합니다 **앰 비 언스** 개체를 **OrigamiCollection** 계층 패널에서 개체입니다.
* 선택 **OrigamiCollection** 찾고 합니다 **오디오 원본** 검사기 패널에서 구성 요소입니다. 이러한 속성을 변경 합니다.
  * 확인 합니다 **Spatialize** 속성입니다.
  * 확인 합니다 **절전 모드 해제에서 재생**합니다.
  * 변경 **공간 Blend** 하 **3D** 슬라이더 오른쪽으로 끌어서 합니다. 값을 슬라이더를 이동 하면 0에서 1로 변경 해야 합니다.
  * 확인 합니다 **루프** 속성입니다.
  * 확장 **3D 소리 설정**를 입력 하 고 **0.1** 에 대 한 **Doppler 수준**합니다.
  * 설정할 **볼륨 롤오프** 하 **로그 롤오프**합니다.
  * 설정할 **최대 거리** 하 **20**합니다.
* 에 **스크립트** 폴더를 라는 스크립트를 만듭니다 **SphereSounds**합니다.
* 끌어서 놓기 **SphereSounds** 에 **Sphere1** 하 고 **Sphere2** 개체 계층 구조에서.
* 오픈 **SphereSounds** Visual Studio에서 다음 코드를 업데이트 하 고 **모두 저장**합니다.

```cs
using UnityEngine;

public class SphereSounds : MonoBehaviour
{
    AudioSource impactAudioSource = null;
    AudioSource rollingAudioSource = null;

    bool rolling = false;

    void Start()
    {
        // Add an AudioSource component and set up some defaults
        impactAudioSource = gameObject.AddComponent<AudioSource>();
        impactAudioSource.playOnAwake = false;
        impactAudioSource.spatialize = true;
        impactAudioSource.spatialBlend = 1.0f;
        impactAudioSource.dopplerLevel = 0.0f;
        impactAudioSource.rolloffMode = AudioRolloffMode.Logarithmic;
        impactAudioSource.maxDistance = 20f;

        rollingAudioSource = gameObject.AddComponent<AudioSource>();
        rollingAudioSource.playOnAwake = false;
        rollingAudioSource.spatialize = true;
        rollingAudioSource.spatialBlend = 1.0f;
        rollingAudioSource.dopplerLevel = 0.0f;
        rollingAudioSource.rolloffMode = AudioRolloffMode.Logarithmic;
        rollingAudioSource.maxDistance = 20f;
        rollingAudioSource.loop = true;

        // Load the Sphere sounds from the Resources folder
        impactAudioSource.clip = Resources.Load<AudioClip>("Impact");
        rollingAudioSource.clip = Resources.Load<AudioClip>("Rolling");
    }

    // Occurs when this object starts colliding with another object
    void OnCollisionEnter(Collision collision)
    {
        // Play an impact sound if the sphere impacts strongly enough.
        if (collision.relativeVelocity.magnitude >= 0.1f)
        {
            impactAudioSource.Play();
        }
    }

    // Occurs each frame that this object continues to collide with another object
    void OnCollisionStay(Collision collision)
    {
        Rigidbody rigid = gameObject.GetComponent<Rigidbody>();

        // Play a rolling sound if the sphere is rolling fast enough.
        if (!rolling && rigid.velocity.magnitude >= 0.01f)
        {
            rolling = true;
            rollingAudioSource.Play();
        }
        // Stop the rolling sound if rolling slows down.
        else if (rolling && rigid.velocity.magnitude < 0.01f)
        {
            rolling = false;
            rollingAudioSource.Stop();
        }
    }

    // Occurs when this object stops colliding with another object
    void OnCollisionExit(Collision collision)
    {
        // Stop the rolling sound if the object falls off and stops colliding.
        if (rolling)
        {
            rolling = false;
            impactAudioSource.Stop();
            rollingAudioSource.Stop();
        }
    }
}
```

* 스크립트를 저장 하 고 Unity로 돌아갑니다.
* 내보내기 빌드하고 HoloLens에 앱을 배포 합니다.
* 가깝게 및 스테이지 멀리 이동 하 고 왼쪽-오른쪽 변경 소리가를 설정 합니다.

## <a name="chapter-6---spatial-mapping"></a>6 장-공간 매핑

>[!VIDEO https://www.youtube.com/embed/Pkt1_wNLLXY]

이제 사용 하려는 [공간 매핑](spatial-mapping.md) 게임판 실제 환경에서 실제 개체에 배치 합니다.

### <a name="objectives"></a>목표

* 가상 세계에 실제를 사용자를 가져옵니다.
* 여기서는 가장 중요 한 문제를 홀로그램에 배치 합니다.

### <a name="instructions"></a>지침

* Unity에서 클릭 합니다 **홀로그램** 프로젝트 패널의 폴더입니다.
* 끌어서 합니다 **공간 매핑** 의 루트에 자산을 **계층**합니다.
* 클릭 합니다 **공간 매핑** 계층 구조의 개체입니다.
* 에 **검사기 패널**, 다음 속성을 변경 합니다.
  * 확인 합니다 **Visual 메시 그리기** 상자입니다.
  * 찾습니다 **그리기 자료** 오른쪽에 원을 클릭 합니다. 형식 "**와이어 프레임**" 맨 위에 있는 검색 필드에 있습니다. 결과 클릭 하 고 창을 닫습니다. 이렇게 하면 와이어 프레임을 그리는 자료에 대 한 값을 설정 가져오기 해야 합니다.
* 내보내기 빌드하고 HoloLens에 앱을 배포 합니다.
* 앱을 실행할 때 와이어 프레임 메시를 실제 환경에 오버레이 합니다.
* 단계를 해제 하 고 바닥에 롤링 구 대체 됩니다 하는 방법을 보세요!

이제는 OrigamiCollection 새 위치로 이동 하는 방법을 보여드리겠습니다.

* 에 **스크립트** 폴더를 라는 스크립트를 만듭니다 **TapToPlaceParent**합니다.
* 에 **계층**, 확장를 **OrigamiCollection** 선택 하 고는 **단계** 개체.
* 끌기 합니다 **TapToPlaceParent** 단계 개체에는 스크립트입니다.
* 엽니다는 **TapToPlaceParent** Visual Studio에서 스크립트 및 다음 업데이트:

```cs
using UnityEngine;

public class TapToPlaceParent : MonoBehaviour
{
    bool placing = false;

    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // On each Select gesture, toggle whether the user is in placing mode.
        placing = !placing;

        // If the user is in placing mode, display the spatial mapping mesh.
        if (placing)
        {
            SpatialMapping.Instance.DrawVisualMeshes = true;
        }
        // If the user is not in placing mode, hide the spatial mapping mesh.
        else
        {
            SpatialMapping.Instance.DrawVisualMeshes = false;
        }
    }

    // Update is called once per frame
    void Update()
    {
        // If the user is in placing mode,
        // update the placement to match the user's gaze.

        if (placing)
        {
            // Do a raycast into the world that will only hit the Spatial Mapping mesh.
            var headPosition = Camera.main.transform.position;
            var gazeDirection = Camera.main.transform.forward;

            RaycastHit hitInfo;
            if (Physics.Raycast(headPosition, gazeDirection, out hitInfo,
                30.0f, SpatialMapping.PhysicsRaycastMask))
            {
                // Move this object's parent object to
                // where the raycast hit the Spatial Mapping mesh.
                this.transform.parent.position = hitInfo.point;

                // Rotate this object's parent object to face the user.
                Quaternion toQuat = Camera.main.transform.localRotation;
                toQuat.x = 0;
                toQuat.z = 0;
                this.transform.parent.rotation = toQuat;
            }
        }
    }
}
```

* 내보내기, 앱 빌드 및 배포 합니다.
* 이제 이제 해야 해당 gazing, 선택 제스처를 사용 하 여 다음을 새 위치로 이동 및 선택 제스처를 다시 사용 하 여 게임을 특정 위치에 배치할 수 있습니다.

## <a name="chapter-7---holographic-fun"></a>7 장-Holographic 재미 있는 작업

### <a name="objectives"></a>목표

* Holographic 지 입구를 표시 합니다.

### <a name="instructions"></a>지침

이제 홀로그램 지를 파악 하는 방법을 보여드리겠습니다.

* **홀로그램** 프로젝트 패널에서 폴더:
  * 끌기 **지 하** 의 자식 계층 구조로 **OrigamiCollection**합니다.
* 에 **스크립트** 폴더를 라는 스크립트를 만듭니다 **HitTarget**합니다.
* 에 **계층**를 확장 합니다 **OrigamiCollection**합니다.
* 확장을 **스테이지** 선택한 개체를 **대상** 개체 (파란색 팬).
* 끌기 합니다 **HitTarget** 에 스크립트를 **대상** 개체입니다.
* 엽니다는 **HitTarget** Visual Studio에서 스크립트 및 다음 업데이트:

```cs
using UnityEngine;

public class HitTarget : MonoBehaviour
{
    // These public fields become settable properties in the Unity editor.
    public GameObject underworld;
    public GameObject objectToHide;

    // Occurs when this object starts colliding with another object
    void OnCollisionEnter(Collision collision)
    {
        // Hide the stage and show the underworld.
        objectToHide.SetActive(false);
        underworld.SetActive(true);

        // Disable Spatial Mapping to let the spheres enter the underworld.
        SpatialMapping.Instance.MappingEnabled = false;
    }
}
```

* Unity에서 선택 합니다 **대상** 개체입니다.
* 두 개의 공용 속성이 표시 됩니다.는 **적중 대상** 구성 요소 및이 장면에서 개체를 참조 해야 합니다.
  * 끌어서 **지 하** 에서 **계층** 패널에서 **지 하** 속성에는 **적중 대상** 구성 요소입니다.
  * 끌어서 **단계** 에서 **계층** 패널에서 **숨길 개체** 속성에는 **적중 대상** 구성 요소.
* 내보내기, 앱 빌드 및 배포 합니다.
* 현장에서 Origami 컬렉션을 놓고를 삭제 하는 구체 선택 제스처를 사용 하 여 합니다.
* 구체 (파란색 팬) 대상에 도달 하면 급증이 발생 합니다. 컬렉션을 숨길 수 됩니다 하 고 지 하 세계에 구멍이 표시 됩니다.

## <a name="the-end"></a>끝

및이 자습서의 끝입니다!

알아보았습니다.

* Unity에서 holographic 앱을 만드는 방법입니다.
* 확인 방법 게이즈 제스처, 음성, 소리, 사용 및 공간 매핑.
* Visual Studio를 사용 하는 앱 빌드 및 배포 하는 방법.

사용자 고유의 홀로그램 환경 만들기를 시작할 준비가 되었습니다!

## <a name="see-also"></a>참조

* [MR Basics 101E: 에뮬레이터를 사용 하 여 전체 프로젝트](holograms-101e.md)
* [응시](gaze.md)
* [제스처](gestures.md)
* [음성 입력](voice-input.md)
* [소리 공간](spatial-sound.md)
* [공간 매핑](spatial-mapping.md)