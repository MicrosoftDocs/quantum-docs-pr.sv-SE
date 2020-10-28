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
# <a name="combinedstructure-function"></a>Funktionen CombinedStructure

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


Med en eller flera lager av kontrollerade rotationer, returnerar ett enskilt lager med modell parameter indexet Skift ATS, så att distinkta skikt är parameterstyrda av distinkta modell parametrar.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Indata

### <a name="layers--controlledrotation"></a>lager: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

De lager som ska kombineras.



## <a name="output--controlledrotation"></a>Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Ett enda lager med kontrollerade rotationer som representerar sammanfogningen av alla andra lager.