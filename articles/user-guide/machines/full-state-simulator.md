---
title: Fullständig tillstånds Simulator
description: 'Lär dig hur du kör dina Q #-program i Microsoft Quantum Development Kit fullständig tillstånds Simulator.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275646"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum Development Kit full State Simulator

Quantum Development Kit innehåller en fullständigt tillstånd Quantum simulator som liknar [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) från Microsoft Research.
Den här simulatorn kan användas för att köra och felsöka Quantum-algoritmer skrivna i Q # på din dator.

Den här Quantum simulatorn exponeras via `QuantumSimulator` klassen. Om du vill använda simulatorn skapar du bara en instans av den här klassen och skickar den till `Run` metoden för den Quantum-åtgärd som du vill köra tillsammans med resten av parametrarna:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator`Klassen implementerar <xref:System.IDisposable> , vilket innebär att `Dispose` metoden ska anropas när instansen av simulatorn inte används längre. Det bästa sättet att göra detta är att figursätta simulatorn i en `using` instruktion, som i exemplet ovan.

## <a name="seed"></a>Dirigeringsrouter

`QuantumSimulator`Använder en slump tals generator för att simulera Quantum-slumpmässig het. I test syfte är det ibland användbart att ha deterministiska resultat. Detta kan åstadkommas genom att tillhandahålla ett start värde för slump tals generatorn i `QuantumSimulator` konstruktorn via `randomNumberGeneratorSeed` parametern:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Konversation

`QuantumSimulator` [OpenMP](http://www.openmp.org/) används för att parallellisera de linjära algebra som krävs. Som standard använder OpenMP alla tillgängliga maskinvarutrådar, vilket innebär att program med små antal kvantbitar ofta körs långsamt eftersom den samordning som krävs vida överstiger det faktiska arbetet. Detta kan åtgärdas genom att ställa in miljövariabeln `OMP_NUM_THREADS` på ett litet tal. Som en mycket generell tumregel räcker 1 tråd för upp till cirka 4 kvantbitar, och därefter kan ytterligare en tråd införas per kvantbit. Detta beror dock starkt på din algoritm.

