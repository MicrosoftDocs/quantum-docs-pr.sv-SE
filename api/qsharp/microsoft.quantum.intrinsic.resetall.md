---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198698"
---
# <a name="resetall-operation"></a><span data-ttu-id="301ef-102">ResetAll-åtgärd</span><span class="sxs-lookup"><span data-stu-id="301ef-102">ResetAll operation</span></span>

<span data-ttu-id="301ef-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="301ef-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="301ef-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="301ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="301ef-105">Om du har en matris med qubits kan du mäta dem och se till att de är i ⟩-läget | 0 så att de kan släppas på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="301ef-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="301ef-106">Indata</span><span class="sxs-lookup"><span data-stu-id="301ef-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="301ef-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="301ef-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="301ef-108">En matris med qubits vars tillstånd ska återställas till $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="301ef-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="301ef-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="301ef-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

