---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727282"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="dc900-102">DumpOperation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dc900-102">DumpOperation operation</span></span>

<span data-ttu-id="dc900-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dc900-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dc900-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc900-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc900-105">Med en åtgärd visas diagnostiken för den åtgärd som görs tillgängliga av det aktuella körnings målet.</span><span class="sxs-lookup"><span data-stu-id="dc900-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="dc900-106">Indata</span><span class="sxs-lookup"><span data-stu-id="dc900-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="dc900-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc900-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc900-108">Antalet qubits som den aktuella åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="dc900-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="dc900-109">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="dc900-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dc900-110">Den åtgärd som ska diagnostiseras.</span><span class="sxs-lookup"><span data-stu-id="dc900-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc900-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc900-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc900-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dc900-112">Remarks</span></span>

<span data-ttu-id="dc900-113">Anrop av den här åtgärden har ingen underrättsering i Q #.</span><span class="sxs-lookup"><span data-stu-id="dc900-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="dc900-114">Den exakta diagnostik som visas, om det finns, är beroende av det aktuella körnings målet och redigerings miljön.</span><span class="sxs-lookup"><span data-stu-id="dc900-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="dc900-115">När den används i den fullständiga Quantum-simulatorn visas till exempel en enhetlig matris som används som representerar `op` .</span><span class="sxs-lookup"><span data-stu-id="dc900-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="dc900-116">Observera att när den körs på simulatorer som beviljar en global fas tvetydighet (t. ex.: full tillstånds simulatorn), kan returnerade representationer variera till en global fas.</span><span class="sxs-lookup"><span data-stu-id="dc900-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="dc900-117">På samma sätt kan sortering av matriser för rader och kolumner variera med de konventioner som används av varje simulator som stöder den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="dc900-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>