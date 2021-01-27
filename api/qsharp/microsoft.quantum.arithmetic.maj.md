---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846554"
---
# <a name="maj-operation"></a><span data-ttu-id="de21c-102">MAJ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="de21c-102">MAJ operation</span></span>

<span data-ttu-id="de21c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de21c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de21c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de21c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de21c-105">På så sätt tillämpas majoriteten på plats till 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="de21c-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="de21c-106">Description</span><span class="sxs-lookup"><span data-stu-id="de21c-106">Description</span></span>

<span data-ttu-id="de21c-107">Om vi anger tillståndet för mål-qubit som $ \ket{z} $ och indataportarna i Indataporten för qubits som $ \ket{x} $ och $ \ket{y} $, utför den här åtgärden följande omvandling: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="de21c-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="de21c-108">Indata</span><span class="sxs-lookup"><span data-stu-id="de21c-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="de21c-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="de21c-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="de21c-110">Den första qubit.</span><span class="sxs-lookup"><span data-stu-id="de21c-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="de21c-111">INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="de21c-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="de21c-112">Andra qubit för indatamängden.</span><span class="sxs-lookup"><span data-stu-id="de21c-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="de21c-113">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="de21c-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="de21c-114">En qubit som majoriteten av funktionen ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="de21c-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de21c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de21c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

