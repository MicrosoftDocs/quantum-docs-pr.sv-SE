---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848432"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="3a02b-102">Funktionen FeatureRegisterSize</span><span class="sxs-lookup"><span data-stu-id="3a02b-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="3a02b-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3a02b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3a02b-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3a02b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3a02b-105">Returnerar antalet qubits som krävs för att koda en viss funktions vektor.</span><span class="sxs-lookup"><span data-stu-id="3a02b-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="3a02b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3a02b-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="3a02b-107">exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3a02b-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3a02b-108">En exempel funktions vektor som ska kodas till ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="3a02b-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="3a02b-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a02b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a02b-110">Storleken som krävs för att koda `sample` till ett qubit-register, uttryckt som ett antal qubits.</span><span class="sxs-lookup"><span data-stu-id="3a02b-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>