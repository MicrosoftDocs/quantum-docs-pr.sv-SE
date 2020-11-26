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
# <a name="combinedstructure-function"></a>Funktionen CombinedStructure

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Med en eller flera lager av kontrollerade rotationer, returnerar ett enskilt lager med modell parameter indexet Skift ATS, så att distinkta skikt är parameterstyrda av distinkta modell parametrar.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Indata

### <a name="layers--controlledrotation"></a>lager: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

De lager som ska kombineras.



## <a name="output--controlledrotation"></a>Utdata: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Ett enda lager med kontrollerade rotationer som representerar sammanfogningen av alla andra lager.