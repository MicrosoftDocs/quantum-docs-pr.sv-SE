---
title: 'Sätt att köra ett Q #-program'
description: 'Översikt över olika sätt att köra Q #-program. Från kommando raden, Q # Jupyter Notebooks och klassiska värd program i python eller ett .NET-språk.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887734"
---
# <a name="ways-to-run-a-q-program"></a>Sätt att köra ett Q #-program

Ett av de största fördelarna med Quantum Development Kit är dess flexibilitet i plattforms-och utvecklings miljöer.
Det innebär dock också att nya Q #-användare kan hitta sig förvirrande eller överbelastade av de många alternativen som finns i [installations guiden](xref:microsoft.quantum.install).
På den här sidan förklarar vi vad som händer när ett Q #-program körs och jämför de olika sätt som användarna kan göra.

En primär distinktion är att Q # kan köras:
- som ett fristående program, där Q # är det enda berörda språket och programmet anropas direkt. Två metoder är faktiskt i den här kategorin:
  - kommando rads gränssnittet
  - Q# Jupyter Notebooks
- med ett ytterligare *värd program*, skrivet i python eller ett .net-språk (t. ex. C# eller F #), som sedan anropar programmet och kan bearbeta returnerade resultat ytterligare.

För att bäst förstå de här processerna och deras skillnader, anser vi ett enkelt Q #-program och jämför hur det kan utföras.

## <a name="basic-q-program"></a>Basic Q #-program

Ett grundläggande Quantum-program kan bestå av att förbereda en qubit i en lika stor position av tillstånden $ \ket {0} $ och $ \ket {1} $, mäta den och returnera resultatet, vilket kommer att slumpmässigt vara ett av dessa två tillstånd med samma sannolikhet.
Den här processen är den som är kärnan i snabb starten av [Quantum slump tals Generator](xref:microsoft.quantum.quickstarts.qrng) .

I Q # skulle detta utföras av följande kod:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Den här koden kan dock endast utföras av Q #.
För att göra det måste du skapa en [Åtgärds](xref:microsoft.quantum.guide.basics#q-operations-and-functions)brödtext, som sedan körs när du anropar---antingen direkt eller av en annan åtgärd. Därför kan du skriva en åtgärd i följande format:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Du har definierat en åtgärd, `MeasureSuperposition` som inte tar några indata och returnerar ett värde av typen [result](xref:microsoft.quantum.guide.types).

Även om exemplen på den här sidan bara består av Q #- *åtgärder*, kommer alla koncept som vi diskuterar att diskuteras på samma sätt som q #- *funktioner*, och därför kan vi se dem gemensamt som *callables*. Deras skillnader diskuteras i [frågor](xref:microsoft.quantum.guide.basics#q-operations-and-functions)och meningar. mer information om hur du definierar dem finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-q-file"></a>Det går att anropa i en Q #-fil

Anropet är exakt vad som anropas och körs av Q #.
Det krävs dock några fler tillägg för att omfatta en fullständig `*.qs` Q #-fil.

Alla Q #-typer och callables (båda de som du definierar och de är inbyggda i språket) definieras i *namn områden*som ger varje fullständigt namn som sedan kan refereras.

Till exempel finns- [`H`](xref:microsoft.quantum.intrinsic.h) och- [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) åtgärderna i [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namn områdena och (en del av [standard biblioteken för Q #](xref:microsoft.quantum.qsharplibintro)).
Därför kan de alltid anropas via sina *fullständiga* namn `Microsoft.Quantum.Intrinsic.H(<qubit>)` och `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , men alltid göra detta skulle leda till mycket rörig kod.

I stället kan `open` callables refereras till med en mer koncis kort text som vi har gjort i åtgärds texten ovan.
Den fullständiga Q #-filen som innehåller vår åtgärd skulle därför bestå av att definiera vårt egna namn område, öppna namn områdena för de callables som vår åtgärd använder och sedan vår åtgärd:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> Namn områden kan också vara *aliasade* när de öppnas, vilket kan vara användbart om anrops bara/typnamn i två namn områden står i konflikt.
> Vi kan till exempel använda `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ovanstående, och sedan anropa `H` via `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Ett undantag till allt detta är [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namn området, som alltid öppnas automatiskt.
> Därför kan callables som [`Length`](xref:microsoft.quantum.core.length) alltid användas direkt.

### <a name="execution-on-target-machines"></a>Körning på mål datorer

Nu är den allmänna körnings modellen för ett Q #-program avmarkerad.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

För det första har det speciella anropet att utföras ha åtkomst till alla andra callables och typer som definierats i samma namnrymd.
De kommer även åt dem från något av [Q #-biblioteken](xref:microsoft.quantum.libraries), men de måste refereras antingen via fullständigt namn eller genom användning av instruktioner som `open` beskrivs ovan.

Själva anropet körs sedan på en *[måldator](xref:microsoft.quantum.machines)*.
Sådana mål datorer kan vara faktiska Quantum-maskinvara eller flera simulatorer som är tillgängliga som en del av QDK.
För våra behov är den mest användbara mål datorn en instans av [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` som beräknar programmets beteende som om den kördes på en brus fri dator som är en brus fri.

Hittills har vi beskrivit vad som händer när en speciell Q #-anrop körs.
Oavsett om Q # används i ett fristående program eller med ett värd program, är den här generella processen mer eller mindre---därför QDK.
Skillnaderna mellan olika sätt att anropa i Quantum Development Kit visas därför i *hur* det kan anropas i Q #, och i vilket sätt resultat returneras.
Mer specifikt kretsar skiljer sig runt 
1. indikerar vilket Q #-anrop som ska utföras,
2. Hur potentiella anrops bara argument tillhandahålls,
3. Ange den måldator där du vill köra den och
4. hur resultat returneras.

Först diskuterar vi hur detta görs med det fristående Q #-programmet från kommando raden och fortsätter sedan med att använda python-och C#-värd program.
Vi reserverar det fristående programmet för Q # Jupyter-anteckningsböcker för senaste, eftersom det är till exempel de första tre primära funktionerna inte är i mitten runt en lokal Q #-fil.

> [!NOTE]
> Även om vi inte visar det i de här exemplen, är en gemensam lösning mellan körnings metoderna att alla meddelanden som skrivs ut inifrån Q #-programmet ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) till exempel eller, till exempel) alltid skrivs ut till respektive konsol.

## <a name="q-from-the-command-line"></a>Q # från kommando raden
Ett av de enklaste sätten att komma igång med att skriva Q #-program är att undvika att behöva oroa dig för separata filer och ett andra språk helt och hållet.
Med hjälp av Visual Studio Code eller Visual Studio med QDK-tillägget kan du använda ett sömlöst arbets flöde där vi kör Q # callables endast från en enda Q #-fil.

För detta kommer vi i slut ändan att starta program körningen genom att ange
```dotnetcli
dotnet run
```
på kommando raden.
Det enklaste arbets flödet är när terminalens katalog plats är samma som Q #-filen, som enkelt kan hanteras bredvid Q # File Editing med hjälp av den integrerade terminalen i VS Code, till exempel.
[ `dotnet run` Kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) godkänner dock flera alternativ, och programmet kan också köras från en annan plats genom att bara ange `--project <PATH>` platsen för Q #-filen.


### <a name="add-entry-point-to-q-file"></a>Lägg till Start punkt i Q #-fil

De flesta Q #-filer kommer att innehålla mer än ett anrops bara, så det är naturligt att låta kompileraren ta reda på *vilken som* anropas när vi tillhandahåller `dotnet run` kommandot.
Detta görs med en enkel ändring i själva Q #-filen: 
    - Lägg till en rad med `@EntryPoint()` direkt föregående anrop.

Vår fil ovan skulle därför bli
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

Nu kommer ett anrop `dotnet run` från kommando raden att `MeasureSuperposition` köras och det returnerade värdet skrivs sedan direkt till terminalen.
Så visas antingen `One` eller `Zero` skrivs ut. 

Observera att det inte spelar någon roll om du har angett fler callables under den, så `MeasureSuperposition` körs endast.
Dessutom är det inget problem om ditt anrop bara innehåller [dokumentations kommentarer](xref:microsoft.quantum.guide.filestructure#documentation-comments) före dess deklaration, så `@EntryPoint()` kan attributet placeras ovanför dem.

### <a name="callable-arguments"></a>Anrops bara argument

Hittills har vi bara sett en åtgärd som inte kräver några indata.
Anta att vi ville utföra en liknande åtgärd, men på flera qubits---det antal som tillhandahålls som ett argument.
Sådan åtgärd kan skrivas som
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
där det returnerade värdet är en matris av mått resultatet.
Observera att [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) och [`ForEach`](xref:microsoft.quantum.arrays.foreach) är i [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namn områdena och som kräver ytterligare `open` instruktioner för varje.

Om vi flyttar `@EntryPoint()` attributet till före den här nya åtgärden (Observera att det bara kan finnas en sådan rad i en fil), försöker köra det med bara `dotnet run` resulterar i ett fel meddelande som anger vilka ytterligare kommando rads alternativ som krävs och hur du uttrycker dem.

Det allmänna formatet för kommando raden är faktiskt `dotnet run [options]` och det finns argument som kan anropas.
I det här fallet saknas argumentet `n` , och det visar att vi behöver tillhandahålla alternativet `-n <n>` . För att köra `MeasureSuperpositionArray` för `n=4` qubits använder vi därför

```dotnetcli
dotnet run -n 4
```

ge utdata som liknar

```output
[Zero,One,One,One]
```

Den här kursen utökar till flera argument.

> [!NOTE]
> Argument namn som definieras i `camelCase` har ändrats något av kompilatorn som ska accepteras som Q #-indata. Om till exempel i stället för `n` , vi använde namnet `numQubits` ovan, skulle den här indatan tillhandahållas på kommando raden via `--num-qubits 4` i stället för `-n 4` .

Fel meddelandet innehåller också andra alternativ som kan användas, inklusive hur du ändrar mål datorn.

### <a name="different-target-machines"></a>Olika mål datorer

Eftersom utmatningarna från våra åtgärder hittills har varit det förväntade resultatet av sin åtgärd på verkliga qubits, är det uppenbart att standard mål datorn från kommando raden är quauntum-simulatorn med full status `QuantumSimulator` .
Vi kan dock instruera callables att köras på en speciell måldator med alternativet `--simulator` (eller kort `-s` ).

Vi kan till exempel köra den på [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

De utskrivna utdata är sedan

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Mer information om vad dessa mått anger finns i [resurs uppskattningen: statistik rapporteras](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Sammanfattning av kommando rads körning
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Alternativ för icke-Q # `dotnet run`

Som vi nämnde ovan med `--project` alternativet godkänner [ `dotnet run` kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) också alternativ som inte är relaterade till de anrops bara argumenten för Q #.
Om du tillhandahåller båda typerna av alternativ `dotnet` måste de-/regionsspecifika alternativen anges först, följt av en avgränsare `--` och sedan de Q #-/regionsspecifika alternativen.
Till exempel kan specifiying en sökväg tillsammans med en nummer qubits för åtgärden ovan köras via `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Q # med värd program

Med vår Q #-fil i handen, är ett alternativ för att anropa en åtgärd eller funktion direkt från kommando raden att använda ett *värd program* i ett annat klassiskt språk. Mer specifikt kan detta göras med antingen python eller ett .NET-språk, till exempel C# eller F # (för det kortfattat vi bara detaljerat C# här).
Lite mer konfiguration krävs för att aktivera samverkan, men informationen finns i [installations guiderna](xref:microsoft.quantum.install).

I en kortfattat så Jenkins innehåller situationen nu en värd program fil (t. ex. `*.py` eller `*.cs` ) på samma plats som vår Q #-fil.
Det är nu *värd* programmet som körs och i samband med körningen kan det anropa speciella q #-åtgärder och-funktioner från Q #-filen.
Kärnan i interoperabiliteten baseras på Q #-kompilatorn som gör innehållet i den Q #-fil som är tillgängligt för värd programmet så att de kan anropas.

En av de främsta fördelarna med att använda ett värd program är att de klassiska data som returneras av Q #-programmet sedan kan bearbetas ytterligare på värd språket.
Detta kan bestå av en avancerad data bearbetning (t. ex. något som inte kan utföras internt i Q #) och sedan anropa ytterligare Q #-åtgärder baserat på dessa resultat eller något så enkelt som att rita Q #-resultaten.

Det allmänna schemat visas här och vi diskuterar de olika implementeringarna för python och C# nedan. Ett exempel som använder ett F # Host-program finns i [.net-samverkan exempel](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Attributet som används för Q #-kommando rads program kan inte användas med värd program.
> Ett fel genereras om det finns i Q #-filen som anropas av en värd. 

Om du vill arbeta med olika värd program krävs inga ändringar i en `*.qs` Q #-fil.
Följande värd program implementerar allt arbete med samma Q #-fil:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

Välj den flik som motsvarar värd språket i intresse.

### <a name="python"></a>[Python](#tab/tabid-python)
Ett python-värdprogram skapas på följande sätt:
1. Importera `qsharp` modulen som registrerar modulens inläsare för Q #-samverkan. 
    Detta gör att Q #-namnområden visas som python-moduler, där vi kan "Importera" Q # callables.
    Observera att den tekniskt sett inte är den Q #-callables som importeras, men hellre python-stub-meddelanden som tillåter att de anropar dem.
    De fungerar sedan som objekt i python-klasser, där vi använder metoder för att ange de mål datorer som åtgärden ska skickas till för körning.

2. Importera de Q #-callables som vi ska anropa direkt---i det här fallet `MeasureSuperposition` och `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    När `qsharp` modulen har importer ATS kan du också importera callables direkt från namn rymderna i Q # Library.

3. Bland alla andra python-koder kan du nu anropa dessa callables på specifika mål datorer och tilldela deras returer till variabler (om de returnerar ett värde) för att användas.

#### <a name="specifying-target-machines"></a>Ange mål datorer
Att anropa en åtgärd som ska köras på en särskild måldator görs via olika python-metoder för det importerade objektet.
Till exempel `.simulate(<args>)` använder, för `QuantumSimulator` att köra åtgärden, men gör det `.estimate_resources(<args>)` på `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Skicka indata till Q\#
Argumenten för Q #-anropet ska anges i form av ett nyckelord, där nyckelordet är argument namnet i den anropade Q #-definitionen.
Det vill säga är `MeasureSuperpositionArray.simulate(n=4)` giltigt, vilket `MeasureSuperpositionArray.simulate(4)` skulle resultera i ett fel.

Det innebär att python-värd programmet 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

resulterar i utdata som följande:

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Ett C#-värdprogram har flera komponenter och fungerar mycket nära vissa komponenter i QDK, till exempel simulatorer, som är inbyggda i C#.

Q #-kompilatorn fungerar här genom att generera ett likvärdigt namngivet C#-namnområde från namn området Q # i vår Q #-fil.
Den genererar ytterligare en motsvarande namngiven C#-klass för var och en av de Q # callables eller typer som definieras däri.

Först gör vi några klasser som används i vårt värd program `using` som är tillgängliga med instruktioner, som är ungefär analagousa till `open` instruktionerna i vår Q #-fil:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Därefter deklarerar vi vårt C#-namnrum, några andra bitar och delar (se hela kod blocket nedan) och sedan en klassisk programmering som vi vill ha (t. ex. beräknings argument för Q # callables).
Den senare är inte nödvändig i vårt fall, men ett exempel på en sådan användning finns i [exempel på .net-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Måldatorer

För att komma tillbaka till Q # måste vi skapa en instans av den mål dator som vi kommer att köra våra åtgärder på.

```csharp
            using var sim = new QuantumSimulator();
```

Att använda andra mål datorer är lika enkelt som att instansiera en annan, även om sättet att göra så och bearbetning av returerna kan vara något annorlunda.
För det kortfattat går vi till [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) för tillfället och inkluderar [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [nedan](#including-the-resources-estimator).

Varje C#-klass som genereras från Q #-åtgärder har en `Run` metod, vars första argument måste vara mål datorns instans.
Så att du kan köra `MeasureSuperposition` på `QuantumSimulator` , vi använder `MeasureSuperposition.Run(sim)` .
De returnerade resultaten kan sedan tilldelas variabler i C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Metoden körs asynkront eftersom det är fallet för verkligt Quantum-maskinvara, och därför `await` blockerar nyckelordet ytterligare körning tills aktiviteten har slutförts.

Om Q #-anropet inte har några returer (dvs. har retur typen `Unit` ) kan körningen fortfarande utföras på samma sätt utan att tilldela den till en variabel.
I så fall skulle hela raden helt enkelt bestå av 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argument

Alla argument till anrops funktionen i Q # skickas bara som ytterligare argument när mål datorn.
Resultatet av `MeasureSuperpositionArray` `n=4` qubits skulle därför hämtas via 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Ett fullständigt C#-värd program kan därför se ut så här

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

På platsen för C#-filen kan värd programmet köras från kommando raden genom att ange
```dotnetcli
dotnet run
```
i det här fallet kommer du att se utdata som skrivits till-konsolen, ungefär som 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> På grund av kompilatorns samverkan med namn områden kan vi alternativt göra vår Q #-callables tillgänglig utan `using NamespaceName;` instruktionen och helt enkelt matcha namn områdets namn områdes rubrik.
> Det vill säga genom att ersätta `namespace host` med `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inklusive resurs uppskattning

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Kräver en något annorlunda implementering för att hämta utdata.

För det första, i stället för att instansiera dem som en variabel med en `using` instruktion (som vi gör med `QuantumSimulator` ), instansierar vi omedelbart objekt av klassen via

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Observera att i stället för en enda mål simulator som ska användas av flera Q #-åtgärder har vi instansierat en för varje. Detta beror på att själva objekten ändras när de används som mål datorer och resultatet kan sedan hämtas efteråt med klass metoden `.ToTSV()` .

För att köra åtgärderna på resurs uppskattningarna använder vi

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
och hämtar sedan resultaten som Tabbavgränsade-värden (TSV) med `estimatorSingleQ.ToTSV()` och `estimatorMultiQ.ToTSV()` .

Det innebär att ett fullständigt C#-värdprogram som använder både `QuantumSimulator` och `ResourcesEstimator` kan ha formuläret:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


vilket ger utdata som liknar

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a>Q# Jupyter Notebooks
Q # Jupyter Notebooks använder SWEETIQ # kernel, som gör att du kan definiera, kompilera och köra Q # callables i en enskild Notebook---alla instruktioner, kommentarer och annat innehåll.
Det innebär att det är möjligt att importera och använda innehållet i `*.qs` Q #-filer, men det är inte nödvändigt i körnings modellen.

Här följer information om hur du kör de Q #-åtgärder som definierats ovan, men en mer bred introduktion till att använda Q # Jupyter Notebooks finns i [Introduktion till q #-och Jupyter-anteckningsböcker](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definiera åtgärder

I ett Q # Jupyter Notebook anger du Q # Code precis som vi skulle inifrån i namn området för en Q #-fil.

Därför kan vi aktivera åtkomst till callables från [Q # standard-biblioteken](xref:microsoft.quantum.qsharplibintro) med `open` instruktioner för deras respektive namn rymder.
När du kör en cell med en sådan instruktion, är definitionerna från dessa namn områden tillgängliga i hela arbets ytan.

> [!NOTE]
> Callables från [Microsoft. Quantum. inneboende](xref:microsoft.quantum.intrinsic) och [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (t. ex. [`H`](xref:microsoft.quantum.intrinsic.h) och [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) är automatiskt tillgängliga för åtgärder som definierats i celler i Q # Jupyter Notebooks.
> Detta gäller dock inte för kod som hämtas från externa Q # källfiler (en process som visas på [Introduktion till Q # och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

På samma sätt kräver definiering av åtgärder bara Q #-koden och körning av cellen.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

Utdata visar sedan dessa åtgärder, som sedan kan anropas från framtida celler.

### <a name="target-machines"></a>Måldatorer

Funktionerna för att köra åtgärder på specifika mål datorer tillhandahålls via [sweetiq # Magic-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp).
`%simulate`Använder exempelvis `QuantumSimulator` , och `%estimate` använder `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Skicka in indata till funktioner och åtgärder

För närvarande kan köra Magic-kommandon endast användas med åtgärder som inte tar några argument. För att kunna köra `MeasureSuperpositionArray` måste vi definiera en "wrapper"-åtgärd som sedan anropar åtgärden med argumenten:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Den här åtgärden kan naturligtvis användas på samma sätt som med `%estimate` och andra körnings kommandon.
