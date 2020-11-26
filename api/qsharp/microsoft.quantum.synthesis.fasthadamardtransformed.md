---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Funktionen FastHadamardTransformed
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203101"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="404b9-102">Funktionen FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="404b9-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="404b9-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="404b9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="404b9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="404b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="404b9-105">Beräknar Hadamard-transformering av en boolesk funktion i {-1,1} encoding med Yates-metoden</span><span class="sxs-lookup"><span data-stu-id="404b9-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="404b9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="404b9-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="404b9-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="404b9-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="404b9-108">Sanningen-tabell i {-1,1} kodning</span><span class="sxs-lookup"><span data-stu-id="404b9-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="404b9-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="404b9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="404b9-110">Spectral-koefficienter för funktionen</span><span class="sxs-lookup"><span data-stu-id="404b9-110">Spectral coefficients of the function</span></span>