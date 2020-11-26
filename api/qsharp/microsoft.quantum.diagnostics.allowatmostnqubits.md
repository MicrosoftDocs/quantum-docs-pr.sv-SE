---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202557"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="ffcca-102">AllowAtMostNQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ffcca-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="ffcca-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ffcca-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ffcca-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffcca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffcca-105">Mellan ett anrop till den här åtgärden och dess intilliggande, försäkrar att högst ett angivet antal ytterligare qubits allokeras med hjälp av uttryck.</span><span class="sxs-lookup"><span data-stu-id="ffcca-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ffcca-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ffcca-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ffcca-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffcca-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffcca-108">Det maximala antalet qubits som kan allokeras.</span><span class="sxs-lookup"><span data-stu-id="ffcca-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="ffcca-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ffcca-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ffcca-110">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="ffcca-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ffcca-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffcca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ffcca-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ffcca-112">Remarks</span></span>

<span data-ttu-id="ffcca-113">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="ffcca-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>