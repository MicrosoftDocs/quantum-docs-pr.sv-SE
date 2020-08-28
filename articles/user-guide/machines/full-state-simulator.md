---
title: Fullständigt tillstånd Quantum Simulator – Quantum Development Kit
description: Lär dig hur du kör dina Q# program på Microsoft Quantum Development Kit fullständiga tillstånds simulatorn.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992231"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Quantum Development Kit (QDK) fullständig tillstånds Simulator

QDK tillhandahåller en fullständig tillstånds simulator som simulerar en Quantum-dator på din lokala dator. Du kan använda den fullständiga tillstånds simulatorn för att köra och felsöka Quantum-algoritmer som skrivits i Q# , med upp till 30 qubits. Den fullständiga tillstånds simulatorn liknar den Quantum simulator som används i  [LIQ $ UI | \rangle $](http://stationq.github.io/Liquid/) Platform från Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Anropa och köra fullständig tillstånds Simulator

Du exponerar hela tillstånds simulatorn via- `QuantumSimulator` klassen. Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Anropa simulatorn från C #

Skapa en instans av `QuantumSimulator` klassen och skicka den sedan till `Run` metoden för en Quantum-åtgärd, tillsammans med eventuella ytterligare parametrar.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Eftersom `QuantumSimulator` klassen implementerar <xref:System.IDisposable> gränssnittet måste du anropa `Dispose` metoden när du inte behöver instansen av simulatorn längre. Det bästa sättet att göra detta är att omsluta Simulator deklarationen och åtgärderna i en [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) -instruktion som automatiskt anropar- `Dispose` metoden.

### <a name="invoking-the-simulator-from-python"></a>Anropa simulatorn från python

Använd metoden [simulera ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) från Q# python-biblioteket med den importerade Q# åtgärden:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Anropa simulatorn från kommando raden

När du kör ett Q# program från kommando raden är den fullständiga tillstånds simulatorn standard mål datorn. Alternativt kan du använda parametern **--Simulator** (eller **-s** genväg) för att ange önskad måldator. Följande kommandon kör ett program med fullständig tillstånds Simulator. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Anropa simulatorn från Juptyer Notebooks

Använd kommandot I Q# trollen [% simulera](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q# åtgärden.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Dirigera simulatorn

Som standard använder den fullständiga tillstånds simulatorn en slump tals generator för att simulera Quantum-slumpmässig het. I test syfte är det ibland användbart att ha deterministiska resultat. I ett C#-program kan du göra detta genom att tillhandahålla ett start värde för slump tals generatorn i `QuantumSimulator` konstruktorn via `randomNumberGeneratorSeed` parametern.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Konfigurera trådar

Den fullständiga tillstånds simulatorn använder [OpenMP](http://www.openmp.org/) för att parallellisera de linjära algebra som krävs. Som standard använder OpenMP alla tillgängliga maskin varu trådar, vilket innebär att program med små antal qubits ofta körs långsamt, eftersom den samordning som krävs för Dwarfs det faktiska arbetet. Du kan åtgärda detta genom att ställa in miljövariabeln `OMP_NUM_THREADS` på ett litet nummer. Som en regel för tummen konfigurerar du en tråd för upp till fyra qubits och sedan en ytterligare tråd per qubit. Du kan behöva justera variabeln beroende på algoritmen.

## <a name="see-also"></a>Se även

- [Kvantresursberäknare](xref:microsoft.quantum.machines.resources-estimator)
- [Toffoli-kvantsimulator](xref:microsoft.quantum.machines.toffoli-simulator)
- [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)