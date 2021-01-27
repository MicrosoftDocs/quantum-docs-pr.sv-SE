---
uid: Microsoft.Quantum.Logical.Xor
title: Funktionen XOR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848460"
---
# <a name="xor-function"></a><span data-ttu-id="3be6d-102">Funktionen XOR</span><span class="sxs-lookup"><span data-stu-id="3be6d-102">Xor function</span></span>

<span data-ttu-id="3be6d-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3be6d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3be6d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3be6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3be6d-105">Returnerar den booleska exklusiva disknuten av två värden.</span><span class="sxs-lookup"><span data-stu-id="3be6d-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="3be6d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3be6d-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="3be6d-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3be6d-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3be6d-108">Det första värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="3be6d-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="3be6d-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3be6d-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3be6d-110">Det andra värdet som ska beaktas.</span><span class="sxs-lookup"><span data-stu-id="3be6d-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3be6d-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3be6d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3be6d-112">`true` om och endast om exakt en av `a` och `b` är `true` .</span><span class="sxs-lookup"><span data-stu-id="3be6d-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>