---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727366"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="05623-102">AllowAtMostNQubits-åtgärd</span><span class="sxs-lookup"><span data-stu-id="05623-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="05623-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="05623-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="05623-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05623-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05623-105">Mellan ett anrop till den här åtgärden och dess intilliggande, försäkrar att högst ett angivet antal ytterligare qubits allokeras med hjälp av uttryck.</span><span class="sxs-lookup"><span data-stu-id="05623-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="05623-106">Indata</span><span class="sxs-lookup"><span data-stu-id="05623-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="05623-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05623-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05623-108">Det maximala antalet qubits som kan allokeras.</span><span class="sxs-lookup"><span data-stu-id="05623-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="05623-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="05623-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="05623-110">Ett meddelande som ska visas vid fel.</span><span class="sxs-lookup"><span data-stu-id="05623-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05623-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05623-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="05623-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="05623-112">Remarks</span></span>

<span data-ttu-id="05623-113">Den här åtgärden kan ersättas av en no-op på mål som inte stöder den.</span><span class="sxs-lookup"><span data-stu-id="05623-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>