---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Funktionen FastHadamardTransformed
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733894"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="996be-102">Funktionen FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="996be-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="996be-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="996be-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="996be-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="996be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="996be-105">Beräknar Hadamard-transformering av en boolesk funktion i {-1,1} encoding med Yates-metoden</span><span class="sxs-lookup"><span data-stu-id="996be-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="996be-106">Indata</span><span class="sxs-lookup"><span data-stu-id="996be-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="996be-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="996be-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="996be-108">Sanningen-tabell i {-1,1} kodning</span><span class="sxs-lookup"><span data-stu-id="996be-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="996be-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="996be-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="996be-110">Spectral-koefficienter för funktionen</span><span class="sxs-lookup"><span data-stu-id="996be-110">Spectral coefficients of the function</span></span>