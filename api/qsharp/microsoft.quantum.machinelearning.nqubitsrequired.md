---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: Funktionen NQubitsRequired
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732974"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="e1925-102">Funktionen NQubitsRequired</span><span class="sxs-lookup"><span data-stu-id="e1925-102">NQubitsRequired function</span></span>

<span data-ttu-id="e1925-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e1925-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e1925-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1925-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1925-105">Returnerar antalet qubits som krävs för att tillämpa en viss sekventiell klassificerare.</span><span class="sxs-lookup"><span data-stu-id="e1925-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="e1925-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e1925-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="e1925-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="e1925-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="e1925-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1925-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1925-109">Minimi storleken på ett register där den sekventiella klassificeraren kan tillämpas.</span><span class="sxs-lookup"><span data-stu-id="e1925-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>