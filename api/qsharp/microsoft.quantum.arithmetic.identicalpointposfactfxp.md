---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Funktionen IdenticalPointPosFactFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731515"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="e09a5-102">Funktionen IdenticalPointPosFactFxP</span><span class="sxs-lookup"><span data-stu-id="e09a5-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="e09a5-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e09a5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e09a5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e09a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e09a5-105">Kontroll av att alla fasta punkt nummer i den angivna matrisen har identiska punkt positioner vid räkning från den minst signifikanta biten.</span><span class="sxs-lookup"><span data-stu-id="e09a5-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="e09a5-106">Det vill säga antalet bitar minus punkt position måste vara konstant för alla fasta punkt nummer i matrisen.</span><span class="sxs-lookup"><span data-stu-id="e09a5-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e09a5-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e09a5-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="e09a5-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="e09a5-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="e09a5-109">Matris med Quantum-fasta punkt nummer som ska kontrol leras för kompatibilitet (med hjälp av intyg).</span><span class="sxs-lookup"><span data-stu-id="e09a5-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="e09a5-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e09a5-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

