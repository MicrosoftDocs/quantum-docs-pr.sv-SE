---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190742"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="3fb8c-102">ApplyMajorityInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3fb8c-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="3fb8c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3fb8c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3fb8c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fb8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fb8c-105">Tillämpar den tre qubit majoritets åtgärden på plats i ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3fb8c-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3fb8c-106">Description</span></span>

<span data-ttu-id="3fb8c-107">Den här åtgärden beräknar majoriteten av funktionerna på plats på 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="3fb8c-108">Om vi betecknar utdata qubit som $z $ och indata-qubits som $x $ och $y $, utför åtgärden följande omvandling: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="3fb8c-109">Indata</span><span class="sxs-lookup"><span data-stu-id="3fb8c-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="3fb8c-110">utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3fb8c-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3fb8c-111">Qubit för första indatamängden.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-111">First input qubit.</span></span> <span data-ttu-id="3fb8c-112">Observera att utdata beräknas på plats och lagras i den här qubit.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="3fb8c-113">inmatade: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3fb8c-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3fb8c-114">Andra och tredje qubits för indatamängden.</span><span class="sxs-lookup"><span data-stu-id="3fb8c-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3fb8c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fb8c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

