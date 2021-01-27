---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: dbbbb2b67dcf191c74e593f61eb894192acb4d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854718"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a>TimeDependentGeneratorSystem-användardefinierad typ

Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representerar en tids beroende dynamisk generator som en funktion från tiden till värdet för den dynamiska generatorn vid den tidpunkten.

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

