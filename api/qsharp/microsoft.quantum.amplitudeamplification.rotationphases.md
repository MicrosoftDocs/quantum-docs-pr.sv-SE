---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843969"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="0bfc2-102">RotationPhases-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="0bfc2-102">RotationPhases user defined type</span></span>

<span data-ttu-id="0bfc2-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0bfc2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0bfc2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bfc2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bfc2-105">Faser för en sekvens med en qubit rotation i amplitud förstärkning.</span><span class="sxs-lookup"><span data-stu-id="0bfc2-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="0bfc2-106">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0bfc2-106">Remarks</span></span>

<span data-ttu-id="0bfc2-107">Den första parametern är en matris med faser för reflektioner, uttryckt som en produkt av en qubit rotation.</span><span class="sxs-lookup"><span data-stu-id="0bfc2-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="0bfc2-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="0bfc2-108">[ G.H.</span></span> <span data-ttu-id="0bfc2-109">Låg, I. L.</span><span class="sxs-lookup"><span data-stu-id="0bfc2-109">Low, I. L.</span></span> <span data-ttu-id="0bfc2-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="0bfc2-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>