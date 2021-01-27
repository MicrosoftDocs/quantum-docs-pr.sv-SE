---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843731"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="13da0-102">ApplyMajorityInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="13da0-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="13da0-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="13da0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="13da0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13da0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13da0-105">Tillämpar den tre qubit majoritets åtgärden på plats i ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="13da0-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="13da0-106">Description</span><span class="sxs-lookup"><span data-stu-id="13da0-106">Description</span></span>

<span data-ttu-id="13da0-107">Den här åtgärden beräknar majoriteten av funktionerna på plats på 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="13da0-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="13da0-108">Om vi betecknar utdata qubit som $z $ och indata-qubits som $x $ och $y $, utför åtgärden följande omvandling: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="13da0-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="13da0-109">Indata</span><span class="sxs-lookup"><span data-stu-id="13da0-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="13da0-110">utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="13da0-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="13da0-111">Qubit för första indatamängden.</span><span class="sxs-lookup"><span data-stu-id="13da0-111">First input qubit.</span></span> <span data-ttu-id="13da0-112">Observera att utdata beräknas på plats och lagras i den här qubit.</span><span class="sxs-lookup"><span data-stu-id="13da0-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="13da0-113">inmatade: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13da0-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="13da0-114">Andra och tredje qubits för indatamängden.</span><span class="sxs-lookup"><span data-stu-id="13da0-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13da0-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13da0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

