---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203951"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="8ff40-102">_ComputeJordanWignerBitString funktion</span><span class="sxs-lookup"><span data-stu-id="8ff40-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="8ff40-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="8ff40-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="8ff40-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8ff40-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8ff40-105">Beräknar Z-komponenten i Jordanien – Wigner sträng mellan fermion-index i en fermionic-operator med ett jämnt antal skapande/Annihilation-operatörer.</span><span class="sxs-lookup"><span data-stu-id="8ff40-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="8ff40-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8ff40-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="8ff40-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ff40-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ff40-108">Antalet Fermions i systemet.</span><span class="sxs-lookup"><span data-stu-id="8ff40-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="8ff40-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8ff40-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8ff40-110">fermionic operatörs index.</span><span class="sxs-lookup"><span data-stu-id="8ff40-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8ff40-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="8ff40-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="8ff40-112">Bitstring `Bool[]` `true` där a `PauliZ` ska användas.</span><span class="sxs-lookup"><span data-stu-id="8ff40-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>