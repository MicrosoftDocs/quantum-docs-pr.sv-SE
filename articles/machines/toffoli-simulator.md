---
title: Quantum Development Kit Toffoli-Simulator | Microsoft Docs
description: Översikt över Microsofts Toffoli-Simulator för Quantum Development Kit
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442352"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Quantum Development Kit Toffoli-Simulator

Quantum Development Kit tillhandahåller en Toffoli-simulator, som är en särskild simulator som kan simulera Quantum-algoritmer som är begränsade till X-, CNOT-och multi-styrda X-Quantum-åtgärder (all klassisk logik och beräkningar är tillgängliga).

Även om Toffoli-simulatorn är mycket mer begränsad i drift än [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator)kan den simulera mycket mer qubits.
Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är allmänt begränsad till cirka 30.
Den kan köra och felsöka en begränsad uppsättning Quantum-algoritmer skrivna i Q # på din dator. till exempel kan Oracle som utvärderar booleska funktioner implementeras med hjälp av dessa portar och testas på olika qubits med den här simulatorn.

Den här Quantum simulatorn exponeras via `ToffoliSimulator`-klassen.
Om du vill använda simulatorn skapar du bara en instans av den här klassen och skickar den till `Run`-metoden för den Quantum-åtgärd som du vill köra tillsammans med resten av parametrarna:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Andra åtgärder

`ToffoliSimulator` stöder rotationer och exponentiated Paulis, till exempel `R` och `Exp`när den resulterande åtgärden är lika med `X` eller identiteten.

Mätning och assert stöds, men endast i Pauli `Z`.
Observera att sannolikheten för viss mätning alltid är 0 eller 1; Det finns ingen slumpmässighet i Toffoli-simulatorn.

`DumpMachine` och `DumpRegister` stöds.
Båda utvärderar den aktuella `Z`-basis för varje qubit, en qubit per rad.

## <a name="qubitcount"></a>QubitCount

Som standard allokerar `ToffoliSimulator` utrymme för 65 536 qubits.
Om algoritmen kräver mer än så kan du ändra antalet qubit genom att ange ett värde för parametern `qubitCount` till konstruktorn.
För varje ytterligare qubit krävs ytterligare byte av minne, så det finns ingen betydande kostnad för att uppskatta antalet qubits som du behöver.

Exempel:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
