---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: Funktionen IsCoprimeI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732851"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="b9a2f-102">Funktionen IsCoprimeI</span><span class="sxs-lookup"><span data-stu-id="b9a2f-102">IsCoprimeI function</span></span>

<span data-ttu-id="b9a2f-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b9a2f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b9a2f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9a2f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9a2f-105">Returnerar true om $a $ och $b $ är co-primtal och falskt annars.</span><span class="sxs-lookup"><span data-stu-id="b9a2f-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="b9a2f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b9a2f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b9a2f-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b9a2f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b9a2f-108">det första antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="b9a2f-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="b9a2f-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b9a2f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b9a2f-110">det andra antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="b9a2f-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="b9a2f-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b9a2f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b9a2f-112">Sant, om $a $ och $b $ är co-primtal (t. ex. den största gemensamma divisorn är 1) och falskt annars</span><span class="sxs-lookup"><span data-stu-id="b9a2f-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>