---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: Funktionen NQubitsRequired
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854971"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="12115-102">Funktionen NQubitsRequired</span><span class="sxs-lookup"><span data-stu-id="12115-102">NQubitsRequired function</span></span>

<span data-ttu-id="12115-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12115-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="12115-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12115-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="12115-105">Returnerar antalet qubits som krävs för att tillämpa en viss sekventiell klassificerare.</span><span class="sxs-lookup"><span data-stu-id="12115-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="12115-106">Indata</span><span class="sxs-lookup"><span data-stu-id="12115-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="12115-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="12115-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="12115-108">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12115-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12115-109">Minimi storleken på ett register där den sekventiella klassificeraren kan tillämpas.</span><span class="sxs-lookup"><span data-stu-id="12115-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>