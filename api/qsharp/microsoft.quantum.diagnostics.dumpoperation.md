---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829280"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="8565a-102">DumpOperation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8565a-102">DumpOperation operation</span></span>

<span data-ttu-id="8565a-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8565a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8565a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8565a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8565a-105">Med en åtgärd visas diagnostiken för den åtgärd som görs tillgängliga av det aktuella körnings målet.</span><span class="sxs-lookup"><span data-stu-id="8565a-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="8565a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8565a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8565a-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8565a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8565a-108">Antalet qubits som den aktuella åtgärden agerar på.</span><span class="sxs-lookup"><span data-stu-id="8565a-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="8565a-109">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just</span><span class="sxs-lookup"><span data-stu-id="8565a-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8565a-110">Den åtgärd som ska diagnostiseras.</span><span class="sxs-lookup"><span data-stu-id="8565a-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8565a-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8565a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="8565a-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="8565a-112">Example</span></span>

<span data-ttu-id="8565a-113">När körs på Quantum Simulator-målet kommer följande fragment att resultera i matrisen $ $ \begin{Aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 1 & 0 & 0) \end{Aligned}.</span><span class="sxs-lookup"><span data-stu-id="8565a-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="8565a-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8565a-114">Remarks</span></span>

<span data-ttu-id="8565a-115">Anrop av den här åtgärden har ingen underrättsering i Q #.</span><span class="sxs-lookup"><span data-stu-id="8565a-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="8565a-116">Den exakta diagnostik som visas, om det finns, är beroende av det aktuella körnings målet och redigerings miljön.</span><span class="sxs-lookup"><span data-stu-id="8565a-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="8565a-117">När den används i den fullständiga Quantum-simulatorn visas till exempel en enhetlig matris som används som representerar `op` .</span><span class="sxs-lookup"><span data-stu-id="8565a-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="8565a-118">Observera att när den körs på simulatorer som beviljar en global fas tvetydighet (t. ex.: full tillstånds simulatorn), kan returnerade representationer variera till en global fas.</span><span class="sxs-lookup"><span data-stu-id="8565a-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="8565a-119">På samma sätt kan sortering av matriser för rader och kolumner variera med de konventioner som används av varje simulator som stöder den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8565a-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>