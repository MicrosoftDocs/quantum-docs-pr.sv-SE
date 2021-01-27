---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843477"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="35328-102">ApplyXorInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="35328-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="35328-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="35328-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="35328-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35328-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35328-105">Tillämpar en Bitvis-XOR-åtgärd mellan ett klassiskt heltal och ett heltal som representeras av ett register av qubits.</span><span class="sxs-lookup"><span data-stu-id="35328-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="35328-106">Description</span><span class="sxs-lookup"><span data-stu-id="35328-106">Description</span></span>

<span data-ttu-id="35328-107">Tillämpar `X` åtgärder på qubits i ett litet endian-register baserat på 1 bitar i ett heltal.</span><span class="sxs-lookup"><span data-stu-id="35328-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="35328-108">Låt oss ange `value` ett och låt y vara ett osignerat heltal som är kodat i `target` och `InPlaceXorLE` utför sedan en åtgärd som anges av följande karta: $ \ket{y}\rightarrow \ket{y\oplus a} $, där $ \oplus $ är den bitvisa eller operatorn.</span><span class="sxs-lookup"><span data-stu-id="35328-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="35328-109">Indata</span><span class="sxs-lookup"><span data-stu-id="35328-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="35328-110">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35328-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35328-111">Ett heltal som antas vara icke-negativt.</span><span class="sxs-lookup"><span data-stu-id="35328-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="35328-112">mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="35328-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="35328-113">Ett Quantum-register som används för att lagra `value` i lite endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="35328-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35328-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35328-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

