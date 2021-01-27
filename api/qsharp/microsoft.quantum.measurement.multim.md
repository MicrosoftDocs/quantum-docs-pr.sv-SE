---
uid: Microsoft.Quantum.Measurement.MultiM
title: Multiin-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857002"
---
# <a name="multim-operation"></a><span data-ttu-id="3b457-102">Multiin-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3b457-102">MultiM operation</span></span>

<span data-ttu-id="3b457-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3b457-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3b457-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b457-105">Mäter varje qubit i en specifik matris enligt standard-basen.</span><span class="sxs-lookup"><span data-stu-id="3b457-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="3b457-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3b457-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="3b457-107">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3b457-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3b457-108">En matris med qubits som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="3b457-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3b457-109">Utdata: __ogiltigt <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="3b457-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="3b457-110">En matris med mått resultat.</span><span class="sxs-lookup"><span data-stu-id="3b457-110">An array of measurement results.</span></span>