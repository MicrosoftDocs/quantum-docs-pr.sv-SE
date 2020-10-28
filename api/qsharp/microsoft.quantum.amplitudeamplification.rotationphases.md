---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731942"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="ee258-102">RotationPhases-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="ee258-102">RotationPhases user defined type</span></span>

<span data-ttu-id="ee258-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ee258-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ee258-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee258-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee258-105">Faser för en sekvens med en qubit rotation i amplitud förstärkning.</span><span class="sxs-lookup"><span data-stu-id="ee258-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="ee258-106">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ee258-106">Remarks</span></span>

<span data-ttu-id="ee258-107">Den första parametern är en matris med faser för reflektioner, uttryckt som en produkt av en qubit rotation.</span><span class="sxs-lookup"><span data-stu-id="ee258-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="ee258-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="ee258-108">[ G.H.</span></span> <span data-ttu-id="ee258-109">Låg, I. L.</span><span class="sxs-lookup"><span data-stu-id="ee258-109">Low, I. L.</span></span> <span data-ttu-id="ee258-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="ee258-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>