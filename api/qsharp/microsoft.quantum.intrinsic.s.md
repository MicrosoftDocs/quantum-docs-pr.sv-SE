---
uid: Microsoft.Quantum.Intrinsic.S
title: S-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: 8a57c60ac1df8f6e94b58acf7183c47f395d291a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732446"
---
# <a name="s-operation"></a><span data-ttu-id="338b4-102">S-åtgärd</span><span class="sxs-lookup"><span data-stu-id="338b4-102">S operation</span></span>

<span data-ttu-id="338b4-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="338b4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="338b4-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="338b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="338b4-105">Tillämpar S-porten på en enda qubit.</span><span class="sxs-lookup"><span data-stu-id="338b4-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="338b4-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="338b4-106">Description</span></span>

<span data-ttu-id="338b4-107">Den här åtgärden kan simuleras av den enhetliga matrisen \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="338b4-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="338b4-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="338b4-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="338b4-109">Indata</span><span class="sxs-lookup"><span data-stu-id="338b4-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="338b4-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="338b4-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="338b4-111">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="338b4-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="338b4-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="338b4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

