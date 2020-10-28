---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Funktionen FeatureRegisterSize
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732811"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="6a900-102">Funktionen FeatureRegisterSize</span><span class="sxs-lookup"><span data-stu-id="6a900-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="6a900-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6a900-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6a900-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a900-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a900-105">Returnerar antalet qubits som krävs för att koda en viss funktions vektor.</span><span class="sxs-lookup"><span data-stu-id="6a900-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="6a900-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6a900-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="6a900-107">exempel: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6a900-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6a900-108">En exempel funktions vektor som ska kodas till ett qubit-register.</span><span class="sxs-lookup"><span data-stu-id="6a900-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="6a900-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a900-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a900-110">Storleken som krävs för att koda `sample` till ett qubit-register, uttryckt som ett antal qubits.</span><span class="sxs-lookup"><span data-stu-id="6a900-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>