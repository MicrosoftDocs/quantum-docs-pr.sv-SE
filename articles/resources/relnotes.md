---
title: Viktig information för Quantum Development Kit
description: Lär dig mer om de senaste uppdateringarna i förhandsversionen av Microsoft Quantum Development Kit.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 869d13acd5cb82fac73be514d6622a616ddceb54
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866680"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Viktig information för Microsoft Quantum Development Kit

Den här artikeln innehåller information om varje version av Quantum Development Kit.

Installationsanvisningar finns i [installationsguiden](xref:microsoft.quantum.install).

Uppdateringsanvisningar finns i [uppdateringsguiden](xref:microsoft.quantum.update).


## <a name="version-01220072031"></a>Version 0.12.20072031

*Utgivnings datum: 21 juli 2020*

Den här versionen innehåller följande:

- Öppna namn områden i Q# antecknings böcker är nu tillgängliga för alla framtida cell körningar. Detta gör att du till exempel kan öppna namn områden en gång i en cell överst i antecknings boken, i stället för att behöva öppna relevanta namn områden i varje kod cell. Ett nytt `%lsopen` magisk-kommando visar en lista över namn områden som har öppnats för tillfället.

Se den fullständiga listan med stängda pull för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [körning](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01220070124"></a>Version 0.12.20070124

*Utgivnings datum: den 2 juli, 2020*

Den här versionen innehåller följande:

- Nytt `qdk-chem` verktyg för att konvertera äldre elektroniska struktur problem serialiserade format (t. ex.: FCIDUMP) till [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- Nya funktioner och åtgärder i [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) namn området för sammanhängande tillämpning av klassiska Oracle med hjälp av omvandlings-och dekompositions syntes algoritmer.
- Jag Q# tillåter nu argument till `%simulate` , `%estimate` och andra Magic-kommandon. Mer information finns i [ `%simulate` kommando referensen för Magic](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- Nya fas visnings alternativ i I Q# . Mer information finns i [ `%config` kommando referensen för Magic](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- I Q# och `qsharp` python-paketet tillhandahålls nu via Conda-paket ([qsharp](https://anaconda.org/quantum-engineering/qsharp) och [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) för att förenkla lokal installation av Q# Jupyter-och python-funktioner till en Conda-miljö. Mer information finns i [ Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) och [ Q# med python](xref:microsoft.quantum.install.python) -installations guider.
- När du använder simulatorn behöver qubits inte längre vara i ⟩-läget | 0 vid lanseringen, men kan återställas automatiskt om de mättes omedelbart innan de släpps.
- Uppdateringar för att göra det enklare för Q# användare att använda biblioteks paket med olika QDK-versioner, vilket kräver att endast större & lägre versions nummer matchar i stället för exakt samma version
- Borttagen inaktuell `Microsoft.Quantum.Primitive.*` namnrymd
- Flyttade åtgärder:
  - `Microsoft.Quantum.Intrinsic.Assert`är nu`Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb`är nu`Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Felkorrigeringar 

Se den fullständiga listan med stängda pull för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [körning](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0112006403"></a>Version 0.11.2006.403

*Utgivningsdatum: 4 juni 2020*

Den här versionen åtgärdar en bugg som påverkar Q# projekt kompilering.

## <a name="version-0112006207"></a>Version 0.11.2006.207

*Utgivningsdatum: 3 juni 2020*

Den här versionen innehåller följande:

- Q#bärbara datorer och python-värdar fungerar inte längre när det finns en Q# Start punkt
- Uppdateringar av [standardbiblioteket](xref:microsoft.quantum.libraries.standard.intro) för användning av åtkomstmodifierare
- Kompilatorn tillåter nu infogning av omskrivningssteg mellan inbyggda återskrivningssteg
- Flera inaktuella funktioner och åtgärder har tagits bort enligt det schema som beskrivs i våra [API-principer](xref:microsoft.quantum.contributing.api-design). Q#program och bibliotek som skapar utan varningar i version 0.11.2004.2825 kommer att fortsätta att fungera oförändrade.

Se den fullständiga listan med stängda pull för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [körning](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

> [!NOTE]
> Den här versionen innehåller en bugg som påverkar Q# projekt kompilering. Vi rekommenderar att du uppgraderar till en nyare version.

## <a name="version-01120042825"></a>Version 0.11.2004.2825

*Utgivningsdatum: 30 april 2020*

Den här versionen innehåller följande:

- Nytt stöd för Q# kommando rads program som inte längre kräver en C#-eller python-värd fil. Mer information om att komma igång med Q# kommando rads program finns [här](xref:microsoft.quantum.install.standalone).
- Uppdateringen av snabbstarten för att skapa en kvantgenerator för slumptal gör att det inte längre behövs en C#- eller Python-värdfil. Se den uppdaterade  [snabbstarten](xref:microsoft.quantum.quickstarts.qrng)
- Prestanda förbättringar i Q# Docker-avbildningar

> [!NOTE]
> Q#kommando rads program som använder det nya [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) attributet kan för närvarande inte anropas från python-eller .net-värd program.
> Mer information finns i samverkansguiderna för [Python](xref:microsoft.quantum.install.python) och [.NET](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Version 0.11.2003.3107

*Utgivningsdatum: 31 mars 2020*

Den här versionen innehåller några mindre felkorrigeringar för version 0.11.2003.2506.

## <a name="version-01120032506"></a>Version 0.11.2003.2506

*Utgivningsdatum: 26 mars 2020*

Den här versionen innehåller följande:

- Nytt stöd för åtkomst modifierare i Q# , mer information finns i [fil strukturer](xref:microsoft.quantum.guide.filestructure)
- Uppdaterades till .NET Core SDK 3.1

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Version 0.10.2002.2610

*Utgivningsdatum: 27 februari 2020*

Den här versionen innehåller följande:

- Nytt Quantum Machine Learning-bibliotek, mer information finns på vår [QML-dokumentationssida](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)
- Jag Q# har fel korrigeringar, vilket resulterar i upp till en prestanda ökning på 10 20x vid inläsning av NuGet-paket

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Version 0.10.2001.2831

*Utgivningsdatum: 29 januari 2020*

Den här versionen innehåller följande:

- Nytt Microsoft.Quantum.SDK NuGet-paket som kommer att ersätta Microsoft.Quantum.Development.Kit NuGet-paketet när nya projekt skapas. Microsoft.Quantum.Development.Kit NuGet-paketet kommer även fortsättningsvis att stödjas för befintliga projekt. 
- Stöd för Q# kompilator tillägg som aktive ras av den nya Microsoft. Quantum. SDK-NuGet paketet. mer information finns i [dokumentationen på GitHub](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), [compiler-exemplet](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) och [ Q# dev-bloggen](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- Stöd för .NET Core 3.1 har lagts till. Vi rekommenderar starkt att ha version 3.1.100 installerat, eftersom om du skapar med äldre .NET Core SDK-versioner kan problem uppstå
- Nya kompilatoromvandlingar finns tillgängliga under Microsoft.Quantum.QsCompiler.Experimental
- Nya funktioner för att exponera utmatnings tillstånds vektorer som HTML i IQ#
- Stöd har lagts till för EstimateFrequencyA till Microsoft.Quantum.Characterization för Hadamard- och SWAP-tester
- AmplitudeAmplification-namnrymden använder nu Q# format guiden

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Version 0.10.1912.0501

*Utgivningsdatum: 5 december 2019*

Den här versionen innehåller följande:

- Nytt testattribut för Q# enhets testning, se uppdaterad API-dokumentation [här](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) och uppdaterade test & fel söknings guide [här](xref:microsoft.quantum.guide.testingdebugging)
- Stack spårning har lagts till i händelse av ett Q# program körnings fel
- Stöd för brytpunkter i Visual Studio Code på grund av en uppdatering i [OmniSharp C# Visual Studio Code-tillägget](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Version 0.10.1911.1607

*Utgivningsdatum: 17 november 2019*

Den här versionen innehåller följande:

- Prestandakorrigering för [Quantum Katas](https://github.com/Microsoft/QuantumKatas)- och Jupyter-notebook-filer

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Version 0.10.1911.307

*Utgivningsdatum: 1 november 2019*

Den här versionen innehåller följande:

- Uppdateringar av Visual Studio Code- och Visual Studio-tillägg som distribuerar språkservern som en fristående körbar fil, vilket eliminerar beroendet av .NET Core SDK-versionen  
- Migrering till .NET Core 3.0
- Banbrytande ändring av Microsoft.Quantum.Simulation.Core.IOperationFactory med den nya `Fail`-metoden. Den påverkar endast anpassade simulatorer som inte utökar SimulatorBase. Mer information finns i [Visa pull-begäran i GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nytt stöd för inaktuella attribut

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Version 0.9.1909.3002

*Utgivningsdatum: 30 september 2019*

Den här versionen innehåller följande:

- Nytt stöd för Q# kod komplettering i Visual studio 2019 (versioner 16,3 & senare) & Visual Studio Code
- Ny [Quantum Kata](https://github.com/Microsoft/QuantumKatas) för kvantadderare

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Version 0.9 (*PackageReference 0.9.1908.2902*)

*Utgivningsdatum: 29 augusti 2019*

Den här versionen innehåller följande:

- Nytt stöd för [conjugation-instruktioner](xref:microsoft.quantum.guide.operationsfunctions#conjugations) iQ#
- Nya kodåtgärder i kompilatorn, till exempel ”replace with” (ersätt med), ”add documentation” (lägg till dokumentation) och uppdatering av objekt i enkla matriser
- Lade till installationsmall och nya projektkommandon i Visual Studio Code-tillägget
- Lade till nya varianter av ApplyIf-kombinatorn, till exempel [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- Ytterligare [Quantum Katas](https://github.com/Microsoft/QuantumKatas) har konverterats till Jupyter-notebook-filer
- Visual Studio-tillägget kräver nu Visual Studio 2019

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilator](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) och [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Ändringarna sammanfattas här, och det finns anvisningar för hur du uppgraderar dina befintliga program.  Läs mer om de här ändringarna på [ Q# dev-bloggen](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Version 0.8 (*PackageReference 0.8.1907.1701*)

*Utgivningsdatum: 12 juli 2019*

Den här versionen innehåller följande:

- Nya indexeringsplatser för segmentering av matriser. Mer information finns i [språkreferensen](xref:microsoft.quantum.guide.expressions#array-slices).
- Du har lagt till Dockerfile som finns på [Microsoft container Registry](https://github.com/microsoft/ContainerRegistry), se [i- Q# lagringsplatsen för mer information](https://github.com/microsoft/iqsharp/blob/master/README.md)
- Icke-bakåtkompatibel ändring för [spårningssimulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro), uppdatering av konfigurationsinställningar, namnändringar; se [.NET API-webbläsaren för de uppdaterade namnen](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) och [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Version 0.7 (*PackageReference 0.7.1905.3109*)

*Utgivningsdatum: 31 maj 2019*

Den här versionen innehåller följande:
- tillägg till Q# språket, 
- uppdateringar av kemibiblioteket 
- ett nytt numeriskt bibliotek.

Se den fullständiga listan med stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) och [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Ändringarna sammanfattas här, och det finns anvisningar för hur du uppgraderar dina befintliga program.  Läs mer om de här ändringarna på [ Q# dev-bloggen](https://devblogs.microsoft.com/qsharp).

### <a name="no-locq-language-syntax"></a>Q#språksyntax
Den här versionen lägger till ny Q# språksyntax:
* Lägger till namngivna objekt för [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types).  
* Användardefinierade konstruktorer kan nu användas som funktioner.
* Lägger till stöd för [kopiera och uppdatera](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) samt [tillämpa och omtilldela](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) i användardefinierade typer.
* Korrigeringsblock för [upprepas tills det lyckas](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)-loopar är nu valfria.
* Vi stöder nu while-loopar i funktioner (inte i åtgärder).

### <a name="library"></a>Bibliotek 

Den här versionen lägger till ett numeriskt bibliotek: Lär dig mer om hur du [använder det nya numeriska biblioteket](xref:microsoft.quantum.numerics.usage) och prova [nya exempel](https://github.com/microsoft/quantum/tree/master/Numerics).  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Den här versionen omorganiserar, utökar och uppdaterar kemibiblioteket:
* Förbättrar modulariteten för komponenter, utökningsbarhet och allmän rensning bland koden.  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Lägger till stöd för [vågfunktioner med multireferens](xref:microsoft.quantum.chemistry.concepts.multireference), både vågfunktioner med sparse-multireferens och enkelt kopplat kluster.  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Tack!) [1QBit](https://1qbit.com)-deltagare ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energiutvärdering med hjälp av variations-ansatz. [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Uppdaterar [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)-schemat till ny [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2) och lade till specifikation för enkelt kopplat kluster. [Problem #65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Lägger till Python-interoperabilitet i funktionerna i kemibiblioteket. Prova detta [exempel](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Problem nr 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Version 0.6.1905

*Utgivningsdatum: 3 maj 2019*

Den här versionen innehåller följande:
- gör ändringar i Q# språket, 
- omstrukturerar Quantum Development Kit-biblioteken 
- lägger till nya exempel och 
- korrigerar buggar.  Flera stängda PR:er för [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) och [exempel](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Ändringarna sammanfattas här, och det finns anvisningar för hur du uppgraderar dina befintliga program.  Du kan läsa mer om de här ändringarna på devblogs.microsoft.com/qsharp.

### <a name="no-locq-language-syntax"></a>Q#språksyntax
Den här versionen lägger till ny Q# språksyntax:
* Lägger till ett [kort sätt att uttrycka specialiseringar av kvantåtgärder](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (kontroll och angränsande) med `+`-operatorer.  Den gamla syntaxen är inaktuell.  Program som använder den gamla syntaxen (till exempel `: adjoint`) fortsätter att fungera, men det genereras en varning vid kompileringstid.  
* Lägger till en ny operator för [kopiera-och-uppdatera](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, som kan användas för att uttrycka skapande av matris som en ändring av en befintlig matris.
* Lägg till den vanliga [”tillämpa och uppdatera”-instruktionen](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), till exempel `+=`, `w/=`.
* Lägger till ett sätt att ange ett kort namn för namnrymder i [öppna direktiv](xref:microsoft.quantum.guide.filestructure#open-directives).

Från och med den här versionen tillåter vi inte längre att ett matriselement anges på vänster sida av en set-instruktion.  Detta beror på att den syntaxen antyder att matriser är föränderliga, när resultatet av den här åtgärden i själva verket alltid har varit skapandet av en ny matris med ändringen.  I stället genereras ett kompileringsfel med ett förslag om att använda den nya kopiera och uppdatera-operatorn `w/` för att åstadkomma samma resultat.  

### <a name="library-restructuring"></a>Omstrukturering av bibliotek
Den här versionen omorganiserar biblioteken så att de kan växa på ett konsekvent sätt:
* Byter namn på namnrymden Microsoft.Quantum.Primitive till Microsoft.Quantum.Intrinsic.  De här åtgärderna implementeras av måldatorn.  Namnrymden Microsoft.Quantum.Primitive är inaktuell.  En varning vid runtime aviserar när program anropar åtgärder och funktioner med hjälp av inaktuella namn.

* Byter namn på paketet Microsoft.Quantum.Canon till Microsoft.Quantum.Standard.  Det här paketet innehåller namn områden som är gemensamma för de flesta Q# program.  Det här omfattar:  
    - Microsoft.Quantum.Canon för gemensamma åtgärder
    - Microsoft.Quantum.Arithmetic för allmänna aritmetiska åtgärder
    - Microsoft.Quantum.Preparation för åtgärder som används till att förbereda kvantbittillstånd
    - Microsoft.Quantum.Simulation för simuleringsfunktioner

I och med den här ändringen kan program som innehåller en enda ”open”-instruktion för namnrymden Microsoft.Quatum.Canon drabbas av kompileringsfel om programmet refererar till åtgärder som har flyttats till de andra tre nya namnrymderna.  Tillägg av ytterligare open-instruktioner för de tre nya namnrymderna är ett enkelt sätt att lösa det här problemet.  

* Flera namnrymder har gjorts inaktuella allt eftersom åtgärderna i dem har omorganiserats till andra namnrymder. Program som använder dessa namnrymder kommer fortsätta att fungera, och en varning vid kompileringstid anger den namnrymd där åtgärden definieras.  

* Namnrymden Microsoft.Quantum.Arithmetic har normaliserats till att använda den användardefinierade typen <xref:microsoft.quantum.arithmetic.littleendian>. Använd funktionen [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) när det behövs för att konvertera till little endian.  

* Namnen på flera callables (Functions och Operations) har ändrats så att de överensstämmer med [ Q# format guiden](xref:microsoft.quantum.contributing.style).  De gamla anropningsbara namnen är inaktuella.  Program som använder de gamla anropningsbara elementen fortsätter att fungera med en varning vid kompileringstid. 

### <a name="new-samples"></a>Nya exempel

Vi har lagt till ett [exempel på användning Q# med F # driv rutin](https://github.com/Microsoft/Quantum/pull/164).  

**Tack!** till följande deltagare i vår öppna kodbas på http://github.com/Microsoft/Quantum. De här bidragen lägger till betydligt större exempel på Q# kod:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle-funktionssyntes. [PR #135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrerar befintliga projekt till 0.6.1905.

Se [installationsguiden](xref:microsoft.quantum.install) för uppdatering av QDK.
  
Om du har befintliga Q# projekt från version 0,5 av Quantum Development Kit följer du stegen nedan för att migrera projekten till den senaste versionen.

    1. Projekt behöver uppgraderas i rätt ordning.  Om du har en lösning med flera projekt uppdaterar du varje projekt i den ordning som de refereras till.
    2. Från en kommandorad kör du `dotnet clean` för att ta bort alla befintliga binärfiler och mellanliggande filer.
    3. I ett redigeringsprogram redigerar du filen .csproj: ändra versionen av alla ”Microsoft.Quantum” `PackageReference` till version 0.6.1904, och ändra paketnamnet ”Microsoft.Quantum.Canon” till ”Microsoft.Quantum.Standard”, till exempel:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. Från kommandoraden kör du det här kommandot: `dotnet msbuild`  
    5. När du har kört detta kan du fortfarande behöva åtgärda fel manuellt på grund av de ändringar som anges ovan.  I många fall rapporteras dessa fel även av IntelliSense i Visual Studio eller Visual Studio Code.
        - Öppna rotmappen för projektet eller den innehållande lösningen i Visual Studio 2019 eller Visual Studio Code.
        - När du har öppnat en. QS-fil i redigeraren bör du se utdata för Q# språk tillägget i fönstret utdata.
        - När projektet har lästs in (vilket anges i utdatafönstret) öppnar du varje fil och åtgärdar alla återstående problem manuellt.

> [!NOTE]
> * För version 0.6 har den språkserver som ingår i Quantum Development Kit inte stöd för flera arbetsytor.
> * För att du ska kunna arbeta med ett projekt i Visual Studio Code öppnar du den rotmapp som innehåller själva projektet och alla refererade projekt.   
> * För att du ska kunna arbeta med en lösning i Visual Studio behöver alla projekt som finns i lösningen finnas i samma mapp som lösningen eller i någon av dess undermappar.  
> * Referenser mellan projekt som migrerats till 0.6 och senare samt projekt som använder äldre paketversioner stöds **inte**.

## <a name="version-051904"></a>Version 0.5.1904

*Utgivningsdatum: 15 april 2019*

Den här versionen innehåller buggkorrigeringar.


## <a name="version-051903"></a>Version 0.5.1903

*Utgivningsdatum: 27 mars 2019*

Den här versionen innehåller följande:

- Lägger till stöd för Jupyter Notebook, vilket ger ett bra sätt att lära sig mer om Q# .  [Kolla in de nya Jupyter Notebook-exemplen och lär dig att skriva egna notebook-filer](xref:microsoft.quantum.install). 

- Lägger till aritmetik för heltalsadderare i Quantum Canon-biblioteket.  Se även en Jupyter-notebook-fil som [beskriver hur du använder de nya heltalsadderarna](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Buggkorrigering för DumpRegister-problem som rapporterats av communityn ([#148](https://github.com/Microsoft/Quantum/issues/148)).

- Lade till möjligheten att returnera inifrån en [using-instruktion](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- Omarbetade [komma igång-guiden](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Version 0.5.1902

*Utgivningsdatum: 27 februari 2019*

Den här versionen innehåller följande:

- Lägger till stöd för en plattformsoberoende Python-värd.  `qsharp`Paketet för python gör det enkelt att simulera Q# åtgärder och funktioner i python. Läs mer om [Python-interoperabilitet](xref:microsoft.quantum.install). 

- Visual Studio- och Visual Studio Code-tilläggen har nu stöd för namnbyte av symboler (till exempel funktioner och åtgärder).

- Visual Studio-tillägget kan nu installeras i Visual Studio 2019.

## <a name="version-041901"></a>Version 0.4.1901

*Utgivningsdatum: 30 januari 2019*

Den här versionen innehåller följande:

- lägger till stöd för en ny primitiv typ, BigInt, som representerar ett heltal med tecken av godtycklig storlek.  Läs mer om [BigInt-typen](xref:microsoft.quantum.guide.types).
- lägger till en ny Toffoli-simulator, en specialiserad snabb simulator som kan simulera X, CNOT och multikontrollerade X-kvantåtgärder med mycket stora antal kvantbitar.  Läs mer om [Toffoli-simulatorn](xref:microsoft.quantum.machines.toffoli-simulator).
- lägger till en enkel resurs uppskattning som uppskattar de resurser som krävs för att köra en specifik instans av en Q# åtgärd på en Quantum-dator.  Läs mer om [resursuppskattningsverktyget](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Version 0.3.1811.2802

*Utgivningsdatum: 28 november 2018*

Trots att vårt VS Code-tillägg inte använde det flaggades det och togs bort från marknadsplatsen under den [rensning av tillägg](https://code.visualstudio.com/blogs/2018/11/26/event-stream) som hade att göra med NPM-paketet `event-stream`. Den här versionen tar bort alla runtime-beroenden som skulle kunna göra att tillägget utlöser röda flaggor.

Om du tidigare hade installerat tillägget behöver du installera det igen genom att gå till [Microsoft Quantum Development Kit för Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode)-tillägget på Visual Studio Marketplace och trycka på Installera. Vi beklagar besväret.


## <a name="version-0318111511"></a>Version 0.3.1811.1511

*Utgivningsdatum: 20 november 2018*

Den här versionen åtgärdar en bugg som hindrade vissa användare från att läsa in Visual Studio-tillägget.

## <a name="version-031811203"></a>Version 0.3.1811.203

*Utgivningsdatum: 2 november 2018*

Den här versionen innehåller några buggkorrigeringar, inklusive:

* Om `DumpMachine` anropas kunde simulatorns tillstånd ändras i vissa situationer.
* Tog bort kompileringsvarningar vid kompilering av projekt med hjälp av en tidigare .NET Core-version än 2.1.403.
* Rensning av dokumentationen, särskilt de knappbeskrivningar som visas när muspekaren hovras i VS Code eller Visual Studio.

## <a name="version-0318102508"></a>Version 0.3.1810.2508

*Utgivningsdatum: 29 oktober 2018*

Den här versionen innehåller nya språkfunktioner och en förbättrad utvecklarupplevelse:

* Den här versionen innehåller en språk Server för Q# , samt klient integreringar för Visual Studio och Visual Studio Code. Detta möjliggör en ny uppsättning IntelliSense-funktioner samt live-feedback för skrivning i form av vågiga understrykningar under fel och varningar. 
* Den här uppdateringen förbättrar avsevärt de diagnostiska meddelandena i allmänhet, med enkel navigering till och exakta intervall för diagnostik samt ytterligare information i den hovringsinformation som visas.
* Q#Språket har utökats på ett sätt som kombinerar hur utvecklare kan utföra vanliga åtgärder och nya förbättringar av språkfunktionerna för att kunna uttrycka den kraftfulla Quantum-beräkningen.  Det finns en fåtal Q# med den här versionen av det aktuella språket.   

Den här versionen innehåller även ett nytt kvantkemibibliotek:

* Kemibiblioteket innehåller nya funktioner för hamiltonsk simulering, däribland:
    - Trotter–Suzuki-integrerare med godtycklig jämn ordning för förbättrad simuleringsnoggrannhet.
    - Teknik för qubitiseringssimulering med kemispecifika optimeringar för reducering av $T$-gatens komplexitet.
* Ett nytt schema med öppen källkod, som kallas Broombridge Schema (en referens till det [landmärke](https://en.wikipedia.org/wiki/Broom_Bridge) som firas som de hamiltonska värdenas födelseplats), introduceras för import och simulering av representationer av molekyler.
* Flera kemiska representationer som definieras med hjälp av Broombridge-schemat tillhandahålls.  Dessa modeller genererades av [NWChem](http://www.nwchem-sw.org/), ett verktyg för beräkningskemi med höga prestanda och öppen källkod.
* Självstudier och exempel beskriver hur du använder kemibiblioteket och Broombridge-datamodellerna för att:
    - Konstruera enkla hamiltonska värden med hjälp av kemibiblioteket
    - Visualisera grundtillståndets energier och excitationsenergier för litiumhydrid med hjälp av fasberäkning.
    - Utför resursuppskattningar för kvantkemisimulering.
    - Uppskatta energinivåer för molekyler som representeras av Broombridge-schemat.
* Dokumentationen beskriver hur du använder NWChem för att generera ytterligare kemiska modeller för Quantum-simulering med Q# .

Läs mer om [kemibiblioteket för Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Med det nya kemibiblioteket delar vi in biblioteken i en ny GitHub-lagringsplats, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Exemplen finns kvar på lagringsplatsen [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Vi välkomnar bidrag till båda dessa!

Den här versionen innehåller buggkorrigeringar och funktioner för problem som rapporterats av communityn:

* IntelliSense för Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* .qs-filer ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Förbättrar felmeddelandet när klammerparenteser förkortas i en if-instruktion ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Stöd för tuppeldekonstruktion vid föränderlig (om)bindning ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Fel vid körning av tillhandahållen BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI visar stora toppar ibland ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Bidrag från communityn

**Tack!** till följande deltagare i vår öppna kodbas på http://github.com/Microsoft/Quantum. De här bidragen lägger till betydligt större exempel på Q# kod:

* Rolf Huisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): förbättrade upplevelsen för QASM/ Q# utvecklare genom att skapa en QASM till Q# Translator. [PR #58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Bidrog med ett exempel som implementerar CHSH-spelet, ett kvantspel som handlar om icke-lokalitet.  [PR #84](https://github.com/Microsoft/Quantum/pull/84).

Vi tackar även Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) och Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) för deras arbete med att förbättra innehållet för oss alla, med dokumentation samt korrigering av stavfel och skrivfel. 

## <a name="version-021809701"></a>Version 0.2.1809.701

*Utgivningsdatum: 10 september 2018*

Den här versionen innehåller buggkorrigeringar för problem som rapporterats av communityn. Detta omfattar:

* Shift-operatorn kan inte användas ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` misslyckas i `QCTraceSimulator` vid utskrift till konsolen ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Tillåt allokering av 0 kvantbitar ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` kräver explicit anrop av Complex() ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* `Measure`-åtgärden returnerar alltid `One` i macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Tack! 

## <a name="version-0218063001"></a>Version 0.2.1806.3001

*Utgivningsdatum: 30 juni 2018*

De här versionerna är bara en snabb korrigering för [problem #48 rapporterad på GitHub](https://github.com/Microsoft/Quantum/issues/48) ( Q# kompileringen Miss lyckas om användar namnet innehåller ett tomt utrymme). Följ samma uppdateringsinstruktioner som för `0.2.1806.1503` med motsvarande ny version (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Version 0.2.1806.1503

*Utgivningsdatum: 22 juni 2018*

Den här versionen innehåller flera bidrag från communityn samt en förbättrad felsökningsupplevelse och bättre prestanda.  Mer specifikt:

* Prestandaförbättringar för både små och stora simuleringar för QuantumSimulator-måldatorn.
* Förbättrade felsökningsfunktioner.
* Bidrag från communityn vad gäller felkorrigeringar, nya hjälpfunktioner, åtgärder och nya exempel.

### <a name="performance-improvements"></a>Prestandaförbättringar

Den här uppdateringen innehåller betydande prestandaförbättringar för simulering av stora och små antal kvantbitar för alla måldatorer.  Den här förbättringen märks tydligt med H<sub>2</sub>-simuleringen, som är ett standardexempel i Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Förbättrade felsökningsfunktioner

Den här uppdateringen lägger till nya felsökningsfunktioner:
* Lade till två nya åtgärder, @"microsoft.quantum.extensions.diagnostics.dumpmachine" och @"microsoft.quantum.extensions.diagnostics.dumpregister", som utvärderar vågfunktionsinformation om målkvantdatorn vid en tidpunkt.  
* I Visual Studio visas sannolikheten för att mäta en $\ket{1}$ på en enda kvantbit automatiskt i felsökningsfönstret för QuantumSimulator-måldatorn.
* I Visual Studio har visningen av variabelegenskaper i felsökningsfönstren **Autos** och **Locals** förbättrats. 

Läs mer om [testning och felsökning](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Bidrag från communityn

Q#Programmerare community växer och vi är älskar att se att den första användaren har bidragit med bibliotek och exempel som har skickats till vår Open Code-bas på http://github.com/Microsoft/quantum .  **Ett stort tack!** till följande deltagare:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): bidrog med ett exempel som definierar en transformationsbaserad metod för logiksyntes som konstruerar Toffoli-nätverk för att implementera en viss permutation. Koden skrivs helt och hållet i Q# Functions och Operations.  [PR #41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): Microsoft MVP Rolf-Huisman bidrog ett exempel som genererar platt QASM kod från Q# kod för en begränsad klass av program som inte har ett klassiskt kontroll flöde och begränsade Quantum-åtgärder. [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): hjälpte till att förbättra vår kodbas genom att skicka in en biblioteksfunktion för kontrollerade åtgärder. [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): åtgärdade @"microsoft.quantum.canon.quantumphaseestimation" och skapade nya enhetstester.  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): rensade upp i teleporteringsexemplet genom att se till att QuantumSimulator-instansen tas bort. [PR #20](https://github.com/Microsoft/Quantum/pull/20)

Och ett stort **tack!** till dessa Microsoft-programvaruutvecklare från Commercial Engineering Services-teamdeltagarna, som införde värdefulla ändringar i vår dokumentation under Hackathon.  Deras ändringar förbättrade tydligheten och introduktionsupplevelsen avsevärt för oss alla:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Uppdatera befintliga projekt

Den här versionen är fullständigt bakåtkompatibel. Du behöver bara uppdatera NuGet-pakages i dina projekt till version `0.2.1806.1503-preview` och göra ett **fullständigt återskapande** så att alla mellanliggande filer återskapas.

I Visual Studio följer du de vanliga anvisningarna för hur du [uppdaterar ett paket](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Uppdatera projektmallar för kommandoraden genom att köra följande kommando:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

När du har kört det här kommandot använder alla nya projekt som skapats med hjälp av `dotnet new <project-type> -lang Q#` automatiskt den här versionen av Quantum Development Kit.

Om du vill uppdatera ett befintligt projekt till att använda den senaste versionen kör du följande kommando inifrån katalogen för varje projekt:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Om ett befintligt projekt också använder XUnit-integrering för enhetstestning kan ett liknande kommando användas för att uppdatera även det paketet:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Beroende på vilken version av XUnit som testprojektet använder kan du även behöva uppdatera XUnit till 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Efter uppdateringen ska du ta bort alla temporära filer som genererats av den tidigare versionen genom att göra följande:
```
dotnet clean 
```

### <a name="known-issues"></a>Kända problem

Inga ytterligare kända problem att rapportera.


## <a name="version-0218022202"></a>Version 0.2.1802.2202

*Utgivningsdatum: 26 februari 2018*

Den här versionen ger stöd för utveckling på fler plattformar, språksamverkan samt prestandaförbättringar. Mer specifikt:

- Stöd för macOS- och Linux-baserad utveckling. 
- .NET Core-kompatibilitet, däribland stöd för Visual Studio Code på olika plattformar.
- En fullständig licens för öppen källkod för Quantum Development Kit-bibliotek.
- Förbättrad simulatorprestanda för projekt som kräver 20 eller fler kvantbitar.
- Samverkan med språket Python (förhandsversion är tillgänglig i Windows).

### <a name="net-editions"></a>.NET-utgåvor

.NET-plattformen är tillgänglig som två olika utgåvor, .NET Framework som medföljer Windows samt .NET Core med öppen källkod som är tillgänglig i Windows, macOS och Linux.
I den här versionen tillhandahålls de flesta delar av Quantum Development Kit som bibliotek för .NET Standard, den uppsättning av klasser som är gemensamma för både Framework och Core.
Dessa bibliotek är därför kompatibla med de senaste versionerna av endera .NET Framework eller .NET Core.

För att se till att projekt som skrivits med hjälp av Quantum Development Kit är så portabla som möjligt rekommenderar vi därför att biblioteksprojekt som skrivs med hjälp av Quantum Development Kit riktas till .NET Standard medan konsolprogram riktas till .NET Core.
Eftersom tidigare versioner av Quantum Development Kit bara hade stöd för .NET Framework kan du behöva migrera dina befintliga projekt. Information om hur du gör det finns nedan.

### <a name="project-migration"></a>Projektmigrering

Projekt som skapats med tidigare versioner av Quantum Development Kit fungerar fortfarande, så länge du inte uppdaterar de NuGet-paket som används i dem. Om du vill migrera befintlig kod till den nya versionen utför du följande steg:
1. Skapa ett nytt .NET Core-projekt med hjälp av rätt typ av Q# projekt mal len (program, bibliotek eller test projekt).
2. Kopiera befintliga .qs- och .cs/.fs-filer från det gamla projektet till det nya projektet (via Lägg till > Befintligt objekt). Kopiera inte filen AssemblyInfo.cs.
3. Skapa och kör det nya projektet.

Observera att åtgärden RandomWalkPhaseEstimation från namnrymden Microsoft.Quantum.Canon flyttades till namnrymden Microsoft.Research.Quantum.RandomWalkPhaseEstimation på lagringsplatsen [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Kända problem

- `--filter`Alternativet att inte `dotnet test` fungera korrekt för tester som skrivits i Q# .
  Därför kan enskilda enhetstester inte köras i Visual Studio Code. Vi rekommenderar att du använder `dotnet test` på kommandoraden för att köra alla tester på nytt.

## <a name="version-0118011707"></a>Version 0.1.1801.1707

*Utgivningsdatum: 18 januari 2018*

Den här versionen åtgärdar vissa problem som rapporterats av communityn. Det gäller följande:

- Simulatorn fungerar nu med tidiga icke-AVX-aktiverade CPU:er.
- De regionala decimal inställningarna kommer inte Q# att orsaka att parsern fungerar.
- Den primitiva åtgärden `SignD` returnerar nu `Int` i stället för `Double`.


## <a name="version-011712901"></a>Version 0.1.1712.901

*Utgivningsdatum: 11 december 2017*

### <a name="known-issues"></a>Kända problem

#### <a name="hardware-and-software-requirements"></a>Krav på maskinvara och programvara

- Den simulator som ingår i Quantum Development Kit kräver en 64-bitars installation av Microsoft Windows för att kunna köras.
- Microsofts kvantsimulator, som installeras med Quantum Development Kit, använder Advanced Vector Extensions (AVX) och kräver en AVX-aktiverad CPU. Intel-processorer som levererades under Q1 2011 (Sandy Bridge) eller senare har stöd för AVX. Vi utvärderar support för tidigare CPU:er och kan komma att meddela mer information vid ett senare tillfälle.

#### <a name="project-creation"></a>Projektskapande

- När du skapar en lösning (. SLN) som ska använda Q# måste lösningen vara en katalog som är högre än varje projekt (. CSPROJ) i lösningen. När du skapar en ny lösning kan du göra detta genom att markera kryssrutan ”Skapa katalog för lösning” i dialogrutan ”Nytt projekt”. Om du inte gör det måste NuGet-paket för Quantum Development Kit installeras manuellt.

#### Q#

- IntelliSense visar inte korrekta fel för Q# kod. Se till att du visar build-fel i Visual Studio-Fellista för att se rätt Q# fel. Observera också att Q# fel inte visas förrän du har gjort en version.
- Användning av en föränderlig matris i en partiell tillämpning kan leda till oväntat beteende.
- Bindning av en oföränderlig matris till en föränderlig matris (a = b, där b är en föränderlig matris) kan leda till oväntat beteende.
- Profilering, kod täckning och andra VS-plugin-program kan inte alltid räkna Q# rader och block på ett korrekt sätt.
- Q#Kompilatorn verifierar inte interpolerade strängar. Det är möjligt att skapa C#-kompileringsfel genom att stava fel i variabel namn eller använda uttryck i Q# interpolerade strängar.

#### <a name="simulation"></a>Simulering

- Quantum Simulator använder OpenMP för att parallellisera den linjära algebra som krävs. Som standard använder OpenMP alla tillgängliga maskinvarutrådar, vilket innebär att program med små antal kvantbitar ofta körs långsamt eftersom den samordning som krävs vida överstiger det faktiska arbetet. Du kan åtgärda detta genom att ange miljövariabeln OMP_NUM_THREADS till en liten siffra. Som en mycket generell tumregel räcker 1 tråd för upp till cirka 4 kvantbitar, och därefter kan ytterligare en tråd införas per kvantbit. Detta beror dock starkt på din algoritm.

#### <a name="debugging"></a>Felsökning

- F11 (steg i) fungerar inte i Q# kod.
- Kod markering i Q# kod vid en Bryt punkt eller en paus i ett steg är ibland felaktigt. Rätt rad markeras, men ibland börjar och slutar markeringen vid fel kolumner på raden.

#### <a name="testing"></a>Testning

- Tester måste köras i 64-bitars läge. Om dina tester misslyckas med meddelandet BadImageFormatException går du till testmenyn och väljer Testinställningar > Standardprocessorarkitektur > x64.
- Vissa tester tar lång tid (möjligen upp till 5 minuter beroende på din dator) att köras. Detta är normalt eftersom vissa av dem använder fler än tjugo kvantbitar. Till exempel körs vår för närvarande största test på 23 kvantbitar.

#### <a name="samples"></a>Exempel

- På vissa datorer kan vissa små exempel köras långsamt såvida inte miljövariabeln OMP_NUM_THREADS anges till ”1”. Se även versionsanteckningen under ”Simulering”.

#### <a name="libraries"></a>Bibliotek

- Det finns ett underförstått antagande att kvantbitar som skickas till en åtgärd i olika argument är unika. Till exempel förutsätter alla biblioteksåtgärder (och alla simulatorer) att de två kvantbitar som skickas till en kontrollerad NOT är olika kvantbitar. Om den här regeln överträds kan det leda till oväntat beteende. Det går att testa för detta med hjälp av spårningssimulatorn för kvantdator.
- Funktionen Microsoft.Quantum.Bind fungerar kanske inte som förväntat i samtliga fall.
- I namnrymden Microsoft.Quantum.Extensions.Math returnerar funktionen SignD en Double i stället för en Int, även om den underliggande funktionen System.Math.Sign alltid returnerar ett heltal. Det är säkert att jämföra resultatet mot 1,0,-1,0 och 0,0, eftersom alla dessa doubles har exakta binära representationer.
