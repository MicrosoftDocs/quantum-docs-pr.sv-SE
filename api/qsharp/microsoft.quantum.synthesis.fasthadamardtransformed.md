---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Funktionen FastHadamardTransformed
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855455"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="7c2dd-102">Funktionen FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="7c2dd-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="7c2dd-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7c2dd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7c2dd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c2dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c2dd-105">Beräknar Hadamard-transformering av en boolesk funktion i {-1,1} encoding med Yates-metoden</span><span class="sxs-lookup"><span data-stu-id="7c2dd-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="7c2dd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7c2dd-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="7c2dd-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7c2dd-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7c2dd-108">Sanningen-tabell i {-1,1} kodning</span><span class="sxs-lookup"><span data-stu-id="7c2dd-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="7c2dd-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7c2dd-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7c2dd-110">Spectral-koefficienter för funktionen</span><span class="sxs-lookup"><span data-stu-id="7c2dd-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="7c2dd-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="7c2dd-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```