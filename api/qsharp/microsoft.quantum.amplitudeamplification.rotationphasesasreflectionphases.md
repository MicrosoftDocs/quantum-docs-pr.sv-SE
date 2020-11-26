---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Funktionen RotationPhasesAsReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191201"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="4357a-102">Funktionen RotationPhasesAsReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="4357a-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="4357a-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4357a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4357a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4357a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4357a-105">Konverterar faser som anges som en qubit rotation till faser som anges som partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="4357a-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="4357a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4357a-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="4357a-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="4357a-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="4357a-108">Matris med en qubit rotation som ska konverteras till partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="4357a-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="4357a-109">Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="4357a-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="4357a-110">En åtgärd som implementerar faser som anges som partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="4357a-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="4357a-111">Referenser</span><span class="sxs-lookup"><span data-stu-id="4357a-111">References</span></span>

<span data-ttu-id="4357a-112">Vi använder konventionen i</span><span class="sxs-lookup"><span data-stu-id="4357a-112">We use the convention in</span></span>

- <span data-ttu-id="4357a-113">[ *G.H. Low, i. L. Chuang,*](https://arxiv.org/abs/1707.05391) för relaterade operatorer för reflektions operatorer.</span><span class="sxs-lookup"><span data-stu-id="4357a-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>