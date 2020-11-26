---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196182"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="7643a-102">SequentialModel-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="7643a-102">SequentialModel user defined type</span></span>

<span data-ttu-id="7643a-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7643a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7643a-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7643a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7643a-105">Beskriver en Quantum klassificerare-modell som består av en sekvens av parameterstyrda och kontrollerade rotationer, en tilldelning av rotations vinklar och en förskjutning mellan de två klasserna som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="7643a-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="7643a-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="7643a-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="7643a-107">Struktur: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="7643a-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="7643a-108">Sekvensen med kontrollerade rotationer som används för att klassificera indata.</span><span class="sxs-lookup"><span data-stu-id="7643a-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="7643a-109">Parametrar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7643a-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7643a-110">En tilldelning av rotations vinklar till den aktuella klassificerings strukturen.</span><span class="sxs-lookup"><span data-stu-id="7643a-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="7643a-111">Bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7643a-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7643a-112">Förskjutningen mellan de två klasserna som känns igen av denna klassificerare.</span><span class="sxs-lookup"><span data-stu-id="7643a-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="7643a-113">Referenser</span><span class="sxs-lookup"><span data-stu-id="7643a-113">References</span></span>

- [<span data-ttu-id="7643a-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="7643a-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)