---
uid: Microsoft.Quantum.Intrinsic.I
title: Jag åtgärdar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849396"
---
# <a name="i-operation"></a><span data-ttu-id="6c13c-102">Jag åtgärdar</span><span class="sxs-lookup"><span data-stu-id="6c13c-102">I operation</span></span>

<span data-ttu-id="6c13c-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6c13c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6c13c-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6c13c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6c13c-105">Utför identitets åtgärden (inga-OP) på en enda qubit.</span><span class="sxs-lookup"><span data-stu-id="6c13c-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6c13c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6c13c-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="6c13c-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6c13c-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="6c13c-108">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c13c-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6c13c-109">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6c13c-109">Remarks</span></span>

<span data-ttu-id="6c13c-110">Detta är en no-op.</span><span class="sxs-lookup"><span data-stu-id="6c13c-110">This is a no-op.</span></span> <span data-ttu-id="6c13c-111">Det finns för klar ande och eftersom det ibland är användbart att anropa identiteten i en algoritm eller skicka den som en parameter.</span><span class="sxs-lookup"><span data-stu-id="6c13c-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>