---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Funktionen SquaredNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848220"
---
# <a name="squarednorm-function"></a><span data-ttu-id="678c9-102">Funktionen SquaredNorm</span><span class="sxs-lookup"><span data-stu-id="678c9-102">SquaredNorm function</span></span>

<span data-ttu-id="678c9-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="678c9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="678c9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="678c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="678c9-105">Returnerar kvadraten 2 – normal för en Vector.</span><span class="sxs-lookup"><span data-stu-id="678c9-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="678c9-106">Description</span><span class="sxs-lookup"><span data-stu-id="678c9-106">Description</span></span>

<span data-ttu-id="678c9-107">Returnerar kvadraten 2 – normal för en Vector; Det innebär att med en inmatad $ \vec{x} $ returneras $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="678c9-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="678c9-108">Indata</span><span class="sxs-lookup"><span data-stu-id="678c9-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="678c9-109">matris: [dubbel](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="678c9-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="678c9-110">Den vektor vars kvadrat 2-norm ska returneras.</span><span class="sxs-lookup"><span data-stu-id="678c9-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="678c9-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="678c9-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="678c9-112">Kvadrat 2 – normal för `array` .</span><span class="sxs-lookup"><span data-stu-id="678c9-112">The squared 2-norm of `array`.</span></span>