---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Funktionen IdenticalPointPosFactFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846624"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="56001-102">Funktionen IdenticalPointPosFactFxP</span><span class="sxs-lookup"><span data-stu-id="56001-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="56001-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="56001-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="56001-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="56001-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="56001-105">Kontroll av att alla fasta punkt nummer i den angivna matrisen har identiska punkt positioner vid räkning från den minst signifikanta biten.</span><span class="sxs-lookup"><span data-stu-id="56001-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="56001-106">Det vill säga antalet bitar minus punkt position måste vara konstant för alla fasta punkt nummer i matrisen.</span><span class="sxs-lookup"><span data-stu-id="56001-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="56001-107">Indata</span><span class="sxs-lookup"><span data-stu-id="56001-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="56001-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="56001-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="56001-109">Matris med Quantum-fasta punkt nummer som ska kontrol leras för kompatibilitet (med hjälp av intyg).</span><span class="sxs-lookup"><span data-stu-id="56001-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="56001-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56001-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

