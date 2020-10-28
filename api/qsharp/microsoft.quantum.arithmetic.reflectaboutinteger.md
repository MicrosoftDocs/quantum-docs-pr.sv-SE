---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730579"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="96b45-102">ReflectAboutInteger-åtgärd</span><span class="sxs-lookup"><span data-stu-id="96b45-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="96b45-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="96b45-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="96b45-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96b45-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96b45-105">Visar ett Quantum-register om ett angivet klassiskt heltal.</span><span class="sxs-lookup"><span data-stu-id="96b45-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="96b45-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="96b45-106">Description</span></span>

<span data-ttu-id="96b45-107">Med ett Quantum-register inlednings vis i status $ \ sum_i \ alpha_i \ket{i} $, där varje $ \ket{i} $ är ett bas tillstånd som representerar ett heltal $i $, visar status för registret om grund tillstånd för ett angivet heltal $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="96b45-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="96b45-108">Indata</span><span class="sxs-lookup"><span data-stu-id="96b45-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="96b45-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96b45-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96b45-110">Det klassiska heltalet som indexerar det grundläggande tillstånd som ska reflekteras.</span><span class="sxs-lookup"><span data-stu-id="96b45-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="96b45-111">REG: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96b45-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="96b45-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96b45-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="96b45-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="96b45-113">Remarks</span></span>

<span data-ttu-id="96b45-114">Den här åtgärden implementeras på plats utan explicit allokering av ytterligare hjälp-qubits.</span><span class="sxs-lookup"><span data-stu-id="96b45-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>