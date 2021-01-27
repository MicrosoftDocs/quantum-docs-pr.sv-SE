---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830904"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="acf1b-102">AllowAtMostNQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="acf1b-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="acf1b-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="acf1b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="acf1b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acf1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acf1b-105">Mellan ett anrop till den här åtgärden och dess intilliggande, försäkrar att högst ett angivet antal ytterligare qubits allokeras med hjälp av uttryck.</span><span class="sxs-lookup"><span data-stu-id="acf1b-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="acf1b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="acf1b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="acf1b-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="acf1b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="acf1b-108">Det maximala antalet qubits som kan allokeras.</span><span class="sxs-lookup"><span data-stu-id="acf1b-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="acf1b-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="acf1b-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="acf1b-110">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="acf1b-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="acf1b-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="acf1b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="acf1b-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="acf1b-112">Example</span></span>

<span data-ttu-id="acf1b-113">Följande fragment fungerar inte när de körs på datorer som har stöd för den här diagnostiken:</span><span class="sxs-lookup"><span data-stu-id="acf1b-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="acf1b-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="acf1b-114">Remarks</span></span>

<span data-ttu-id="acf1b-115">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="acf1b-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>