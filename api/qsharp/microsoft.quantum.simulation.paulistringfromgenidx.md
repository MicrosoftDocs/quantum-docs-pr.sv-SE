---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: Funktionen PauliStringFromGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230318"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="0a06d-102">Funktionen PauliStringFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="0a06d-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="0a06d-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0a06d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0a06d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a06d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a06d-105">Extraherar Pauli-strängen och dess qubit-index för en Pauli-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="0a06d-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="0a06d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0a06d-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="0a06d-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0a06d-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0a06d-108">`GeneratorIndex` typ som kodar en Pauli-term.</span><span class="sxs-lookup"><span data-stu-id="0a06d-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="0a06d-109">Utdata: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="0a06d-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="0a06d-110">Pauli-strängen för den term som beskrivs av a `GeneratorIndex` , och index för den qubits som den agerar på.</span><span class="sxs-lookup"><span data-stu-id="0a06d-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>