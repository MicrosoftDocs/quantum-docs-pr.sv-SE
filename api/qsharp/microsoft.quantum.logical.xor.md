---
uid: Microsoft.Quantum.Logical.Xor
title: Funktionen XOR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732814"
---
# <a name="xor-function"></a><span data-ttu-id="9f275-102">Funktionen XOR</span><span class="sxs-lookup"><span data-stu-id="9f275-102">Xor function</span></span>

<span data-ttu-id="9f275-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9f275-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9f275-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f275-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f275-105">Returnerar den booleska exklusiva disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="9f275-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="9f275-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9f275-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="9f275-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9f275-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9f275-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="9f275-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="9f275-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9f275-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9f275-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="9f275-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9f275-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9f275-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9f275-112">`true` om och endast om exakt en av `a` och `b` är `true` .</span><span class="sxs-lookup"><span data-stu-id="9f275-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>