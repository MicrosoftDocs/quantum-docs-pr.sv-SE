---
title: Spårningssimulator för kvantdator – Quantum Development Kit
description: Lär dig att använda Microsofts spårningssimulator för kvantdatorer som felsöker klassisk kod och beräknar resurskraven för ett Q#-program.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54a1f63461cfcc8146f7dc4d18d321238d77454d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833354"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Spårningssimulator för kvantdator i Microsoft Quantum Development Kit (QDK)

QDK-klassen <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> kör ett kvantprogram utan att egentligen simulera tillståndet för en kvantdator. Det innebär att kvantspårningssimulatorn kan köra kvantprogram som använder tusentals kvantbitar.  Det är användbart av två viktiga orsaker: 

* Vid felsökning av klassisk kod som ingår i ett kvantprogram. 
* Vid beräkning av vilka resurser som krävs för att köra en specifik instans av ett kvantprogram på en kvantdator. Faktum är att [resursberäknaren](xref:microsoft.quantum.machines.resources-estimator), som ger en mer begränsad uppsättning mätvärden, bygger på spårningssimulatorn.

## <a name="invoking-the-quantum-trace-simulator"></a>Anropa kvantspårningssimulatorn

Du kan använda kvantspårningssimulatorn till att köra valfri Q#-åtgärd.

Precis som med andra måldatorer skapar du först en instans av klassen `QCTraceSimulator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.

Observera att i motsats till `QuantumSimulator`-klassen implementerar `QCTraceSimulator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mätresultatet

Eftersom kvantspårningssimulatorn inte simulerar det faktiska kvanttillståndet, kan den inte beräkna sannolikheten för mätresultatet i en åtgärd. 

Om en åtgärd inkluderar mätningar måste du därför uttryckligen ange dessa sannolikheter med hjälp av <xref:microsoft.quantum.diagnostics.assertmeasurementprobability>-åtgärden från namnområdet <xref:microsoft.quantum.diagnostics>. Följande exempel illustrerar detta:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

När kvantspårningssimulatorn påträffar `AssertMeasurementProbability` kommer den registrera att mätning av `PauliZ` i `source` och `q` bör visa ett resultat på `Zero`, med sannolikheten **0,5**. När `M`-åtgärden körs senare hittar den de registrerade värdena i resultatets sannolikhet och `M` returnerar `Zero` eller `One`, med sannolikheten **0,5**. När samma kod körs i en simulator som håller koll på kvanttillståndet, kontrollerar simulatorn att de angivna sannolikheterna i `AssertMeasurementProbability` är korrekta.

Observera att om det finns minst en mätningsåtgärd som inte är kommenterad med `AssertMeasurementProbability`, utlöser simulatorn ett [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Verktyg för kvantspårningssimulator

QDK:n innehåller fem verktyg som du kan använda med kvantspårningssimulatorn för att hitta buggar i dina program och utföra beräkningar av kvantprogramresurser: 

|Verktyg | Beskrivning |
|-----| -----|
|[Kontroll av distinkta indata](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Söker efter potentiella konflikter med delade kvantbitar |
|[Kontroll av användning av upphävda kvantbitar](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Kontrollerar om programmet tillämpar en åtgärd på en kvantbit som redan har släppts |
|[Räknare för primitiva åtgärder](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Räknar antalet primitiva processer som används av varje åtgärd som anropas i ett kvantprogram  |
|[Djupräknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Samlar in antal som representerar de nedre gränserna för djupet i varje åtgärd som anropas i ett kvantprogram   |
|[Breddräknare](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Räknar antalet allokerade och lånade kvantbitar för varje åtgärd i ett kvantprogram |

Vart och ett av dessa verktyg aktiveras genom att ställa in lämpliga flaggor i `QCTraceSimulatorConfiguration` och sedan skicka konfigurationen till `QCTraceSimulator`-deklarationen. Information om hur du använder de olika verktygen finns i länkarna i föregående lista. Mer information om hur du konfigurerar `QCTraceSimulator` finns i [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>QCTraceSimulator-metoder

`QCTraceSimulator` har flera inbyggda metoder för att hämta värdena för de mått som spåras under en kvantåtgärd. Exempel på [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric)- och [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv)-metoderna finns i artiklarna [Räknare för primitiva åtgärder](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Djupräknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) och [Breddräknare](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Mer information om alla tillgängliga metoder finns i [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) i Q# API-referensen.  

## <a name="see-also"></a>Se även

- [Kvantresursberäknare](xref:microsoft.quantum.machines.resources-estimator)
- [Toffoli-kvantsimulator](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kvantsimulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) 