---
title: Kvantsimulatorer och värdprogram | Microsoft Docs
description: Beskriver hur du använder kvantsimulatorer med ett klassiskt .NET-språk, vanligtvis antingen C# eller Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273809"
---
# <a name="quantum-simulators-and-host-applications"></a>Kvantsimulatorer och värdprogram

## <a name="what-youll-learn"></a>Detta får du lära dig

> [!div class="checklist"]
> * Hur kvantalgoritmer körs
> * Vilka kvantsimulatorer som ingår i den här versionen
> * Hur du skriver en C#-drivrutin för kvantalgoritmen

## <a name="the-quantum-development-kit-execution-model"></a>Körningsmodell för Quantum Development Kit

I [Att skriva ett kvantprogram](xref:microsoft.quantum.write-program) körde vi vår kvantalgoritm genom att skicka ett `QuantumSimulator`-objekt till algoritmklassens `Run`-metod.
`QuantumSimulator`-klassen kör kvantalgoritmen genom att helt simulera kvanttillståndets vektor, vilket är perfekt när man vill köra och testa `Teleport`.
I [Begreppsguide](xref:microsoft.quantum.concepts.intro) finns mer information om kvanttillståndsvektorer.

Andra måldatorer kan användas för att köra en kvantalgoritm.
Datorn ansvarar för att tillhandahålla implementeringar av kvantprimitiver för algoritmen.
Detta inkluderar primitiva åtgärder som t. ex. H, CNOT och Measure, samt hantering och spårning av kvantbitar.
Olika klasser i kvantdatorer representerar olika körningsmodeller för samma kvantalgoritm.

Varje typ av kvantdator kan ge olika implementeringar av dessa primitiver.
Till exempel utför spårningssimulatorn för kvantdatorn som ingår i utvecklingspaketet inte någon simulering alls.
I stället spårar den grind-, kvantbits- och annan resursanvändning för algoritmen.

### <a name="quantum-machines"></a>Kvantdatorer

Senare definierar vi ytterligare kvantdatorklasser som har stöd för andra typer av simulering och stöd för körning på topologiska kvantdatorer.
Om algoritmen tillåts vara konstant samtidigt som den underliggande datorimplementeringen varierar, blir det enkelt att testa och felsöka en algoritm i simuleringen. Den kan sedan köras på verklig maskinvara och man kan vara säker på att algoritmen inte har ändrats.

### <a name="whats-included-in-this-release"></a>Vad ingår i den här versionen?

Den här versionen av Quantum Developer Kit innehåller flera kvantdatorklasser.
Alla definieras i namnområdet `Microsoft.Quantum.Simulation.Simulators`.

* En [vektorsimulator för fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`-klassen.
* En [enkel resursberäknare](xref:microsoft.quantum.machines.resources-estimator), `ResourcesEstimator`-klassen. Beräknaren gör en analys på toppnivå av vilka resurser som krävs för att köra en kvantalgoritm.
* En [spårningsbaserad resursberäknare](xref:microsoft.quantum.machines.qc-trace-simulator.intro), `QCTraceSimulator`-klassen. Beräknaren möjliggör avancerad analys av resursförbrukningen för algoritmens hela anropsgraf.
* En [Toffoli-simulator](xref:microsoft.quantum.machines.toffoli-simulator), `ToffoliSimulator`-klassen.

## <a name="writing-a-host-application"></a>Skriva ett värdprogram

I [Att skriva ett kvantprogram](xref:microsoft.quantum.write-program) skrev vi en enkel C#-drivrutin för vår teleporteringsalgoritm. En C#-drivrutin har fyra huvudsakliga syften:

* Skapa måldatorn
* Beräkna eventuella argument som krävs för kvantalgoritmen
* Köra kvantalgoritmen med simulatorn
* Bearbeta resultatet av åtgärden

Här diskuterar vi varje steg mer ingående.

### <a name="constructing-the-target-machine"></a>Skapa måldatorn

Kvantdatorer är instanser av vanliga .NET-klasser, vilket innebär att de skapas genom att anropa sin konstruktor, precis som alla andra .NET-klasser.
Vissa simulatorer, inklusive `QuantumSimulator`, implementerar .NET <xref:System.IDisposable?displayProperty=nameWithType>-gränssnittet och ska omslutas i en C#`using`-instruktion.

### <a name="computing-arguments-for-the-algorithm"></a>Beräkna argument för algoritmen

I vårt `Teleport`-exempel beräknade vi några relativt artificiella argument som ska skickas till vår kvantalgoritm.
Det är dock vanligare att det finns viktiga data som krävs av kvantalgoritmen, och det är enklast att tillhandahålla den från den klassiska drivrutinen.

Vid kemiska simuleringar kräver till exempel kvantalgoritmen en stor tabell med interaktionsintegraler för molekylorbitaler.
De läses vanligtvis in från en fil som tillhandahålls när algoritmen körs.
Eftersom Q# inte har någon metod för att komma åt filsystemet, samlas dessa datatyper in bäst av den klassiska drivrutinen och skickas sedan till kvantalgoritmens `Run`-metod.

Ett annat fall där den klassiska drivrutinen spelar en nyckelroll är i variationsmetoder.
I den här algoritmklassen förbereds ett kvanttillstånd som baseras på vissa klassiska parametrar. Detta tillstånd används sedan för att beräkna specifika intressanta värden.
Parametrarna justeras baserat på algoritmtypen hill climbing eller maskininlärning, varefter kvantalgoritmen körs igen.
Vid sådana algoritmer implementeras hill climbing-algoritmen bäst som en helt klassisk funktion som anropas av den klassiska drivrutinen. Resultatet av hill climbing-algoritmen skickas sedan till nästa körning av kvantalgoritmen.

### <a name="running-the-quantum-algorithm"></a>Köra kvantalgoritmen

Den här delen är i allmänhet rätt okomplicerad.
Varje Q#-åtgärd kompileras till en klass som tillhandahåller en statisk `Run`-metod.
Argumenten till den här metoden kommer från den utplattade argumenttuppeln för själva åtgärden, plus ett ytterligare första argument som är simulatorn som ska köras. För en åtgärd som förväntar sig den namngivna tuppeln av typen `(a: String, (b: Double, c: Double))`, är dess utplattade motsvarighet av typen `(String a, Double b, Double c)`.


Det finns vissa saker att tänka på när argument skickas till en `Run`-metod:

* Matriser måste vara omslutna i ett `Microsoft.Quantum.Simulation.Core.QArray<T>`-objekt.
    En `QArray`-klass har en konstruktor som kan hantera alla sorterade samlingar (`IEnumerable<T>`) med lämpliga objekt.
* Den tomma tuppeln, `()` i Q#, representeras av `QVoid.Instance` i C#.
* Tupplar som inte är tomma representeras som `ValueTuple`-instanser i .NET.
* Q#-användardefinierade typer skickas som bastypen.
* Om du vill skicka en åtgärd eller en funktion till en `Run`-metod, måste du hämta en instans av åtgärdens eller funktionens klass med hjälp av simulatorns `Get<>`-metod.

### <a name="processing-the-results"></a>Bearbeta resultat

Resultatet av kvantalgoritmen returneras från `Run`-metoden.
`Run`-metoden körs asynkront och returnerar därför en instans av <xref:System.Threading.Tasks.Task`1>.
Det finns flera sätt att hämta det faktiska åtgärdsresultatet på. Det enklaste är att använda `Task`:s [`Result`-egenskap](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
Men andra tekniker, som att använda [`Wait`-metoden](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) eller [`await`-nyckelord](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) i C# fungerar också.

Precis som i argument visas Q#-tupplar som `ValueTuple`-instanser och Q#-matriser visas som `QArray`-instanser.
Användardefinierade typer skickas som bastyper.
Den tomma tuppeln, `()`, returneras som en instans av klassen `QVoid`.

Många kvantalgoritmer kräver avsevärd efterbearbetning för att kunna härleda användbara svar.
Till exempel är kvantdelen av Shors algoritm bara början av en beräkning som hittar faktorerna i ett tal.

I de flesta fall är det enklast att göra denna typ av efterbearbetning i den klassiska drivrutinen.
Det är bara den klassiska drivrutinen som kan rapportera resultat till användaren eller skriva dem till disk.
Den klassiska drivrutinen har åtkomst till analysbibliotek och andra matematiska funktioner som inte visas i Q#.


## <a name="failures"></a>Fel

När Q# `fail`-instruktionen nås under körningen av en åtgärd, utlöses ett `ExecutionFailException`.

Eftersom `System.Task` har använts i `Run`-metoden utlöses ett undantagsfel som orsakas av att en `fail`-instruktion kommer att omslutas i ett `System.AggregateException`.
För att hitta den faktiska orsaken till det här felet måste du iterera i `AggregateException` 
`InnerExceptions`, till exempel:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Andra klassiska språk

Även om de exempel som vi har visat är i C#, F# och Python, har Quantum Development Kit också stöd för att skriva klassiska värdprogram på andra språk.
Om du till exempel vill skriva ett värdprogram i Visual Basic [går det utmärkt](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
