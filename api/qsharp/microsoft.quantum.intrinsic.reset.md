---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Återställ åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818630"
---
# <a name="reset-operation"></a><span data-ttu-id="d00e9-102">Återställ åtgärd</span><span class="sxs-lookup"><span data-stu-id="d00e9-102">Reset operation</span></span>

<span data-ttu-id="d00e9-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d00e9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d00e9-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d00e9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d00e9-105">Med en enda qubit, mäter den och ser till att den är i ⟩-läget | 0, så att den kan släppas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="d00e9-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d00e9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d00e9-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d00e9-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d00e9-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d00e9-108">Qubit vars tillstånd ska återställas till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d00e9-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d00e9-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d00e9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

