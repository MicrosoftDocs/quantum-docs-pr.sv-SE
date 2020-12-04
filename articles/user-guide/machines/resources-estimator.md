---
title: Uppskattningar av Quantum Resources-Quantum Development Kit
description: Lär dig mer om Microsoft QDKs resurs uppskattning, som beräknar de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604651"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Uppskatta QDK-resurser (Quantum Development Kit)

Som namnet antyder `ResourcesEstimator` beräknar klassen de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator. Detta uppnår detta genom att köra åtgärden Quantum utan att faktiskt simulera en Quantum-dators tillstånd. av den anledningen beräknar den resurser för Q# åtgärder som använder tusentals qubits, förutsatt att den klassiska delen av koden körs på rimlig tid.

Resurs uppräkningen är byggd ovanpå [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), som ger en mer omfattande uppsättning mått och verktyg som hjälper dig att felsöka Q# program.

## <a name="invoking-and-running-the-resources-estimator"></a>Anropar och kör resurs uppskattningen

Du kan använda resurs uppskattningen för att köra alla Q# åtgärder. Mer information finns i [sätt att köra ett Q# program](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Anropar resurs uppskattningen från C # 

Precis som med andra måldatorer skapar du först en instans av klassen `ResourcesEstimator` och skickar den sedan som den första parametern för en åtgärds `Run`-metod.

Observera att i motsats till `QuantumSimulator`-klassen implementerar `ResourcesEstimator`-klassen inte <xref:System.IDisposable>-gränssnittet och därför behöver du inte ange det i en `using`-instruktion.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Som exemplet visar `ResourcesEstimator` tillhandahåller `ToTSV()` metoden, som genererar en tabell med Tabbavgränsade värden (TSV). Du kan spara tabellen till en fil eller Visa den i konsolen för analys. Följande är ett exempel på utdata från föregående program:

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> En `ResourcesEstimator` instans återställer inte sina beräkningar vid varje körning. Om du använder samma instans för att köra en annan åtgärd sammanställs de nya resultaten med de befintliga resultaten. Om du behöver återställa beräkningar mellan körningarna skapar du en ny instans för varje körning.

### <a name="invoking-the-resources-estimator-from-python"></a>Anropar resurs uppskattningen från python

Använd metoden [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) från python-biblioteket med den importerade Q# åtgärden:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Anropar resurs uppskattningen från kommando raden

När du kör ett Q# program från kommando raden använder du parametern **--Simulator** (eller **-s** Shortcut) för att ange `ResourcesEstimator` mål datorn. Följande kommando kör ett program med hjälp av resurs uppskattningen: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Anropar resurs uppskattningen från Juptyer Notebooks

Använd Q# kommandot% unmagic kommandot [%](xref:microsoft.quantum.iqsharp.magic-ref.simulate) för att köra Q# åtgärden.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Hämta beräknade data program mässigt

Förutom en TSV-tabell kan du program mässigt hämta de beräknade resurserna under körning via `Data` egenskapen för resurs uppskattningen. `Data`Egenskapen ger en `System.DataTable` instans med två kolumner: `Metric` och `Sum` , indexerat av måttets namn.

Följande kod visar hur du hämtar och skriver ut det totala antalet `QubitClifford` - `T` och- `CNOT` åtgärder som används av en Q# åtgärd:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Rapporterade mått

Resurs uppskattningen spårar följande mått:

|Mått|Beskrivning|
|----|----|
|__CNOT__    |Antalet körningar av `CNOT` åtgärder (även kallat kontrollerade Pauli X-åtgärder).|
|__QubitClifford__ |Antalet körningar av alla enskilda qubit Clifford-och Pauli-åtgärder.|
|__Mått__    |Antalet körningar av alla mätningar.  |
|__R__    |Antalet körningar av en enskild-qubit rotations, exklusive `T` , Clifford och Pauli åtgärder.  |
|__T__    |Antalet körningar av `T` åtgärder och deras konjugat, inklusive `T` åtgärderna, T_x = H. T. H och T_y = hy. T. hy.  |
|__Djuplodande__|Djupet i Quantum-kretsen som körs av Q# åtgärden (se [nedan](#depth-width-and-qubitcount)). Djup måttet räknar som standard bara `T` grindar. Mer information finns i [djup räknare](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Bredd__|Bredden på den Quantum-krets som körs av Q# åtgärden (se [nedan](#depth-width-and-qubitcount)). Djup måttet räknar som standard bara `T` grindar. Mer information finns i [räknare för bredd](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).   |
|__QubitCount__    |Den nedre gränsen för maximalt antal allokerade qubits under körningen av Q# åtgärden. Det här måttet kanske inte är kompatibelt med __djupet__ (se nedan).  |
|__BorrowedWidth__    |Det maximala antalet qubits som lånas i Q# åtgärden.  |


## <a name="depth-width-and-qubitcount"></a>Djup, bredd och QubitCount

Rapporterade djup och bredd beräkningar är kompatibla med varandra.
(Tidigare båda talen var möjliga, men olika kretsar krävs för djup och bredd.) För närvarande kan båda måtten i det här paret uppnås med samma krets på samma tillfälle.

Följande mått rapporteras:

__Djup:__ För rot åtgärds tiden det tar att utföra den antar vissa grind tider.
För åtgärder som kallas eller efterföljande åtgärds tids skillnad mellan den senaste qubit tillgänglighets tiden i början och slutet av åtgärden.

__Bredd:__ För rot åtgärden – antalet qubits som faktiskt använts för att köra det (och anropet till den).
För åtgärder som kallas eller efterföljande åtgärder – hur många fler qubits som användes utöver qubits som redan användes i början av åtgärden.

Observera att återanvända qubits inte bidrar till det här numret.
T. ex. om några qubits har släppts innan en åtgärd A startar och alla qubit som krävs av den här åtgärden (och åtgärder som anropas från A) var uppfyllda genom att återanvända tidigare versions qubits, så rapporteras bredden A till 0. Lånade qubits bidrar inte till bredden.

__QubitCount:__ För rot åtgärden – minsta antal qubits som skulle räcka för att utföra den här åtgärden (och åtgärder som anropas från den).
För åtgärder som anropas eller efterföljande åtgärder – minsta antal qubits som skulle räcka för att utföra den här åtgärden separat. Det här talet inkluderar inte inqubits. Det innefattar lånade qubits.

Två drifts lägen stöds. Läge väljs genom att ställa in QCTraceSimulatorConfiguration. OptimizeDepth.

__OptimizeDepth = True:__ QubitManager rekommenderas inte från qubit åter användning och allokerar nya qubit varje gång den begär en qubit. För rot åtgärdens __djup__ blir det minsta djupet (nedre gräns). Kompatibel __Bredd__ rapporteras för det här djupet (båda kan uppnås samtidigt). Observera att den här bredden sannolikt inte är optimalt för detta djup. __QubitCount__ kan vara lägre än bredden för rot åtgärden eftersom den tar återanvända.

__OptimizeDepth = falskt:__ QubitManager uppmanas att återanvända qubits och återanvända de utgivna qubits innan du allokerar nya. __Bredden__ för rot åtgärden blir den minimala bredden (nedre gränser). Ett kompatibelt __djup__ rapporteras som kan uppnås. __QubitCount__ kommer att vara samma som __bredden__ för rot åtgärden förutsatt att ingen lånar.

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ange sannolikheten för mätresultatet

Du kan använda <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> från <xref:Microsoft.Quantum.Diagnostics> namn området för att ge information om den förväntade sannolikheten för en mätnings åtgärd. Mer information finns i [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Se även

- [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Toffoli-kvantsimulator](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kvantsimulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) 
