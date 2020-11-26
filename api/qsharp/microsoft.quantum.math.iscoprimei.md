---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: Funktionen IsCoprimeI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195366"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="df09c-102">Funktionen IsCoprimeI</span><span class="sxs-lookup"><span data-stu-id="df09c-102">IsCoprimeI function</span></span>

<span data-ttu-id="df09c-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="df09c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="df09c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df09c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df09c-105">Returnerar true om $a $ och $b $ är co-primtal och falskt annars.</span><span class="sxs-lookup"><span data-stu-id="df09c-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="df09c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="df09c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="df09c-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df09c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df09c-108">det första antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="df09c-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="df09c-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df09c-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df09c-110">det andra antalet som Primality testas</span><span class="sxs-lookup"><span data-stu-id="df09c-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="df09c-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df09c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df09c-112">Sant, om $a $ och $b $ är co-primtal (t. ex. den största gemensamma divisorn är 1) och falskt annars</span><span class="sxs-lookup"><span data-stu-id="df09c-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>