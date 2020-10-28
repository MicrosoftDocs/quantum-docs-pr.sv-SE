---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Funktionen RotationPhasesAsReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731934"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="ab5a2-102">Funktionen RotationPhasesAsReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="ab5a2-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="ab5a2-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ab5a2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ab5a2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab5a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab5a2-105">Konverterar faser som anges som en qubit rotation till faser som anges som partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="ab5a2-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="ab5a2-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ab5a2-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="ab5a2-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="ab5a2-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="ab5a2-108">Matris med en qubit rotation som ska konverteras till partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="ab5a2-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="ab5a2-109">Utdata: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="ab5a2-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="ab5a2-110">En åtgärd som implementerar faser som anges som partiella reflektioner.</span><span class="sxs-lookup"><span data-stu-id="ab5a2-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="ab5a2-111">Referenser</span><span class="sxs-lookup"><span data-stu-id="ab5a2-111">References</span></span>

<span data-ttu-id="ab5a2-112">Vi använder konventionen i</span><span class="sxs-lookup"><span data-stu-id="ab5a2-112">We use the convention in</span></span>

- <span data-ttu-id="ab5a2-113">[ *G.H. Low, i. L. Chuang,*](https://arxiv.org/abs/1707.05391) för relaterade operatorer för reflektions operatorer.</span><span class="sxs-lookup"><span data-stu-id="ab5a2-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>