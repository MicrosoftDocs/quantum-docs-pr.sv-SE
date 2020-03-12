---
title: 'Design principer för Q # API'
description: 'Design principer för Q # API'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024210"
---
# <a name="q-api-design-principles"></a>Design principer för Q # API

## <a name="introduction"></a>Introduktion

Som ett språk och en plattform ger Q # användare möjlighet att skriva, köra, förstå och utforska Quantum-program.
För att användarna ska kunna utforma Q #-bibliotek följer vi en uppsättning design principer för API: er som vägleder våra design och hjälper oss att göra användbara bibliotek för den Quantum Development-gruppen.
Den här artikeln innehåller de här principerna och ger exempel på hur du kan använda dem när du utformar Q # API: er.

> [!TIP]
> Det här är ett ganska detaljerat dokument som hjälper dig att hjälpa till med biblioteks utveckling och djupgående biblioteks bidrag.
> Du kommer förmodligen att upptäcka det mest användbart om du skriver dina egna bibliotek i Q #, eller om du bidrar med större funktioner till [lagrings platsen för Q #-bibliotek](https://github.com/microsoft/QuantumLibraries).
>
> Å andra sidan rekommenderar vi att du börjar med [bidrags hand boken](xref:microsoft.quantum.contributing), om du vill lära dig att bidra till Quantum Development Kit.
> Om du vill ha mer allmän information om hur vi rekommenderar att du formaterar din Q #-kod kanske du är intresse rad av att checka ut [stil guiden](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Allmänna principer

**Nyckel princip:** Exponera API: er som placerar fokus på Quantum-program.

- ✅ väljer **du** Operations-och funktions namn som återspeglar den övergripande strukturen för algoritmer och program.
- ⛔️ visar **inte** API: er som främst fokuserar på lågnivå implementerings uppgifter.

**Nyckel princip:** Starta varje API-design med exempel användnings fall för att säkerställa att API: er är intuitiva att använda.

- ✅ **Se till att varje** komponent i ett offentligt API har ett motsvarande användnings fall, i stället för att försöka utforma för alla möjliga användnings områden från början.
    Sätt inte på olika offentliga API: er om de är användbara, men se till att varje del av ett API har ett *konkret* exempel där det är användbart.

  *Fler*
  - @"microsoft.quantum.canon.applytoeachca" kan användas som `ApplyToEachCA(H, _)` för att förbereda register i ett enhetligt befattnings tillstånd, en gemensam uppgift i många Quantum-algoritmer. Samma åtgärd kan också användas för många andra uppgifter i förberedelser, siffror och Oracle-baserade algoritmer.

- ✅ **skapa** nya API-design för kreativitet och workshop för att kontrol lera att de är intuitiva och uppfyller föreslagna användnings fall.

  *Fler*
  - Kontrol lera den aktuella Q-\# koden för att se hur nya API-Designer kan förenkla och klargöra befintliga implementeringar.
  - Granska föreslagna API-design med representanter för primära mål grupper.

**Nyckel princip:** Utforma API: er som stöder och uppmuntrar till läsbar kod.

- ✅ **Se till att koden** kan läsas av domän experter och icke-experter.
- ✅ **fokuserar** på effekterna av varje åtgärd och funktion inom algoritmen på hög nivå, med hjälp av dokumentationen för att gå in på implementerings informationen på lämpligt sätt.
- ✅ **ska** du följa den vanliga meddelande [guiden för Q\#](xref:microsoft.quantum.contributing.style) när så är tillämpligt.

**Nyckel princip:** Design-API: er som ska vara stabila och för att vidarebefordra kompatibilitet.

- ✅ **göra** inaktuella gamla API: er på ett smidigt sätt när du behöver bryta ändringar.

- ✅ **ge** "shim"-åtgärder och-funktioner som tillåter att befintlig användar kod fungerar korrekt under utfasningen.

  *Fler*
  - När du byter namn på en åtgärd som kallas `EstimateExpectation` till `EstimateAverage`, introducerar du en ny åtgärd som kallas `EstimateExpectation` som anropar den ursprungliga åtgärden med det nya namnet, så att befintlig kod kan fortsätta att fungera korrekt.

- ✅ **använder** attributet @"microsoft.quantum.core.deprecated" för att kommunicera utfasningar till användaren.

- ✅ när du byter namn på en åtgärd eller **funktion ska du ange det** nya namnet som en sträng Indatatyp som ska `@Deprecated`.

- ⛔️ **inte** att ta bort befintliga funktioner eller åtgärder utan en föråldrad period på minst sex månader för för hands versioner, eller minst två år för versioner som stöds.

## <a name="functions-and-operations"></a>Funktioner och åtgärder

**Nyckel princip:** se till att varje funktion och åtgärd har ett enda väldefinierat syfte inom API: et.

- ⛔️ visar **inte** funktioner och åtgärder som utför flera orelaterade uppgifter.

**Nyckel princip:** utforma funktioner och åtgärder för att vara så användbara som möjligt och för att förutse framtida behov.

- ✅ **har** design funktioner och åtgärder för att skapa bra med andra funktioner och åtgärder, både i samma API och i tidigare befintliga bibliotek.

  *Fler*
  - @"microsoft.quantum.canon.delay" åtgärden gör minimala antaganden om inaktuella indatatyper och kan därför användas för att fördröja program för båda åtgärderna i Q # standard-biblioteket eller som definieras av användarna.
    <!-- TODO: define bad example. -->

- ✅ **visar** rent deterministisk klassisk logik som funktioner i stället för åtgärder.

  *Fler*
  - En subrutin som kvadraterar sin flytt ALS indata kan skrivas deterministiskt och bör därför exponeras för användaren som `Squared : Double -> Double` snarare än som en åtgärd `Square : Double => Double`. Detta gör att subrutinen kan anropas på fler platser (t. ex. i andra funktioner) och ger användbar optimerings information till kompilatorn som kan påverka prestanda och optimeringar.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` och `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` skiljer sig åt i de garantier som gjorts med avseende på determinism. båda är användbara i olika situationer.
  - API-rutiner som transformerar tillämpningen av Quantum-åtgärder kan ofta utföras på ett deterministiskt sätt och kan därför göras tillgängliga som funktioner som `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.

- ✅ **DO** generaliserar indatatypen så mycket som rimligt för varje funktion och åtgärd, med hjälp av typ parametrar efter behov.

  *Fler*
  - `ApplyToEach` har typen `<'T>(('T => Unit), 'T[]) => Unit` snarare än den specifika typen av program `((Qubit => Unit), Qubit[]) => Unit`.

> [!TIP]
> Det är viktigt att förutse framtida behov, men det är också viktigt att lösa konkreta problem för dina användare.
> Den här nyckeln kräver sålunda alltid noggranna överväganden och balansering för att undvika att utveckla API: er "i själva fallet".

**Nyckel princip:** Välj indata och utdatatyper för funktioner och åtgärder som är förutsägbara och som kommunicerar syftet med ett anrop.

- ✅ **använder** tuple-typer för att logiskt gruppera indata och utdata som bara är viktiga när de betraktas tillsammans. Överväg att använda en användardefinierad typ i dessa fall.

  *Fler*
  - En funktion för att mata ut den lokala minimi för en annan funktion kan behöva ta gränser för ett Sök intervall som indata, så att `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` kan vara en lämplig signatur.
  - En åtgärd för att uppskatta ett derivat av en Machine Learning-klassificerare med parameter Shift-tekniken kan behöva ta både de skiftna och skifta parameter vektorer som indata. En indatatyp som liknar `(unshifted : Double[], shifted : Double[])` kan vara lämplig i det här fallet.

- ✅ **ordnar** objekten i indata-och utdataström konsekvent över olika funktioner och åtgärder.

  *Fler*
  - Om du överväger två eller Functions eller åtgärder som varje tar en rotations vinkel och en mål qubit som indata, kontrollerar du att de är ordnade i varje tupel. Det vill `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` och `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` till `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` och `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.

**Nyckel princip:** design funktioner och åtgärder för att fungera bra med frågor och svar\# språk funktioner, till exempel delvis program.

- ✅ **ordnar** objekt i tupler så att de vanligaste inmatningarna sker först (d.v.s.: så att partiella program fungerar på samma sätt som currying).

  *Fler*
  - En åtgärd `ApplyRotation` som tar ett flytt ALS nummer och en qubit eftersom indata kanske ofta används delvis med flytt ALS indata för användning med åtgärder som förväntar sig indata av typen `Qubit => Unit`. Det innebär att signaturen för `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      fungerar mest konsekvent med delvis program.
  - Den här vägledningen innebär vanligt vis att placera alla klassiska data innan alla qubits i indata-tupler, men Använd bra omdöme och kontrol lera hur ditt API anropas i praktiken.

## <a name="user-defined-types"></a>Användardefinierade typer

**Nyckel princip:** Använd användardefinierade typer för att hjälpa till att göra API: er mer lättfattliga programspecifika och bekvämt att använda.

- ✅ **introducera** nya användardefinierade typer för att ge en bra kort skrift för långa och/eller komplicerade typer.

  *Fler*
  - I de fall där en åtgärds typ med tre qubit mat ris indata utförs ofta som indata eller returneras som utdata, vilket ger en UDT som `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      kan hjälpa dig att ge en användbar kort skrift.

- ✅ **introducera** nya användardefinierade typer för att indikera att en viss bastyp endast ska användas i en särskilt idé.

  *Fler*
  - En åtgärd som ska tolkas specifikt som en åtgärd som kodar klassiska data till ett Quantum-register kan vara lämplig för etiketter med en användardefinierad typ `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.

- ✅ **lägger** till nya användardefinierade typer med namngivna objekt som möjliggör framtida utökning (t. ex. en resultat struktur som kan innehålla ytterligare namngivna objekt i framtiden).

  *Fler*
  - När en åtgärd `TrainModel` visar ett stort antal konfigurations alternativ, exponeras dessa alternativ som en ny `TrainingOptions` UDT och en ny funktion `DefaultTrainingOptions : Unit -> TrainingOptions` gör det möjligt för användare att åsidosätta vissa namngivna objekt i TrainingOptions UDT-värden samtidigt som biblioteks utvecklare kan lägga till nya UDT-objekt efter behov.

- ✅ **deklarerar du namngivna** objekt för nya användardefinierade typer i preferenser som kräver att användarna känner till rätt tuple-inkonstruktion.

  *Fler*
  - När du representerar ett komplext tal i dess polära dekomposition föredrar du `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` att `newtype ComplexPolar = (Double, Double)`.

**Nyckel princip:** Använd användardefinierade typer på olika sätt för att minska kognitiv belastning och som inte kräver att användaren lär sig ytterligare begrepp och nomenklatur.

- ⛔️ introducerar **inte** användardefinierade typer som kräver att användaren ofta använder sig av unwrap-operatorn (`!`) eller som ofta kräver flera nivåer av avbrytning. Några möjliga lösningar för minskning är:

  - När du exponerar en användardefinierad typ med ett enda objekt bör du överväga att definiera ett namn för objektet. Tänk till exempel `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` i `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.

  - Att se till att andra funktioner och åtgärder kan acceptera "figursatta" UDT-instanser direkt.

- ⛔️ introducerar **inte** nya användardefinierade typer som duplicerar inbyggda typer utan att tillhandahålla ytterligare Expressiveness.

  *Fler*
  - En UDT-`newtype QubitRegister = Qubit[]` ger inga ytterligare Expressiveness över `Qubit[]`och är därför svårare att använda utan går-förmån.
  - En UDT-`newtype LittleEndian = Qubit[]` dokumenterar hur det underliggande registret ska användas och tolkas och ger därmed ytterligare Expressiveness över sin bastyp.

- ⛔️ introducerar **inte** accessor-funktioner om det inte är absolut nödvändigt.   föredra namngivna objekt i det här fallet.

  *Fler*
  - När du introducerar en UDT-`newtype Complex = (Double, Double)`bör du hellre ändra definitionen till `newtype Complex = (Real : Double, Imag : Double)` till att introducera funktioner `GetReal : Complex -> Double` och `GetImag : Complex -> Double`.

## <a name="namespaces-and-organization"></a>Namn områden och organisation

**Nyckel princip:** Välj namn områdes namn som är förutsägbara och som tydligt kommunicerar syftet med funktioner, åtgärder och användardefinierade typer i varje namnrymd.

- ✅ **gör** namn namn rymder som `Publisher.Product.DomainArea`.

  *Fler*
  - Funktioner, åtgärder och UDTs som publiceras av Microsoft som en del av funktionen Quantum-simulering i Quantum Development Kit placeras i `Microsoft.Quantum.Simulation`-namnrymden.
  - `Microsoft.Quantum.Math` representerar ett namn område som publicerats av Microsoft som en del av Quantum Development Kit som hör till området matematik.

- ✅ **utför** åtgärder, funktioner och användardefinierade typer som används för vissa funktioner i ett namn område som beskriver funktionen, även när funktionen används i olika problem domäner.

  *Fler*
  - API: er för tillstånds förberedelse som publicerats av Microsoft som en del av Quantum Development Kit placeras i `Microsoft.Quantum.Preparation`.
  - API: er för Quantum simulator som publicerats av Microsoft som en del av Quantum Development Kit skulle placeras i `Microsoft.Quantum.Simulation`.

- ✅ **utför** åtgärder, funktioner och användardefinierade typer som enbart används inom vissa domäner i namn områden som indikerar deras domän. Om det behövs använder du under namn rymder för att indikera fokuserade uppgifter inom varje domänbaserat namn område.

  *Fler*
  - Quantum Machine Learning-biblioteket som publicerades av Microsoft placeras i stort sett i @"microsoft.quantum.machinelearning" namn området, men exempel på data uppsättningar tillhandahålls av namn området @"microsoft.quantum.machinelearning.datasets".
  - Quantum kemi-API: er som publicerats av Microsoft som en del av Quantum Development Kit bör placeras i `Microsoft.Quantum.Chemistry`. Funktioner som är speciella för att implementera Jordanien-Wigner-dekompositionen kan placeras i `Microsoft.Quantum.Chemistry.JordanWigner`, så att det primära gränssnittet för domän arean Quantum kemi inte är bekymrat till implementeringar.

**Nyckel princip:** Använd namn rymder och åtkomst modifierare för att vara avsiktliga om den API-yta som visas för användarna och för att dölja intern information som rör implementering och testning av dina API: er.

- ✅ närhelst det är rimligt **, ska du placera alla** funktioner och åtgärder som behövs för att implementera ett API i samma namnrymd som API: et som implementeras, men markerat med nyckelorden "privat" eller "internt" för att indikera att de inte ingår i den offentliga API-ytan för ett bibliotek. Använd ett namn som börjar med ett under streck (`_`) för att visuellt särskilja privata och interna åtgärder och funktioner från offentliga callables.

  *Fler*
  - Åtgärds namnet `_Features` anger en funktion som är privat för en specifik namnrymd och sammansättning och som ska åtföljas av antingen nyckelordet `internal`.

- ✅ i sällsynta fall att en omfattande uppsättning privata funktioner eller åtgärder krävs för att implementera API: et för ett angivet namn område, **ska du** placera dem i ett nytt namn område som matchar namn området som implementeras och slutar på `.Private`.

- ✅ **Placera** alla enhets tester i namn områden som matchar namn området under test och slutar `.Tests`.

## <a name="naming-conventions-and-vocabulary"></a>Namngivnings konventioner och vokabulär

**Nyckel princip:** Välj namn och terminologi som är tydliga, tillgängliga och läsbara i flera olika mål grupper, inklusive både Quantum Novices och experter.

- ⛔️ **inte** använda diskriminerande eller undantags identifierare, eller terminologi i kommentarer för API-dokumentation.

- ✅ **använder** kommentarer för API-dokumentation för att tillhandahålla relevant kontext, exempel och referenser, särskilt för svårare koncept.

- ⛔️ **inte** använda ID-namn som inte är nödvändigt för Esoteric, eller som kräver betydande Quantum-algoritmer att läsa.

  *Fler*
  - Föredra "amplitud förstärkning iteration" till "Grover iteration".

- ✅ väljer **du** åtgärder och funktions namn som tydligt förmedlar den avsedda påverkan av ett anrops bara och inte dess implementering. Observera att implementeringen kan och bör vara

  *Fler*
  - Föredra "uppskatta överlappande" till "Hadamard test", eftersom den senare kommunicerar hur den tidigare implementeras.

- ✅ **använder** ord på ett konsekvent sätt i alla API: er för api-\#:

  - **Verb**

    - **Assert**: kontrol lera att ett antagande om status för en måldator och dess qubits innehåller, möjligen med hjälp av fysiska resurser. Åtgärder som använder det här verbet bör alltid vara säkert flyttbara utan att det påverkar funktionerna i bibliotek och körbara program. Observera att till skillnad från fakta, som är allmänt beroende av externa tillstånd, till exempel ett qubit register, körnings miljön eller så vidare. Som beroende av extern status är en typ av sido effekt, och försäkrar måste visas som åtgärder i stället för functions.

    - **Uppskattning**: Använd en eller flera eventuellt upprepade mätningar för att beräkna en klassisk kvantitet från mätnings resultaten.

      *Fler*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Förbered**: tillämpa en Quantum-åtgärd eller en sekvens med åtgärder för en eller flera qubits som antas starta i ett visst ursprungligt tillstånd (vanligt vis $ \ket{00\cdots 0), vilket gör att tillstånden för dessa qubits utvecklas till ett önskat slut tillstånd. I allmänhet **kan** man på andra stater än det som anges i andra länder leda till en odefinierad allmän omvandling, men **bör** fortfarande bevara en åtgärd och dess angränsande "annullera ut" och tillämpa en no-op.

      *Fler*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Mått**: tillämpa en Quantum-åtgärd eller en sekvens med åtgärder för en eller flera qubits, och Läs sedan ut klassiska data.

      *Fler*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Tillämpa**: tillämpa en Quantum-åtgärd eller en sekvens med åtgärder på en eller flera qubits, vilket gör att qubits ändras på ett konsekvent sätt. Det här verbet är det mest generella verbet i Q\# nomenklatur och **bör inte** användas när ett mer särskilt verb är direkt relevant.

  - **Substantiv**:

    - **Fakta**: ett booleskt villkor som bara är beroende av sina indata och inte på en måldators tillstånd, dess miljö eller tillståndet för datorns qubits. Till skillnad från en försäkran är ett faktum bara känsligt för de *värden* som anges i detta faktum. Exempel:

      *Fler*
      - @"microsoft.quantum.diagnostics.equalityfacti": representerar ett likhets faktum mellan två heltals indata; antingen är de heltal som anges som indata lika med varandra, eller inte, oberoende av andra program tillstånd.

    - **Alternativ:** En UDT som innehåller flera namngivna objekt som kan fungera som valfria argument till en funktion eller åtgärd. Exempel:

      *Fler*
      - @"microsoft.quantum.machinelearning.trainingoptions" UDT innehåller namngivna objekt för inlärnings pris, minibatch storlek och andra konfigurerbara parametrar för ML-utbildning.

  - **Adjektiv**:

    - ⛔️ **nytt**: denna adjektiv **bör inte** användas, för att undvika förvirring med användning som ett verb i många programmeringsspråk (t. ex.: C++, C#Java, typescript, PowerShell).

  - **Förpositioner:** I vissa fall kan förpositioner användas för att ytterligare disambiguate eller för tydliga roller i Substantiv och verb i funktions-och åtgärds namn. Bryr dig om att göra detta sparsamt och konsekvent.

    - **Som:** Visar att en funktions indata och utdata representerar samma information, men att utdata representerar den informationen **som** ett *X* i stället för den ursprungliga representationen. Detta är särskilt vanligt för typ konverterings funktioner.

      *Fler*
      - `IntAsDouble(2)` anger att både indata (`2`) och utdata (`2.0`) representerar samma information, men använder olika Q\# data typer för att göra det.

    - **Från:** För att säkerställa konsekvens **bör** denna förposition inte användas för att indikera typ konverterings funktioner eller andra **fall där det** är lämpligt.

    - ⛔️ **till:** den här förpositionen **bör inte** användas för att undvika förvirring med användning som ett verb i flera programmeringsspråk.
