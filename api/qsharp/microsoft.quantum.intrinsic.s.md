---
uid: Microsoft.Quantum.Intrinsic.S
title: S-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198460"
---
# <a name="s-operation"></a><span data-ttu-id="d37c6-102">S-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d37c6-102">S operation</span></span>

<span data-ttu-id="d37c6-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d37c6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d37c6-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d37c6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d37c6-105">Tillämpar S-porten på en enda qubit.</span><span class="sxs-lookup"><span data-stu-id="d37c6-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d37c6-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d37c6-106">Description</span></span>

<span data-ttu-id="d37c6-107">Den här åtgärden kan simuleras av den enhetliga matrisen \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="d37c6-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="d37c6-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="d37c6-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="d37c6-109">Indata</span><span class="sxs-lookup"><span data-stu-id="d37c6-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="d37c6-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d37c6-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d37c6-111">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="d37c6-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d37c6-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d37c6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

