---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731699"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="42f7a-102">ApplyXorInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="42f7a-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="42f7a-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="42f7a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="42f7a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42f7a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42f7a-105">Tillämpar en Bitvis-XOR-åtgärd mellan ett klassiskt heltal och ett heltal som representeras av ett register av qubits.</span><span class="sxs-lookup"><span data-stu-id="42f7a-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="42f7a-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="42f7a-106">Description</span></span>

<span data-ttu-id="42f7a-107">Tillämpar `X` åtgärder på qubits i ett litet endian-register baserat på 1 bitar i ett heltal.</span><span class="sxs-lookup"><span data-stu-id="42f7a-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="42f7a-108">Låt oss ange `value` ett och låt y vara ett osignerat heltal som är kodat i `target` och `InPlaceXorLE` utför sedan en åtgärd som anges av följande karta: $ \ket{y}\rightarrow \ket{y\oplus a} $, där $ \oplus $ är den bitvisa eller operatorn.</span><span class="sxs-lookup"><span data-stu-id="42f7a-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="42f7a-109">Indata</span><span class="sxs-lookup"><span data-stu-id="42f7a-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="42f7a-110">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="42f7a-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="42f7a-111">Ett heltal som antas vara icke-negativt.</span><span class="sxs-lookup"><span data-stu-id="42f7a-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="42f7a-112">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="42f7a-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="42f7a-113">Ett Quantum-register som används för att lagra `value` i lite endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="42f7a-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42f7a-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42f7a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

