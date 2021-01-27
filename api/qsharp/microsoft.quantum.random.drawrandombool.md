---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853695"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="bf31f-102">DrawRandomBool-åtgärd</span><span class="sxs-lookup"><span data-stu-id="bf31f-102">DrawRandomBool operation</span></span>

<span data-ttu-id="bf31f-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="bf31f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="bf31f-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bf31f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bf31f-105">Vid en lyckad sannolikhet returnerar en enskild Bernoulli-utvärdering som är sann med den aktuella sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="bf31f-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="bf31f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="bf31f-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="bf31f-107">successProbability: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bf31f-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bf31f-108">Sannolikheten som `true` ska returneras.</span><span class="sxs-lookup"><span data-stu-id="bf31f-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bf31f-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf31f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf31f-110">`true` med sannolikhet `successProbability` och `false` sannolikhet `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="bf31f-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="bf31f-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="bf31f-111">Example</span></span>

<span data-ttu-id="bf31f-112">Följande exempel på Q #-kodfragment vänder sig från en prioriterad mynt:</span><span class="sxs-lookup"><span data-stu-id="bf31f-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```