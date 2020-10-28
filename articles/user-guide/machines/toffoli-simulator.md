---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Lär dig mer om Microsoft QDKe Toffoli simulator, en speciell funktion Quantum simulator som kan användas med miljon tals qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690788"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Toffoli Simulator för Quantum Development Kit (QDK)

QDK Toffoli-simulatorn är en särskild simulator med en begränsad omfattning och stöder bara `X` , `CNOT` och flera kontrollerade `X` Quantum-åtgärder. All klassisk logik och alla beräkningar är tillgängliga.

Även om Toffoli-simulatorn är mer begränsad i funktionalitet än med [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), har den fördelen att kunna simulera mycket mer qubits. Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är begränsad till cirka 30 qubits. Detta är användbart, till exempel med Oracle som utvärderar booleska funktioner – de kan implementeras med den begränsade uppsättningen algoritmer som stöds och testas på ett stort antal qubits.

## <a name="invoking-the-toffoli-simulator"></a>Anropar Toffoli-simulatorn

Du exponerar Toffoli-simulatorn via- `ToffoliSimulator` klassen. Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Anropar Toffoli-simulatorn från C #

Precis som med andra måldatorer skapar du först en instans av klassen `ToffoliSimulator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.

Observera att i motsats till `QuantumSimulator`-klassen implementerar `ToffoliSimulator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Anropar Toffoli-simulatorn från python

Använd metoden [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q# åtgärden:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Anropar Toffoli-simulatorn från kommando raden

När du kör ett Q# program från kommando raden använder du parametern **--simulatorn** (eller **-s** ) för att ange mål datorn för Toffoli Simulator. Följande kommando kör ett program med hjälp av resurs uppskattningen: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Anropar Toffoli-simulatorn från Juptyer Notebooks

Använd Q# kommandot Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) för att köra Q# åtgärden.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Åtgärder som stöds

Toffoli Simulator stöder:

* Rotationer och exponentiated Paulis, till exempel `R` och `Exp` , när den resulterande åtgärden är lika med `X` eller identitets mat ris.
* Mått och [assert](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) -åtgärder, men endast i Pauli- `Z` basen. Observera att sannolikheten för en mått åtgärd alltid är **0** eller **1** ; Det finns ingen slumpmässighet i Toffoli-simulatorn.
* `DumpMachine` och- `DumpRegister` funktioner.
Båda funktionerna utvärderar aktuell `Z` bas status för varje qubit, en qubit per rad.

## <a name="specifying-the-number-of-qubits"></a>Ange antalet qubits

Som standard `ToffoliSimulator` allokerar en instans utrymme för 65 536 qubits.
Om algoritmen kräver mer qubits kan du ange antalet qubit genom att ange ett värde för `qubitCount` parametern för konstruktorn.
För varje ytterligare qubit krävs bara en byte av minne, så det finns ingen betydande kostnad för att uppskatta antalet qubits som du behöver.

Exempel:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Se även

- [Uppskattning av Quantum-resurser](xref:microsoft.quantum.machines.resources-estimator)
- [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Quantum, fullständig tillstånds Simulator](xref:microsoft.quantum.machines.full-state-simulator) 