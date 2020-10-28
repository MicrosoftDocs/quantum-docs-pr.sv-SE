---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Funktionen SquaredNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733803"
---
# <a name="squarednorm-function"></a><span data-ttu-id="9b150-102">Funktionen SquaredNorm</span><span class="sxs-lookup"><span data-stu-id="9b150-102">SquaredNorm function</span></span>

<span data-ttu-id="9b150-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9b150-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9b150-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b150-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b150-105">Returnerar kvadraten 2 – normal för en Vector.</span><span class="sxs-lookup"><span data-stu-id="9b150-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="9b150-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b150-106">Description</span></span>

<span data-ttu-id="9b150-107">Returnerar kvadraten 2 – normal för en Vector; Det innebär att med en inmatad $ \vec{x} $ returneras $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="9b150-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="9b150-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9b150-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="9b150-109">matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9b150-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9b150-110">Den vektor vars kvadrat 2-norm ska returneras.</span><span class="sxs-lookup"><span data-stu-id="9b150-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="9b150-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b150-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b150-112">Kvadrat 2 – normal för `array` .</span><span class="sxs-lookup"><span data-stu-id="9b150-112">The squared 2-norm of `array`.</span></span>