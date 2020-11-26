---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196420"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="737d4-102">Funktionen FeatureRegisterSize</span><span class="sxs-lookup"><span data-stu-id="737d4-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="737d4-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="737d4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="737d4-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="737d4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="737d4-105">Returnerar antalet qubits som krävs för att koda en viss funktions vektor.</span><span class="sxs-lookup"><span data-stu-id="737d4-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="737d4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="737d4-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="737d4-107">exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="737d4-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="737d4-108">En exempel funktions vektor som ska kodas till ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="737d4-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="737d4-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="737d4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="737d4-110">Storleken som krävs för att koda `sample` till ett qubit-register, uttryckt som ett antal qubits.</span><span class="sxs-lookup"><span data-stu-id="737d4-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>