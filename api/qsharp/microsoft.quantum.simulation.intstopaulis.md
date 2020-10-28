---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Funktionen IntsToPaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725821"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="a4d48-102">Funktionen IntsToPaulis</span><span class="sxs-lookup"><span data-stu-id="a4d48-102">IntsToPaulis function</span></span>

<span data-ttu-id="a4d48-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a4d48-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a4d48-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4d48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4d48-105">Konverterar en matris med heltal till en matris med en qubit Pauli-operator.</span><span class="sxs-lookup"><span data-stu-id="a4d48-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a4d48-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a4d48-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="a4d48-107">InTS: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a4d48-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a4d48-108">Matris med heltal i intervallet som ska `0..3`  konverteras till Pauli-operatorer.</span><span class="sxs-lookup"><span data-stu-id="a4d48-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a4d48-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a4d48-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a4d48-110">En matris `paulis` med Pauli-operatorer `Pauli[]` har samma längd som det som `ints` `paulis[idxPauli]` är lika med det element som `[PauliI, PauliX, PauliY, PauliZ]` anges av `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="a4d48-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>