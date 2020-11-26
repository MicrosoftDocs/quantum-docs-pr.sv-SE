---
uid: Microsoft.Quantum.Measurement.MultiM
title: Multiin-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227003"
---
# <a name="multim-operation"></a><span data-ttu-id="0cfa6-102">Multiin-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0cfa6-102">MultiM operation</span></span>

<span data-ttu-id="0cfa6-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="0cfa6-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="0cfa6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cfa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cfa6-105">Mäter varje qubit i en specifik matris enligt standard-basen.</span><span class="sxs-lookup"><span data-stu-id="0cfa6-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="0cfa6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0cfa6-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="0cfa6-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0cfa6-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0cfa6-108">En matris med qubits som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="0cfa6-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0cfa6-109">Utdata: __ogiltigt <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="0cfa6-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="0cfa6-110">En matris med mått resultat.</span><span class="sxs-lookup"><span data-stu-id="0cfa6-110">An array of measurement results.</span></span>