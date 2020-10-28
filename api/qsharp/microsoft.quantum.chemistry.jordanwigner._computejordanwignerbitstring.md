---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728071"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="ca7f6-102">_ComputeJordanWignerBitString funktion</span><span class="sxs-lookup"><span data-stu-id="ca7f6-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="ca7f6-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ca7f6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ca7f6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca7f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca7f6-105">Beräknar Z-komponenten i Jordanien – Wigner sträng mellan fermion-index i en fermionic-operator med ett jämnt antal skapande/Annihilation-operatörer.</span><span class="sxs-lookup"><span data-stu-id="ca7f6-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="ca7f6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ca7f6-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="ca7f6-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ca7f6-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ca7f6-108">Antalet Fermions i systemet.</span><span class="sxs-lookup"><span data-stu-id="ca7f6-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="ca7f6-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ca7f6-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ca7f6-110">fermionic operatörs index.</span><span class="sxs-lookup"><span data-stu-id="ca7f6-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ca7f6-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ca7f6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ca7f6-112">Bitstring `Bool[]` `true` där a `PauliZ` ska användas.</span><span class="sxs-lookup"><span data-stu-id="ca7f6-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>