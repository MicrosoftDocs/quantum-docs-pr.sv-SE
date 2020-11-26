---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: Funktionen IsCoprimeL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228142"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="5bffc-102">Funktionen IsCoprimeL</span><span class="sxs-lookup"><span data-stu-id="5bffc-102">IsCoprimeL function</span></span>

<span data-ttu-id="5bffc-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5bffc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5bffc-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bffc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bffc-105">Returnerar true om $a $ och $b $ är co-primtal och falskt annars.</span><span class="sxs-lookup"><span data-stu-id="5bffc-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5bffc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5bffc-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5bffc-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5bffc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5bffc-108">det första antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="5bffc-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5bffc-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5bffc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5bffc-110">det andra antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="5bffc-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="5bffc-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5bffc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5bffc-112">Sant, om $a $ och $b $ är co-primtal (t. ex. den största gemensamma divisorn är 1) och falskt annars</span><span class="sxs-lookup"><span data-stu-id="5bffc-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>