---
title: Sätt att köra ett Q# program
description: Översikt över olika sätt att köra Q# program. Från kommando tolken, Q# Jupyter-anteckningsböcker och klassiska värd program i python eller ett .net-språk.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e44a366b7eea133499beb44dbb338a02174c0073
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863198"
---
# <a name="ways-to-run-a-no-locq-program"></a>Sätt att köra ett Q# program

Ett av de största fördelarna med Quantum Development Kit är dess flexibilitet i plattforms-och utvecklings miljöer.
Det innebär dock också att nya Q# användare kan upptäcka att de många alternativen finns i [installations guiden](xref:microsoft.quantum.install).
På den här sidan förklarar vi vad som händer när ett Q# program körs och jämför de olika sätt som användarna kan göra.

En primär distinktion är att Q# du kan köra:
- som ett fristående program, där Q# är det enda språk som ingår och programmet anropas direkt. Två metoder är faktiskt i den här kategorin:
  - kommando rads gränssnittet
  - Q# Jupyter-anteckningsböcker
- med ett ytterligare *värd program*, skrivet i python eller ett .net-språk (t. ex. C# eller F #), som sedan anropar programmet och kan bearbeta returnerade resultat ytterligare.

För att bäst förstå de här processerna och deras skillnader, Överväg vi ett enkelt Q# program och jämför hur det kan utföras.

## <a name="basic-no-locq-program"></a>Basic- Q# program

Ett grundläggande Quantum-program kan bestå av att förbereda en qubit i en lika stor position av tillstånden $ \ket {0} $ och $ \ket {1} $, mäta den och returnera resultatet, vilket kommer att slumpmässigt vara ett av dessa två tillstånd med samma sannolikhet.
Den här processen är den som är kärnan i snabb starten av [Quantum slump tals Generator](xref:microsoft.quantum.quickstarts.qrng) .

I Q# kan detta utföras med följande kod:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Den här koden kan dock inte utföras av Q# .
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

Även om exemplen på den här sidan bara består av Q# *åtgärder*, kommer alla koncept som vi diskuterar att diskutera är lika med Q# *funktioner*, och därför kan vi se dem gemensamt som *callables*. Skillnaderna beskrivs i [ Q# grunderna: åtgärder och funktioner](xref:microsoft.quantum.guide.basics#q-operations-and-functions), och mer information om hur du definierar dem finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-no-locq-file"></a>Det går att anropa i en Q# fil

Anropet är exakt vad som anropas och körs av Q# .
Det krävs dock några fler tillägg för att omfatta en fullständig `*.qs` Q# fil.

Alla Q# typer och callables (både de som du definierar och de är inbyggda i språket) definieras i *namn områden*som ger varje fullständigt namn som sedan kan refereras.

Till exempel finns- [`H`](xref:microsoft.quantum.intrinsic.h) och- [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) åtgärderna i [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namn områdena och (ingår i [ Q# standard biblioteken](xref:microsoft.quantum.qsharplibintro)).
Därför kan de alltid anropas via sina *fullständiga* namn `Microsoft.Quantum.Intrinsic.H(<qubit>)` och `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , men alltid göra detta skulle leda till mycket rörig kod.

I stället kan `open` callables refereras till med en mer koncis kort text som vi har gjort i åtgärds texten ovan.
Den fullständiga Q# filen som innehåller vår åtgärd skulle därför bestå av att definiera vår egen namnrymd, öppna namn områdena för de callables som vår åtgärd använder och sedan vår åtgärd:

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

Nu är den allmänna körnings modellen för ett Q# program avmarkerad.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

För det första har det speciella anropet att utföras ha åtkomst till alla andra callables och typer som definierats i samma namnrymd.
De kommer även åt dem från alla [ Q# bibliotek](xref:microsoft.quantum.libraries), men de måste refereras antingen via deras fullständiga namn eller genom användning av `open` instruktioner som beskrivs ovan.

Själva anropet körs sedan på en *[måldator](xref:microsoft.quantum.machines)*.
Sådana mål datorer kan vara faktiska Quantum-maskinvara eller flera simulatorer som är tillgängliga som en del av QDK.
För våra behov är den mest användbara mål datorn en instans av [hela tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` som beräknar programmets beteende som om den kördes på en brus fri dator som är en brus fri.

Hittills har vi beskrivit vad som händer när en speciell Q# anrop utförs.
Oavsett om används Q# i ett fristående program eller med ett värd program, är den här generella processen mer eller mindre---, och därför är QDK flexibiliteten.
Skillnaderna mellan olika sätt att anropa i Quantum Development Kit visas därför i *hur* det kan anropas Q# för att utföras och på vilket sätt resultaten returneras.
Mer specifikt kretsar skiljer sig runt 
1. indikerar vilket anrop som ska Q# utföras,
2. Hur potentiella anrops bara argument tillhandahålls,
3. Ange den måldator där du vill köra den och
4. hur resultat returneras.

Först diskuterar vi hur detta görs med det Q# fristående programmet från kommando tolken och fortsätter sedan att använda python-och C#-värd program.
Vi reserverar det fristående programmet för Q# Jupyter Notebooks för sista, eftersom till skillnad från de tre första, är den primära funktionen inte en lokal Q# fil.

> [!NOTE]
> Även om vi inte illustrerar det i de här exemplen, är en gemensam lösning mellan körnings metoderna att alla meddelanden som skrivs ut inifrån Q# programmet (av [`Message`](xref:microsoft.quantum.intrinsic.message) eller till [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) exempel) alltid skrivs ut till respektive konsol.

## <a name="no-locq-from-the-command-prompt"></a>Q# från kommando tolken
Ett av de enklaste sätten att komma igång med att skriva Q# program är att undvika att behöva oroa dig för separata filer och ett andra språk helt och hållet.
Med hjälp av Visual Studio Code eller Visual Studio med QDK-tillägget kan du använda ett sömlöst arbets flöde där vi kör Q# callables från endast en enda Q# fil.

För detta kommer vi i slut ändan att starta program körningen genom att ange
```dotnetcli
dotnet run
```
i kommando tolken.
Det enklaste arbets flödet är när terminalens katalog plats är samma som Q# filen, som enkelt kan hanteras tillsammans Q# med fil redigering genom att använda den integrerade terminalen i vs Code, till exempel.
[ `dotnet run` Kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) godkänner dock flera alternativ, och programmet kan också köras från en annan plats genom att bara ange `--project <PATH>` platsen för Q# filen.


### <a name="add-entry-point-to-no-locq-file"></a>Lägg till Start punkt till Q# fil

De flesta Q# filer kommer att innehålla mer än ett anrops bara, så det är naturligt att låta kompileraren ta reda på *vilket* anrop som kan utföras när vi tillhandahåller `dotnet run` kommandot.
Detta görs med en enkel ändring i Q# själva filen: 
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

Nu kommer ett anrop `dotnet run` från kommando tolken att `MeasureSuperposition` köras, och det returnerade värdet skrivs sedan direkt till terminalen.
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
> Argument namn som definieras i `camelCase` har ändrats något av kompilatorn som ska godkännas som Q# indata. Om till exempel i stället för `n` , vi använde namnet `numQubits` ovan, skulle den här indatan tillhandahållas på kommando raden via `--num-qubits 4` i stället för `-n 4` .

Fel meddelandet innehåller också andra alternativ som kan användas, inklusive hur du ändrar mål datorn.

### <a name="different-target-machines"></a>Olika mål datorer

Eftersom resultatet från våra åtgärder hittills har varit det förväntade resultatet av sin åtgärd på verkliga qubits, är det uppenbart att standard mål datorn från kommando raden är en Quantum-simulator med full status `QuantumSimulator` .
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

### <a name="non-no-locq-dotnet-run-options"></a>Icke- Q# `dotnet run` alternativ

Som vi nämnde ovan med `--project` alternativet godkänner [ `dotnet run` kommandot](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) också alternativ som inte är relaterade till de Q# anrops bara argumenten.
Om du tillhandahåller båda typerna av alternativ `dotnet` måste de-/regionsspecifika alternativen anges först, följt av en avgränsare `--` och sedan de Q# -/regionsspecifika alternativen.
Till exempel kan specifiying en sökväg tillsammans med en nummer qubits för åtgärden ovan köras via `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# med värd program

Med vår Q# fil i handen är ett alternativ för att anropa en åtgärd eller funktion direkt från kommando tolken att använda ett *värd program* i ett annat klassiskt språk. Mer specifikt kan detta göras med antingen python eller ett .NET-språk, till exempel C# eller F # (för det kortfattat vi bara detaljerat C# här).
Lite mer konfiguration krävs för att aktivera samverkan, men informationen finns i [installations guiderna](xref:microsoft.quantum.install).

I en kortfattat så Jenkins innehåller situationen nu en värd program fil (t. ex. `*.py` eller `*.cs` ) på samma plats som vår Q# fil.
Det är nu *värd* programmet som körs och i samband med körningen kan det anropa vissa Q# åtgärder och funktioner från Q# filen.
Kärnornas kärna baseras på Q# kompilatorn som gör innehållet i Q# filen tillgängligt för värd programmet så att de kan anropas.

En av de främsta fördelarna med att använda ett värd program är att de klassiska data som returneras av Q# programmet kan bearbetas ytterligare på värd språket.
Detta kan bestå av en avancerad data bearbetning (t. ex. något som inte kan utföras internt i Q# ) och sedan anropa ytterligare Q# åtgärder baserat på dessa resultat eller något så enkelt som att rita Q# resultatet.

Det allmänna schemat visas här och vi diskuterar de olika implementeringarna för python och C# nedan. Ett exempel som använder ett F # Host-program finns i [.net-samverkan exempel](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Attributet som används för Q# program kan inte användas med värd program.
> Ett fel genereras om det finns i den Q# fil som anropas av en värd. 

Om du vill arbeta med olika värd program krävs inga ändringar i en `*.qs` Q# fil.
Följande värd program implementerar allt arbete med samma Q# fil:

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
1. Importera `qsharp` modulen som registrerar modulens inläsare för Q# interoperabilitet. 
    Detta gör Q# att namn områden kan visas som python-moduler, från vilka vi kan importera Q# callables.
    Observera att det tekniskt sett inte är Q# callablest som importeras, men hellre python-stub-stub som tillåter att de anropar dem.
    De fungerar sedan som objekt i python-klasser, där vi använder metoder för att ange de mål datorer som åtgärden ska skickas till för körning.

2. Importera de Q# callables som vi kommer att anropa direkt---i det här fallet `MeasureSuperposition` och `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    När `qsharp` modulen har importer ATS kan du också importera callables direkt från Q# biblioteks namn områdena.

3. Bland alla andra python-koder kan du nu anropa dessa callables på specifika mål datorer och tilldela deras returer till variabler (om de returnerar ett värde) för att användas.

#### <a name="specifying-target-machines"></a>Ange mål datorer
Att anropa en åtgärd som ska köras på en särskild måldator görs via olika python-metoder för det importerade objektet.
Till exempel `.simulate(<args>)` använder, för `QuantumSimulator` att köra åtgärden, men gör det `.estimate_resources(<args>)` på `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Skicka indata till Q\#
Argument för anrop kan anges Q# i form av ett nyckelord, där nyckelordet är argument namnet i den Q# anropade definitionen.
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

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Använda Q# kod från andra projekt eller paket

Som standard `import qsharp` läser kommandot in alla `.qs` filer i den aktuella mappen och gör att deras Q# åtgärder och funktioner kan användas i python-skriptet.

Om du vill läsa in Q# kod från en annan mapp kan du använda [ `qsharp.projects` API: et](https://docs.microsoft.com/python/qsharp/qsharp.projects.projects) för att lägga till en referens till en `.csproj` fil för ett Q# projekt (det vill säga ett projekt som refererar `Microsoft.Quantum.Sdk` ).
Det här kommandot kommer att kompilera alla `.qs` filer i mappen som innehåller `.csproj` undermapparna och. Det kommer också att läsa in alla paket som refereras via `PackageReference` eller Q# projekt som refereras till via `ProjectReference` i `.csproj` filen.

Följande python-kod importerar till exempel ett externt projekt, refererar till dess sökväg i förhållande till den aktuella mappen och anropar en av dess Q# åtgärder:

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Detta resulterar i utdata som följande:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

Q#Använd [ `qsharp.packages` API: et](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages)för att läsa in externa paket som innehåller kod.

Om Q# koden i den aktuella mappen är beroende av externa projekt eller paket kan du se fel när du kör `import qsharp` , eftersom beroendena ännu inte har lästs in.
Om du vill läsa in nödvändiga externa paket eller Q# projekt under `import qsharp` kommandot kontrollerar du att mappen med python-skriptet innehåller en `.csproj` fil som refererar till den `Microsoft.Quantum.Sdk` . I `.csproj` lägger du till egenskapen `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` i `<PropertyGroup>` . Detta instruerar mig Q# att rekursivt läsa in alla `ProjectReference` eller `PackageReference` objekt som finns i det `.csproj` under `import qsharp` kommandot.

Här är till exempel en enkel `.csproj` fil som gör att jag Q# kan läsa in `Microsoft.Quantum.Chemistry` paketet automatiskt:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> För närvarande krävs den här anpassade `<IQSharpLoadAutomatically>` egenskapen av python-värdar, men i framtiden kan detta bli standard beteendet för en `.csproj` fil som finns i samma mapp som python-skriptet.

> [!NOTE]
> För närvarande `<QsharpCompile>` ignoreras inställningen i av `.csproj` python-värdar, och alla `.qs` filer i mappen i `.csproj` (inklusive undermappar) läses in och kompileras. Stöd för `.csproj` inställningar kommer att förbättras i framtiden (se [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) för mer information).


### <a name="c"></a>[C#](#tab/tabid-csharp)

Ett C#-värdprogram har flera komponenter och fungerar mycket nära vissa komponenter i QDK, till exempel simulatorer, som är inbyggda i C#.

Q#Kompilatorn fungerar här genom att generera ett likvärdigt namngivet C#-namnområde från Q# namn området i vår Q# fil.
Den genererar ytterligare en motsvarande namngiven C#-klass för var och en av de Q# callables eller typer som definieras däri.

Först gör vi några klasser som används i vårt värd program `using` som är tillgängliga med instruktioner, som är ungefär analagousa till `open` uttrycken i vår Q# fil:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Härnäst deklarerar vi vårt C#-namnrum, några andra bitar och delar (se hela kod blocket nedan) och sedan en klassisk programmering som vi vill ha (t. ex. beräknings argument för Q# callables).
Den senare är inte nödvändig i vårt fall, men ett exempel på en sådan användning finns i  [exempel på .net-interoperabilitet](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Måldatorer

Kom tillbaka till Q# , vi måste skapa en instans av den mål dator som vi kommer att köra våra åtgärder på.

```csharp
            using var sim = new QuantumSimulator();
```

Att använda andra mål datorer är lika enkelt som att instansiera en annan, även om sättet att göra så och bearbetning av returerna kan vara något annorlunda.
För det kortfattat går vi till [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) för tillfället och inkluderar [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [nedan](#including-the-resources-estimator).

Varje C#-klass som genereras från Q# åtgärder har en `Run` metod, vars första argument måste vara mål datorns instans.
Så att du kan köra `MeasureSuperposition` på `QuantumSimulator` , vi använder `MeasureSuperposition.Run(sim)` .
De returnerade resultaten kan sedan tilldelas variabler i C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Metoden körs asynkront eftersom det är fallet för verkligt Quantum-maskinvara, och därför `await` blockerar nyckelordet ytterligare körning tills aktiviteten har slutförts.

Om Q# anropet inte har några returer (t. ex. har retur typen `Unit` ) kan körningen fortfarande utföras på samma sätt utan att tilldela den till en variabel.
I så fall skulle hela raden helt enkelt bestå av 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argument

Alla argument till Q# anrops bara skickas som ytterligare argument när mål datorn.
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

På C#-filens plats kan värd programmet köras från kommando tolken genom att ange
```dotnetcli
dotnet run
```
i det här fallet kommer du att se utdata som skrivits till-konsolen, ungefär som 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> På grund av kompilatorns samverkan med namn områden kan vi alternativt göra vårt Q# callables tillgängligt utan `using NamespaceName;` instruktionen och helt enkelt matcha namn områdets namn områdes rubrik.
> Det vill säga genom att ersätta `namespace host` med `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inklusive resurs uppskattning

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Kräver en något annorlunda implementering för att hämta utdata.

För det första, i stället för att instansiera dem som en variabel med en `using` instruktion (som vi gör med `QuantumSimulator` ), instansierar vi omedelbart objekt av klassen via

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Observera att i stället för en enda mål simulator som ska användas av flera Q# åtgärder har vi instansierat en för varje. Detta beror på att själva objekten ändras när de används som mål datorer och resultatet kan sedan hämtas efteråt med klass metoden `.ToTSV()` .

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

## <a name="no-locq-jupyter-notebooks"></a>Q# Jupyter-anteckningsböcker
Q# Jupyter Notebooks använder i- Q# kärnan, vilket gör att du kan definiera, kompilera och köra Q# callables i en enda Notebook---alla instruktioner, kommentarer och annat innehåll.
Det innebär att det är möjligt att importera och använda innehållet i filer, men det är `*.qs` Q# inte nödvändigt i körnings modellen.

Här kommer vi att lära dig hur du kör de Q# åtgärder som definierats ovan, men en mer bred introduktion till att använda Q# Jupyter Notebooks finns i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definiera åtgärder

I en Q# Jupyter Notebook anger du Q# kod på samma sätt som i namn området för en Q# fil.

Därför kan vi aktivera åtkomst till callables från [ Q# standard biblioteken](xref:microsoft.quantum.qsharplibintro) med `open` instruktioner för deras respektive namn rymder.
När du kör en cell med en sådan instruktion, är definitionerna från dessa namn områden tillgängliga i hela arbets ytan.

> [!NOTE]
> Callables från [Microsoft. Quantum. inneboende](xref:microsoft.quantum.intrinsic) och [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (t. ex. [`H`](xref:microsoft.quantum.intrinsic.h) och [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) är automatiskt tillgängliga för åtgärder som definierats i celler i Q# Jupyter notebook-datorer.
> Detta gäller dock inte för kod som hämtas från externa Q# källfiler (en process som visas i [intro till Q# och Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

På samma sätt kräver definiering av åtgärder bara att Q# koden skrivs och att cellen körs.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

Utdata visar sedan dessa åtgärder, som sedan kan anropas från framtida celler.

### <a name="target-machines"></a>Måldatorer

Funktionerna för att köra åtgärder på specifika mål datorer finns via [I Q# Magic-kommandon](xref:microsoft.quantum.guide.quickref.iqsharp).
`%simulate`Använder exempelvis `QuantumSimulator` , och `%estimate` använder `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>Skicka in indata till funktioner och åtgärder

Om du vill skicka indata till Q# åtgärder kan argumenten skickas som `key=value` par till kommandot Magic Magic.
För att kunna köra `MeasureSuperpositionArray` med fyra qubits kan vi köra `%simulate MeasureSuperpositionArray n=4` :

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Det här mönstret kan användas på samma sätt med `%estimate` och andra körnings kommandon.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Använda Q# kod från andra projekt eller paket

Som standard läser ett Q# Jupyter Notebook alla `.qs` filer i den aktuella mappen och gör att de kan Q# användas i den bärbara datorn. [ `%who` Kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.who) visar alla åtgärder och funktioner som är tillgängliga för närvarande Q# .

Om du vill läsa in Q# kod från en annan mapp kan du använda [ `%project` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) för att lägga till en referens till en `.csproj` fil för ett Q# projekt (det vill säga ett projekt som refererar till `Microsoft.Quantum.Sdk` ). Med det här kommandot kompileras `.qs` filer i mappen som innehåller `.csproj` (och undermapparna). Det kommer också att läsa in alla paket som refereras via `PackageReference` eller Q# projekt som refereras till via `ProjectReference` i `.csproj` filen. 

Som exempel simulerar följande celler en Q# åtgärd från ett externt projekt, där projekt Sök vägen refereras till i förhållande till den aktuella mappen:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

Om du vill läsa in externa paket som innehåller Q# kod använder du [ `%package` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
När du läser in ett paket blir det också tillgängligt eventuella anpassade Magic-kommandon eller Visa kodare som finns i alla sammansättningar som ingår i paketet.

Om du vill läsa in externa paket eller Q# projekt på Notebook intialization-tid, se till att mappen Notebook innehåller en `.csproj` fil som refererar till `Microsoft.Quantum.Sdk` . I `.csproj` lägger du till egenskapen `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` i `<PropertyGroup>` . Detta instruerar mig Q# att rekursivt läsa in alla `ProjectReference` eller `PackageReference` objekt som finns i den `.csproj` bärbara datorns inläsnings tid.

Här är till exempel en enkel `.csproj` fil som gör att jag Q# kan läsa in `Microsoft.Quantum.Chemistry` paketet automatiskt:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> För närvarande krävs den här anpassade `<IQSharpLoadAutomatically>` egenskapen av Q# Jupyter Notebook värdar, men i framtiden kan detta bli standard beteendet för en `.csproj` fil som finns i samma mapp som Notebook-filen.

> [!NOTE]
> För närvarande `<QsharpCompile>` ignoreras inställningen i av `.csproj` Q# Jupyter Notebook värdar, och alla `.qs` filer i mappen i `.csproj` (inklusive undermappar) läses in och kompileras. Stöd för `.csproj` inställningar kommer att förbättras i framtiden (se [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) för mer information).
