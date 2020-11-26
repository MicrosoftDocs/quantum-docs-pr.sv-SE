---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Funktionen IdenticalPointPosFactFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223059"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="3c409-102">Funktionen IdenticalPointPosFactFxP</span><span class="sxs-lookup"><span data-stu-id="3c409-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="3c409-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3c409-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3c409-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3c409-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3c409-105">Kontroll av att alla fasta punkt nummer i den angivna matrisen har identiska punkt positioner vid räkning från den minst signifikanta biten.</span><span class="sxs-lookup"><span data-stu-id="3c409-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="3c409-106">Det vill säga antalet bitar minus punkt position måste vara konstant för alla fasta punkt nummer i matrisen.</span><span class="sxs-lookup"><span data-stu-id="3c409-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3c409-107">Indata</span><span class="sxs-lookup"><span data-stu-id="3c409-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="3c409-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="3c409-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="3c409-109">Matris med Quantum-fasta punkt nummer som ska kontrol leras för kompatibilitet (med hjälp av intyg).</span><span class="sxs-lookup"><span data-stu-id="3c409-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c409-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c409-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

