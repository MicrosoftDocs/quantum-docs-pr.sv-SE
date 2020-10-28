---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: Funktionen CombinedStructure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731115"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="2fe43-102">Funktionen CombinedStructure</span><span class="sxs-lookup"><span data-stu-id="2fe43-102">CombinedStructure function</span></span>

<span data-ttu-id="2fe43-103">Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2fe43-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2fe43-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fe43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fe43-105">Med en eller flera lager av kontrollerade rotationer, returnerar ett enskilt lager med modell parameter indexet Skift ATS, så att distinkta skikt är parameterstyrda av distinkta modell parametrar.</span><span class="sxs-lookup"><span data-stu-id="2fe43-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="2fe43-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2fe43-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="2fe43-107">lager: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="2fe43-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="2fe43-108">De lager som ska kombineras.</span><span class="sxs-lookup"><span data-stu-id="2fe43-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="2fe43-109">Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="2fe43-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="2fe43-110">Ett enda lager med kontrollerade rotationer som representerar sammanfogningen av alla andra lager.</span><span class="sxs-lookup"><span data-stu-id="2fe43-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>