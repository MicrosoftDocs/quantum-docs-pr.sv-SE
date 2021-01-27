---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854899"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="f84cc-102">SequentialModel-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="f84cc-102">SequentialModel user defined type</span></span>

<span data-ttu-id="f84cc-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f84cc-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f84cc-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f84cc-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f84cc-105">Beskriver en Quantum klassificerare-modell som består av en sekvens av parameterstyrda och kontrollerade rotationer, en tilldelning av rotations vinklar och en förskjutning mellan de två klasserna som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="f84cc-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="f84cc-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="f84cc-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="f84cc-107">Struktur: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="f84cc-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="f84cc-108">Sekvensen med kontrollerade rotationer som används för att klassificera indata.</span><span class="sxs-lookup"><span data-stu-id="f84cc-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="f84cc-109">Parametrar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f84cc-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f84cc-110">En tilldelning av rotations vinklar till den aktuella klassificerings strukturen.</span><span class="sxs-lookup"><span data-stu-id="f84cc-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="f84cc-111">Bias: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f84cc-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f84cc-112">Förskjutningen mellan de två klasserna som känns igen av denna klassificerare.</span><span class="sxs-lookup"><span data-stu-id="f84cc-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="f84cc-113">Referenser</span><span class="sxs-lookup"><span data-stu-id="f84cc-113">References</span></span>

- [<span data-ttu-id="f84cc-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="f84cc-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)