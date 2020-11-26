---
uid: Microsoft.Quantum.Intrinsic.I
title: Jag åtgärdar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198953"
---
# <a name="i-operation"></a><span data-ttu-id="dcee1-102">Jag åtgärdar</span><span class="sxs-lookup"><span data-stu-id="dcee1-102">I operation</span></span>

<span data-ttu-id="dcee1-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="dcee1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="dcee1-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dcee1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dcee1-105">Utför identitets åtgärden (inga-OP) på en enda qubit.</span><span class="sxs-lookup"><span data-stu-id="dcee1-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dcee1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dcee1-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="dcee1-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dcee1-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="dcee1-108">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dcee1-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dcee1-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dcee1-109">Remarks</span></span>

<span data-ttu-id="dcee1-110">Detta är en no-op.</span><span class="sxs-lookup"><span data-stu-id="dcee1-110">This is a no-op.</span></span> <span data-ttu-id="dcee1-111">Det finns för klar ande och eftersom det ibland är användbart att anropa identiteten i en algoritm eller skicka den som en parameter.</span><span class="sxs-lookup"><span data-stu-id="dcee1-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>