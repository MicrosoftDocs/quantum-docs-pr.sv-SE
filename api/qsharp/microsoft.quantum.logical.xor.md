---
uid: Microsoft.Quantum.Logical.Xor
title: Funktionen XOR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197100"
---
# <a name="xor-function"></a><span data-ttu-id="00866-102">Funktionen XOR</span><span class="sxs-lookup"><span data-stu-id="00866-102">Xor function</span></span>

<span data-ttu-id="00866-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="00866-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="00866-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00866-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00866-105">Returnerar den booleska exklusiva disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="00866-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="00866-106">Indata</span><span class="sxs-lookup"><span data-stu-id="00866-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="00866-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00866-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00866-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="00866-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="00866-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00866-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00866-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="00866-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="00866-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00866-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00866-112">`true` om och endast om exakt en av `a` och `b` är `true` .</span><span class="sxs-lookup"><span data-stu-id="00866-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>