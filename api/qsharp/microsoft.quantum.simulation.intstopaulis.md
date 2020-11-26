---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Funktionen IntsToPaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230539"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="73781-102">Funktionen IntsToPaulis</span><span class="sxs-lookup"><span data-stu-id="73781-102">IntsToPaulis function</span></span>

<span data-ttu-id="73781-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="73781-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="73781-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73781-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73781-105">Konverterar en matris med heltal till en matris med en qubit Pauli-operator.</span><span class="sxs-lookup"><span data-stu-id="73781-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="73781-106">Indata</span><span class="sxs-lookup"><span data-stu-id="73781-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="73781-107">InTS: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73781-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="73781-108">Matris med heltal i intervallet som ska `0..3`  konverteras till Pauli-operatorer.</span><span class="sxs-lookup"><span data-stu-id="73781-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="73781-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="73781-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="73781-110">En matris `paulis` med Pauli-operatorer `Pauli[]` har samma längd som det som `ints` `paulis[idxPauli]` är lika med det element som `[PauliI, PauliX, PauliY, PauliZ]` anges av `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="73781-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>