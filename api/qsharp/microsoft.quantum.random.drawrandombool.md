---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730955"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="691f7-102">DrawRandomBool-åtgärd</span><span class="sxs-lookup"><span data-stu-id="691f7-102">DrawRandomBool operation</span></span>

<span data-ttu-id="691f7-103">Namnrymd: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="691f7-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="691f7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="691f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="691f7-105">Vid en lyckad sannolikhet returnerar en enskild Bernoulli-utvärdering som är sann med den aktuella sannolikheten.</span><span class="sxs-lookup"><span data-stu-id="691f7-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="691f7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="691f7-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="691f7-107">successProbability: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="691f7-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="691f7-108">Sannolikheten som `true` ska returneras.</span><span class="sxs-lookup"><span data-stu-id="691f7-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="691f7-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="691f7-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="691f7-110">`true` med sannolikhet `successProbability` och `false` sannolikhet `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="691f7-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>