---
title: Quantum Toffoli Simulator – Quantum Development Kit
description: Lär dig mer om Microsoft QDKe Toffoli simulator, en speciell funktion Quantum simulator som kan användas med miljon tals qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870625"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Toffoli Simulator för Quantum Development Kit (QDK)

QDK Toffoli-simulatorn är en särskild simulator med en begränsad omfattning och stöder bara `X` , `CNOT` och flera kontrollerade `X` Quantum-åtgärder. All klassisk logik och alla beräkningar är tillgängliga.

Även om Toffoli-simulatorn är mer begränsad i funktionalitet än med [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), har den fördelen att kunna simulera mycket mer qubits. Toffoli-simulatorn kan användas med miljon tals qubits, medan hela tillstånds simulatorn är begränsad till cirka 30 qubits. Detta är användbart, till exempel med Oracle som utvärderar booleska funktioner – de kan implementeras med den begränsade uppsättningen algoritmer som stöds och testas på ett stort antal qubits.

## <a name="invoking-the-toffoli-simulator"></a>Anropar Toffoli-simulatorn

Du exponerar Toffoli-simulatorn via- `ToffoliSimulator` klassen. Mer information finns i [sätt att köra ett Q #-program](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Anropar Toffoli-simulatorn från C #

Precis som med andra mål datorer skapar du först en instans av `ToffoliSimulator` klassen och skickar den som den första parametern för en åtgärds `Run` metod.

Observera att om klassen till skillnad från `QuantumSimulator` klassen `ToffoliSimulator` implementerar inte <xref:System.IDisposable> gränssnittet, och därför behöver du inte ange det i en `using` instruktion.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Anropar Toffoli-simulatorn från python

Använd metoden [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q #-åtgärden:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Anropar Toffoli-simulatorn från kommando raden

När du kör ett Q #-program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange Toffoli Simulator mål dator. Följande kommando kör ett program med hjälp av resurs uppskattningen: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Anropar Toffoli-simulatorn från Juptyer Notebooks

Använd SWEETIQ # Magic kommandot [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) för att köra Q #-åtgärden.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Åtgärder som stöds

Toffoli Simulator stöder:

* Rotationer och exponentiated Paulis, till exempel `R` och `Exp` , när den resulterande åtgärden är lika med `X` eller identitets mat ris.
* Mått och [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) -åtgärder, men endast i Pauli- `Z` basen. Observera att sannolikheten för en mått åtgärd alltid är **0** eller **1**; Det finns ingen slumpmässighet i Toffoli-simulatorn.
* `DumpMachine`och- `DumpRegister` funktioner.
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