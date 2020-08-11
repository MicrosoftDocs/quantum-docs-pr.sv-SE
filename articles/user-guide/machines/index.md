---
title: Kvantsimulatorer och Q#-program
description: Beskriver de kvantsimulatorer som är tillgängliga som måldatorer för Q#-program.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868312"
---
# <a name="quantum-simulators"></a>Kvantsimulatorer

Kvantsimulatorer är program som körs på klassiska datorer och fungerar som *måldatorer* för Q#-program. Detta gör det möjligt att köra och testa kvantprogram i en miljö som kan förutsäga hur kvantbitar kommer att reagera på olika åtgärder. I den här artikeln beskrivs vilka kvantsimulatorer som ingår i Quantum Development Kit (QDK) och olika sätt att skicka Q#-program till kvantsimulatorer, till exempel via kommandoraden eller med hjälp av drivrutinskod som skrivs på ett klassiskt språk.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Kvantsimulatorer i Quantum Development Kit (QDK)

Kvantsimulatorn ansvarar för att tillhandahålla implementeringar av kvantprimitiver för en algoritm. Detta inkluderar primitiva åtgärder som t.ex. `H`, `CNOT` och `Measure`, samt hantering och spårning av kvantbitar. QDK innehåller olika klasser av kvantsimulatorer som motsvarar olika körningsmodeller för samma kvantalgoritm. 


Varje typ av kvantsimulator kan ge olika implementeringar av dessa primitiver. Till exempel kör en [simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) kvantalgoritmen genom att helt simulera [kvanttillståndsvektorn](xref:microsoft.quantum.glossary#quantum-state), medan [spårningssimulatorn för kvantdatorer](xref:microsoft.quantum.machines.qc-trace-simulator.intro) inte bryr sig om det faktiska kvanttillståndet alls. I stället spårar den grind-, kvantbits- och annan resursanvändning för algoritmen.

### <a name="quantum-machine-classes"></a>Kvantdatorklasser

Framöver kommer QDK:n att kunna definiera ytterligare kvantdatorklasser som har stöd för andra typer av simulering och stöd för körning på kvantmaskinvara. Om algoritmen tillåts vara konstant samtidigt som den underliggande datorimplementeringen varierar, blir det enkelt att testa och felsöka en algoritm i simuleringen. Den kan sedan köras på verklig maskinvara och man kan vara säker på att algoritmen inte har ändrats.

QDK:n innehåller flera kvantdatorklasser som definieras i namnområdet `Microsoft.Quantum.Simulation.Simulators`.

|Simulator |Klass|Beskrivning|
|-----|------|---|
|[Simulator med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Kör och felsöker kvantalgoritmer och är begränsad till cirka 30 kvantbitar. |
|[Enkel resursberäknare](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Gör en analys på toppnivå av vilka resurser som krävs för att köra en kvantalgoritm och har stöd för tusentals kvantbitar.|
|[Spårningsbaserad resursberäknare](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Kör avancerad analys av resursförbrukningen för algoritmens hela anropsgraf och har stöd för tusentals kvantbitar.|
|[Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simulerar kvantalgoritmer som är begränsade till `X`, `CNOT` och multistyrda `X` kvantåtgärder och har stöd för miljontals kvantbitar. |

## <a name="invoking-the-quantum-simulator"></a>Anropa kvantsimulatorn

I [Sätt att köra ett Q#-program på](xref:microsoft.quantum.guide.host-programs) visas tre sätt att skicka Q#-koden till kvantsimulatorn: 

* Använda kommandoraden
* Använda ett Python-värdprogram
* Använda ett C#-värdprogram

Kvantdatorer är instanser av vanliga .NET-klasser, vilket innebär att de skapas genom att anropa sin konstruktor, precis som alla andra .NET-klasser. Hur du gör detta beror på hur du kör Q#-programmet.

## <a name="next-steps"></a>Nästa steg

* Mer information om hur du anropar måldatorer för Q#-program i olika miljöer finns i [Sätt att köra ett Q#-program på](xref:microsoft.quantum.guide.host-programs).
