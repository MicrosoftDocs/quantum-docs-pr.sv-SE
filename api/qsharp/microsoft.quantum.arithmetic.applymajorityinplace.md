---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731835"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="0cfda-102">ApplyMajorityInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0cfda-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="0cfda-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0cfda-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0cfda-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0cfda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0cfda-105">Tillämpar den tre qubit majoritets åtgärden på plats i ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="0cfda-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0cfda-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0cfda-106">Description</span></span>

<span data-ttu-id="0cfda-107">Den här åtgärden beräknar majoriteten av funktionerna på plats på 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="0cfda-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="0cfda-108">Om vi betecknar utdata qubit som $z $ och indata-qubits som $x $ och $y $, utför åtgärden följande omvandling: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="0cfda-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="0cfda-109">Indata</span><span class="sxs-lookup"><span data-stu-id="0cfda-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="0cfda-110">utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0cfda-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0cfda-111">Qubit för första indatamängden.</span><span class="sxs-lookup"><span data-stu-id="0cfda-111">First input qubit.</span></span> <span data-ttu-id="0cfda-112">Observera att utdata beräknas på plats och lagras i den här qubit.</span><span class="sxs-lookup"><span data-stu-id="0cfda-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="0cfda-113">inmatade: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0cfda-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0cfda-114">Andra och tredje qubits för indatamängden.</span><span class="sxs-lookup"><span data-stu-id="0cfda-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cfda-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cfda-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

