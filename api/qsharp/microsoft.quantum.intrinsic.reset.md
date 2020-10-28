---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Återställ åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731350"
---
# <a name="reset-operation"></a><span data-ttu-id="064c0-102">Återställ åtgärd</span><span class="sxs-lookup"><span data-stu-id="064c0-102">Reset operation</span></span>

<span data-ttu-id="064c0-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="064c0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="064c0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="064c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="064c0-105">Med en enda qubit, mäter den och ser till att den är i ⟩-läget | 0, så att den kan släppas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="064c0-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="064c0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="064c0-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="064c0-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="064c0-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="064c0-108">Qubit vars tillstånd ska återställas till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="064c0-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="064c0-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="064c0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

