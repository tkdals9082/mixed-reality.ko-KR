---
title: 응시 및 커밋
description: 응시 및 커밋 입력된 모델 개요
author: sostel
ms.author: sostel
ms.date: 05/05/2019
ms.topic: article
ms.localizationpriority: high
keywords: 눈 추적, 혼합 현실, 입력, 응시, 눈 대상, HoloLens 2, 눈 기반 선택
ms.openlocfilehash: 9cc27f24e1275223f33becd1ff0ec6bdf5b43a57
ms.sourcegitcommit: 60060386305eabfac2758a2c861a43c36286b151
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66455089"
---
# <a name="eye-gaze-and-commit"></a><span data-ttu-id="05431-104">응시 및 커밋</span><span class="sxs-lookup"><span data-stu-id="05431-104">Eye-gaze and commit</span></span>
<span data-ttu-id="05431-105">HoloLens 2를 사용 하 여 훌륭한 기회를 응시 & 빠르고 보다 편리 하 게 커밋 헤드 게이즈 대신 응시를 사용 하 여 했습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-105">With HoloLens 2, we have the great opportunity to make gaze & commit faster and more comfortable by using eye gaze instead of head gaze.</span></span> <span data-ttu-id="05431-106">일반을 확장 하 고 따라서 [head 게이즈 및 커밋](gaze-and-commit.md) 상호 작용 모델:</span><span class="sxs-lookup"><span data-stu-id="05431-106">This allows to extend the common [head-gaze and commit](gaze-and-commit.md) interaction model:</span></span> 
1. <span data-ttu-id="05431-107">간단 하 게 대상을 확인 하 고</span><span class="sxs-lookup"><span data-stu-id="05431-107">Simply look at a target and</span></span> 
2. <span data-ttu-id="05431-108">A: 예: 입력 보조 명시적 수행할 대상을 선택 하 여 의도 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="05431-108">To confirm your intention to select the target, perform a secondary explicit input such as a:</span></span>  
   - <span data-ttu-id="05431-109">손 제스처 (예는 어 탭)</span><span class="sxs-lookup"><span data-stu-id="05431-109">Hand gesture (e.g., an Air Tap)</span></span>
   - <span data-ttu-id="05431-110">(예: Bluetooth 키보드 또는에서 clicker) 단추 누름</span><span class="sxs-lookup"><span data-stu-id="05431-110">Button press (e.g., on a Bluetooth keyboard or clicker)</span></span>
   - <span data-ttu-id="05431-111">음성 명령 (예: "Select")</span><span class="sxs-lookup"><span data-stu-id="05431-111">Voice command (e.g., "Select")</span></span>
   - <span data-ttu-id="05431-112">Dwelling (즉, 사용자 유지 찾는 선택 대상에 있는)</span><span class="sxs-lookup"><span data-stu-id="05431-112">Dwelling (i.e., the user simply keeps looking at the target to select)</span></span>

<span data-ttu-id="05431-113">그러나 응시 헤드 게이즈 몇 가지에서 매우 다른 방식으로 작동 하 고 고유한 챌린지 횟수 따라서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05431-113">However, eye gaze behaves very differently to head gaze in certain ways and hence comes with a number of unique challenges.</span></span> <span data-ttu-id="05431-114">에 [눈 Gaze 디자인 지침](eye-tracking.md), 일반적인 이점을 요약 내용 및 사용 하는 경우 고려해 야 할 과제 시각 holographic 앱에 대 한 입력으로 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-114">In the [Eye Gaze Design Guidelines](eye-tracking.md), we summarize general advantages and challenges to take into account when using eye tracking as an input in your holographic app.</span></span> <span data-ttu-id="05431-115">이 섹션에서는 응시로 커밋에 대 한 특정 디자인 고려 사항에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-115">In this section, we focus on the specific design considerations for eye-gaze & commit.</span></span>
<span data-ttu-id="05431-116">먼저, 눈 매우 빠르게 이동 하 고 되므로 신속 하 고 보기를 대상으로 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-116">First, our eyes move incredibly fast and thus are great at quickly targeting across the view.</span></span> <span data-ttu-id="05431-117">따라서 gaze 눈 빠른 게이즈 커밋 작업을 어 탭 또는 단추 누르기와 같은 고속 커밋으로 결합 하는 경우에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-117">This makes eye gaze ideal for quick gaze-and-commit actions especially when combined with fast commits such as an air-tap or button press.</span></span>
   
<span data-ttu-id="05431-118">다음 표에 다음달 디자인 지침 경우 눈을 사용 하 여 이러한 유형의 상호 작용에 대 한 gaze 유념 해야 하는 헤드 및 눈 게이즈 간의 차이점을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-118">In the following, we will address design guidelines when using eye gaze for this type of interaction and will discuss differences between head and eye gaze that you should keep in mind.</span></span>

## <a name="design-guidelines-for-eye-gaze-and-commit"></a><span data-ttu-id="05431-119">디자인-응시 및 커밋에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="05431-119">Design guidelines for eye-gaze and commit</span></span>

<span data-ttu-id="05431-120">**커서를 표시 하지 않습니다**: 상호 작용 하기는 거의 불가능 아니지만 헤드를 사용 하는 경우 커서 없이 gaze, 커서가 신속 하 게 방해 하 고 성가신 응시를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="05431-120">**Do not show a cursor**: While it is nearly impossible to interact without a cursor when using head gaze, the cursor becomes quickly distracting and annoying when using eye gaze.</span></span> <span data-ttu-id="05431-121">사용자에 게 알려 커서에 의존 하지 않고 여부 시선 추적 중인 있고 올바르게 검색 현재 조회할 미묘한 visual을 사용 하 여 대상에서 (자세한 내용은 아래 참조)을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-121">Instead of relying on a cursor to inform the user whether eye tracking is working and has correctly detected the currently looked at target, use subtle visual highlights (more details below).</span></span>

<span data-ttu-id="05431-122">**미묘한 혼합된 hover 피드백에 대 한 노력**: 헤드 응시에 대 한 시각적 피드백을 유용한 것 처럼 보이게 응시를 사용 하 여 매우 많은 일이 환경에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-122">**Strive for subtle blended hover feedback**: What seems great visual feedback for head gaze can result in terrible, overwhelming experiences using eye gaze.</span></span> <span data-ttu-id="05431-123">눈은 매우 빠르고, 필드-의-보기의 지점 간 darting 신속 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-123">Remember that your eyes are enormously fast, quickly darting across points in your field-of-view.</span></span> <span data-ttu-id="05431-124">를 찾아보면 flickery 피드백 (설정/해제) 빠른 갑자기 강조 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-124">Quick sudden highlight changes (on/off) may result in flickery feedback when looking around.</span></span> <span data-ttu-id="05431-125">따라서 가리키기 피드백을 제공 하는 경우는에서 원활 하 게 혼합 된 강조 표시를 사용 하는 것이 좋습니다 (하 고 혼합 된 스케일 아웃 지금 볼 때).</span><span class="sxs-lookup"><span data-stu-id="05431-125">So, when providing hover feedback, we recommend using a smoothly blended-in highlight (and blended-out when looking away).</span></span> <span data-ttu-id="05431-126">이 처음에 확인할 수 있습니다 거의 피드백 대상 보면 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-126">This means that at first you would barely notice the feedback when looking at a target.</span></span> <span data-ttu-id="05431-127">500-1000 밀리초 동안 강조 표시를 강도가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="05431-127">Over the course of 500-1000 ms the highlight would increase in intensity.</span></span> <span data-ttu-id="05431-128">초보 사용자에 게 수를 확인할는 시스템에 올바르게 집중된 대상이 대상 보고 유지, 동안 전문가 gaze 및 피드백의 농도가 될 때까지 기다리지 않고 커밋할 신속 하 게 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-128">While novice users could keep looking at the target to ensure that the system has correctly determined the focused target, expert users could quickly gaze & commit without waiting until the feedback is at its full intensity.</span></span> <span data-ttu-id="05431-129">또한 가리키기 피드백 페이드아웃 때 blend 옵트아웃을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-129">In addition, we also recommend using a blend-out when fading out the hover feedback.</span></span> <span data-ttu-id="05431-130">연구에 따르면 신속 하 게 동작 및 고대비 변경은 (따라서 확인 하지 않은 위치 visual 필드의 영역)에 주변 시야에 확실 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-130">Research has shown that quick motion and contrast changes are very noticeable in your peripheral vision (so, the area of your visual field where you are not looking).</span></span> <span data-ttu-id="05431-131">페이드 아웃 blend 기능으로 느려집니다 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-131">The fade-out doesn't have to be as slow as the blend-in.</span></span> <span data-ttu-id="05431-132">이에 강조 표시에 대 한 고대비 또는 색 변경 내용이 있는 경우에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-132">This is only critical when you have high contrast or color changes for your highlight.</span></span> <span data-ttu-id="05431-133">Hover 피드백에 매우 미묘한 되었으면 차이가 아마도 발견 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05431-133">If the hover feedback was pretty subtle to begin with, you probably won't notice a difference.</span></span>

<span data-ttu-id="05431-134">**응시 및 커밋 신호 동기화 확인**: 입력된 신호 동기화 하므로 간단한 게이즈 & 커밋 어려워집니다 작을 수 있으며, 걱정 하지 마세요!</span><span class="sxs-lookup"><span data-stu-id="05431-134">**Look out for synchronizing gaze and commit signals**: The synchronization of input signals may be less of a challenge for simple gaze & commit, so, don't worry!</span></span> <span data-ttu-id="05431-135">긴 음성 명령 또는 복잡 한 손 제스처 포함 될 수는 있지만 더 복잡 한 커밋 작업을 사용 하려는 경우에 대 한 확인해 볼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05431-135">It is something to look out for in case you want to use more complicated commit actions though that may involve long voice commands or complicated hand gestures.</span></span> <span data-ttu-id="05431-136">대상 확인 하 고 긴 음성 명령을 장모님 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-136">Imagine you look at target and utter a long voice command.</span></span> <span data-ttu-id="05431-137">이야기 하는 데 필요한 시간과 말씀 하 신 내용을 검색 하는 데 필요한 시스템 계정으로 수행에 응시가 일반적으로 장기 이동 장면에서 몇 가지 새 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-137">Taken into account the time that you needed to speak and the time that the system needed to detect what you said, your eye gaze has usually long moved on to some new target in the scene.</span></span> <span data-ttu-id="05431-138">따라서 하거나 사용자가 명령을 인식 된 될 때까지 대상 살펴보면 유지 해야 합니다. 또는 명령 및 새로운 사용자가에 대해 살펴보고 다음 다시 시작을 결정 하는 방법에 대 한 입력을 처리할 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05431-138">Hence, either make your users aware that they may need to keep looking at a target until the command has been recognized or handle the input in a way to determine the onset of the command and what the user had been looking at back then.</span></span>

## <a name="see-also"></a><span data-ttu-id="05431-139">참조</span><span class="sxs-lookup"><span data-stu-id="05431-139">See also</span></span>
* [<span data-ttu-id="05431-140">헤드 게이즈 및 커밋</span><span class="sxs-lookup"><span data-stu-id="05431-140">Head-gaze and commit</span></span>](gaze-and-commit.md)
* [<span data-ttu-id="05431-141">손 제스처</span><span class="sxs-lookup"><span data-stu-id="05431-141">Hand gestures</span></span>](gestures.md)
* [<span data-ttu-id="05431-142">음성 입력 </span><span class="sxs-lookup"><span data-stu-id="05431-142">Voice input</span></span>](voice-design.md)
* [<span data-ttu-id="05431-143">모션 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="05431-143">Motion controllers</span></span>](motion-controllers.md)