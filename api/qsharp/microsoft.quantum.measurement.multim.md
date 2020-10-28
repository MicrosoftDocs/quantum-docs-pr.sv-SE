---
uid: Microsoft.Quantum.Measurement.MultiM
title: Multiin-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726502"
---
# <a name="multim-operation"></a><span data-ttu-id="e643b-102">Multiin-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e643b-102">MultiM operation</span></span>

<span data-ttu-id="e643b-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e643b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e643b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e643b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e643b-105">Mäter varje qubit i en specifik matris enligt standard-basen.</span><span class="sxs-lookup"><span data-stu-id="e643b-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="e643b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e643b-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="e643b-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e643b-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e643b-108">En matris med qubits som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="e643b-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e643b-109">Utdata: __ogiltigt <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="e643b-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="e643b-110">En matris med mått resultat.</span><span class="sxs-lookup"><span data-stu-id="e643b-110">An array of measurement results.</span></span>