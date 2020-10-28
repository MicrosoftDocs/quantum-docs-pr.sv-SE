---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: Funktionen PauliStringFromGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726289"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="5e87e-102">Funktionen PauliStringFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="5e87e-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="5e87e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5e87e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5e87e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e87e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e87e-105">Extraherar Pauli-strängen och dess qubit-index för en Pauli-term som beskrivs av en `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="5e87e-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="5e87e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5e87e-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="5e87e-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5e87e-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5e87e-108">`GeneratorIndex` typ som kodar en Pauli-term.</span><span class="sxs-lookup"><span data-stu-id="5e87e-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="5e87e-109">Utdata: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="5e87e-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="5e87e-110">Pauli-strängen för den term som beskrivs av a `GeneratorIndex` , och index för den qubits som den agerar på.</span><span class="sxs-lookup"><span data-stu-id="5e87e-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>