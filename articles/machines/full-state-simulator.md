---
title: Quantum Development Kit full State Simulator | Microsoft Docs
description: Översikt över Microsofts Quantum Development Kit full State Simulator
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184686"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Quantum Development Kit full State Simulator

Quantum Development Kit innehåller en fullständigt tillstånd Quantum simulator som liknar [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) från Microsoft Research.
Den här simulatorn kan användas för att köra och felsöka Quantum-algoritmer skrivna i Q # på din dator.

Den här Quantum simulatorn exponeras via `QuantumSimulator`-klassen. Om du vill använda simulatorn skapar du bara en instans av den här klassen och skickar den till `Run`-metoden för den Quantum-åtgärd som du vill köra tillsammans med resten av parametrarna:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator`-klassen implementerar <xref:System.IDisposable>, så `Dispose`-metoden ska anropas när instansen av simulatorn inte används längre. Det bästa sättet att göra detta är att omsluta simulatorn i en `using`-instruktion, som i exemplet ovan.

## <a name="seed"></a>Dirigeringsrouter

`QuantumSimulator` använder en slump tals generator för att simulera Quantum-slumpmässig het. I test syfte är det ibland användbart att ha deterministiska resultat. Detta kan åstadkommas genom att tillhandahålla ett start värde för slump tals generatorn i `QuantumSimulator`s konstruktorn via `randomNumberGeneratorSeed` parameter:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Konversation

`QuantumSimulator` använder [OpenMP](http://www.openmp.org/) för att parallellisera de linjära algebra som krävs. Som standard använder OpenMP alla tillgängliga maskin varu trådar, vilket innebär att program med små mängder qubits ofta kommer att köras långsamt, eftersom den samordning som krävs kommer att Dwarf det faktiska arbetet. Detta kan åtgärdas genom att ställa in miljövariabeln `OMP_NUM_THREADS` till ett litet tal. En mycket bra tumregel är att 1 tråd är bra för upp till ungefär 4 qubits och en ytterligare tråd per qubit är bra, även om det är mycket beroende av algoritmen.

