---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: Funktionen CombinedStructure
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211975"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="a38f3-102">Funktionen CombinedStructure</span><span class="sxs-lookup"><span data-stu-id="a38f3-102">CombinedStructure function</span></span>

<span data-ttu-id="a38f3-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a38f3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a38f3-104">Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a38f3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a38f3-105">Med en eller flera lager av kontrollerade rotationer, returnerar ett enskilt lager med modell parameter indexet Skift ATS, så att distinkta skikt är parameterstyrda av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="a38f3-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="a38f3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a38f3-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="a38f3-107">lager: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="a38f3-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="a38f3-108">De lager som ska kombineras.</span><span class="sxs-lookup"><span data-stu-id="a38f3-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="a38f3-109">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="a38f3-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="a38f3-110">Ett enda lager med kontrollerade rotationer som representerar sammanfogningen av alla andra lager.</span><span class="sxs-lookup"><span data-stu-id="a38f3-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>