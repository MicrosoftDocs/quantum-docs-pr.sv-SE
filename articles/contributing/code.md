---
title: Bidrags kod | Microsoft Docs
description: Bidrags kod
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: cca50e6c63d4bb982aa5f0a59fc19d08ecbec508
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185910"
---
# <a name="contributing-code"></a>Bidrags kod #

Förutom att rapportera problem och förbättra dokumentationen kan kod till Quantum Development Kit vara ett mycket direkt sätt att hjälpa dina kollegor i Quantum Programming-communityn.
Genom att bidra med kod kan du hjälpa till att åtgärda problem, tillhandahålla nya exempel, göra befintliga bibliotek lättare att använda, eller till och med helt nya funktioner.

I den här guiden ska vi se en del av vad vi letar efter när vi granskar pull-begäranden för att hjälpa ditt bidrag att göra den mest bra.

## <a name="what-we-look-for"></a>Vad vi letar efter ##

Ett idealiskt kod bidrag bygger på det befintliga arbetet i en databas för Quantum Development Kit för att åtgärda problem, Visa befintliga funktioner eller lägga till nya funktioner inom en lagrings plats.
När vi accepterar ett kod bidrag blir det en del av Quantum Development Kit, så att nya funktioner släpps, bevaras och utvecklas på samma sätt som resten av Quantum Development Kit.
Därför är det användbart när funktioner som läggs till av ett bidrag är väl testade och dokumenteras.

### <a name="unit-tests"></a>Enhets tester ###

De Q #-funktioner, åtgärder och användardefinierade typer som utgör bibliotek, till exempel Canon, testas automatiskt som en del av utvecklingen på [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) -lagringsplatsen.
När en ny pull-begäran öppnas, till exempel så kontrollerar vår [Azure-pipeline](https://azure.microsoft.com/services/devops/pipelines/) att ändringarna i pull-begäran inte bryter några befintliga funktioner som program varan Quantum Programming är beroende av.
Dessa tester skrivs med [Microsoft. Quantum. Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) -paketet, som visar Q #-funktioner och-åtgärder som tester för [Xunit](https://xunit.github.io/) -ramverket.

[`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) använder den här xUnit-integreringen för att köra alla funktioner eller åtgärder som slutar på `Test`.
Följande funktion används till exempel för att se till att <xref:microsoft.quantum.canon.fst> och <xref:microsoft.quantum.canon.snd> fungerar både för att returnera rätt utdata i ett representativt exempel.
Om resultatet av `Fst` eller `Snd` är felaktigt används `fail`-instruktionen för att göra testet misslyckat.

```qsharp
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

Mer komplicerade villkor kan kontrol leras med hjälp av metoderna i [avsnittet test](xref:microsoft.quantum.libraries.diagnostics) i standard biblioteks guiden.
Följande test kontrollerar till exempel att `H(q); X(q); H(q);` som anropas av <xref:microsoft.quantum.canon.applywith> gör samma sak som `Z(q)`.

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

När du lägger till nya funktioner, är det en bra idé att även lägga till nya tester för att se till att ditt bidrag gör det.
Detta hjälper resten av communityn att underhålla och utveckla din funktion, och särskilt hjälper andra utvecklare att se att de kan lita på din funktion.

> [!NOTE]
> Detta fungerar på ett annat sätt, även om!
> Om det finns en befintlig funktion som saknar test, kan vi hjälpa oss att lägga till test täckning till ett bra bidrag till communityn.

Lokalt kan du köra enhets test med Visual Studio Test Explorer eller kommandot `dotnet test`, så att du kan kontrol lera ditt bidrag innan du öppnar en pull-begäran.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>När vi avvisar en pull-begäran ##

Ibland avvisar vi pull-begäran för ett bidrag.
Om detta inträffar kan det inte betyda att det är dåligt, eftersom det finns ett antal orsaker till att vi kanske inte kan acceptera ett visst bidrag.
I de flesta fall är ett bidrag till Quantum Programming-communityn en riktigt bra, men det är inte rätt ställe att utveckla databasen i Quantum Development Kit.
I sådana fall rekommenderar vi starkt att du skapar din egen lagrings plats---delar av styrkan i Quantum Development Kit är att det är enkelt att skapa och distribuera egna bibliotek med GitHub och NuGet.org, på samma sätt som vi distribuerar Canon och kemi bibliotek idag.

Vid andra tillfällen kan vi avvisa ett användbart bidrag helt enkelt eftersom vi ännu inte är redo att underhålla och utveckla det.
Det kan vara svårt att göra allt, så vi planerar ut vilka funktioner vi kan arbeta med som en översikt.
Detta kan vara ett annat fall där en funktion släpps som ett bibliotek från tredje part kan göra mycket bra.
Du kan också be om hjälp med att ändra en funktion som passar bättre i vår översikt så att vi kan utföra det bästa arbetet med den.

Vi kommer också att be om ändringar i en pull-begäran om den kräver mer dokumentation eller enhets test för att hjälpa oss att använda den, eller om den är tillräckligt stor från resten av de Q #-bibliotek som det gör det svårare för användarna att hitta din funktion.
I dessa fall kommer vi att försöka erbjuda några råd i kod granskningar om vad som kan läggas till eller ändras för att göra ditt bidrag enklare för oss att ta med.

Slutligen kan vi inte ta emot bidrag som skadar den Quantum Computing-gruppen, enligt beskrivningen i [Microsofts regler för öppen källkod för uppförande](https://opensource.microsoft.com/codeofconduct/).
Vi vill se till att bidragen betjänar hela den Quantum data bearbetnings gruppen, både i den aktuella underbara mångfalden och i framtiden när den växer för att bli ännu mer.
Vi uppskattar din hjälp att realisera detta mål.

## <a name="next-steps"></a>Nästa steg ##

Tack för att du hjälper till att göra Quantum Development Kit till en fantastisk resurs för hela Quantum Programming-gruppen!
Om du vill veta mer kan du fortsätta med följande guide på Q #-format.

> [!div class="nextstepaction"]
> [Läs mer om rikt linjer för Q #-format](xref:microsoft.quantum.contributing.style)
