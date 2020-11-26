---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Funktionen WeightOnePaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204546"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="98993-102">Funktionen WeightOnePaulis</span><span class="sxs-lookup"><span data-stu-id="98993-102">WeightOnePaulis function</span></span>

<span data-ttu-id="98993-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98993-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98993-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98993-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98993-105">Returnerar en matris med alla vikt-1 Pauli-operatorer för ett angivet antal qubits.</span><span class="sxs-lookup"><span data-stu-id="98993-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="98993-106">Indata</span><span class="sxs-lookup"><span data-stu-id="98993-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="98993-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98993-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98993-108">Antalet qubits som de returnerade Pauli-operatörerna har definierats på.</span><span class="sxs-lookup"><span data-stu-id="98993-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="98993-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="98993-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="98993-110">En matris med multi-qubit Pauli-operatorer, som var och en visas som en matris med längd `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="98993-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>