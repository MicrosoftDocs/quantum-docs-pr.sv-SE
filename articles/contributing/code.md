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
# <a name="contributing-code"></a><span data-ttu-id="128ce-103">Bidrags kod</span><span class="sxs-lookup"><span data-stu-id="128ce-103">Contributing Code</span></span> #

<span data-ttu-id="128ce-104">Förutom att rapportera problem och förbättra dokumentationen kan kod till Quantum Development Kit vara ett mycket direkt sätt att hjälpa dina kollegor i Quantum Programming-communityn.</span><span class="sxs-lookup"><span data-stu-id="128ce-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="128ce-105">Genom att bidra med kod kan du hjälpa till att åtgärda problem, tillhandahålla nya exempel, göra befintliga bibliotek lättare att använda, eller till och med helt nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="128ce-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="128ce-106">I den här guiden ska vi se en del av vad vi letar efter när vi granskar pull-begäranden för att hjälpa ditt bidrag att göra den mest bra.</span><span class="sxs-lookup"><span data-stu-id="128ce-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="128ce-107">Vad vi letar efter</span><span class="sxs-lookup"><span data-stu-id="128ce-107">What We Look For</span></span> ##

<span data-ttu-id="128ce-108">Ett idealiskt kod bidrag bygger på det befintliga arbetet i en databas för Quantum Development Kit för att åtgärda problem, Visa befintliga funktioner eller lägga till nya funktioner inom en lagrings plats.</span><span class="sxs-lookup"><span data-stu-id="128ce-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="128ce-109">När vi accepterar ett kod bidrag blir det en del av Quantum Development Kit, så att nya funktioner släpps, bevaras och utvecklas på samma sätt som resten av Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="128ce-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="128ce-110">Därför är det användbart när funktioner som läggs till av ett bidrag är väl testade och dokumenteras.</span><span class="sxs-lookup"><span data-stu-id="128ce-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="128ce-111">Enhets tester</span><span class="sxs-lookup"><span data-stu-id="128ce-111">Unit Tests</span></span> ###

<span data-ttu-id="128ce-112">De Q #-funktioner, åtgärder och användardefinierade typer som utgör bibliotek, till exempel Canon, testas automatiskt som en del av utvecklingen på [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) -lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="128ce-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="128ce-113">När en ny pull-begäran öppnas, till exempel så kontrollerar vår [Azure-pipeline](https://azure.microsoft.com/services/devops/pipelines/) att ändringarna i pull-begäran inte bryter några befintliga funktioner som program varan Quantum Programming är beroende av.</span><span class="sxs-lookup"><span data-stu-id="128ce-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>
<span data-ttu-id="128ce-114">Dessa tester skrivs med [Microsoft. Quantum. Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) -paketet, som visar Q #-funktioner och-åtgärder som tester för [Xunit](https://xunit.github.io/) -ramverket.</span><span class="sxs-lookup"><span data-stu-id="128ce-114">These tests are written using the [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package, which exposes Q# functions and operations as tests for the [xUnit](https://xunit.github.io/) framework.</span></span>

<span data-ttu-id="128ce-115">[`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) använder den här xUnit-integreringen för att köra alla funktioner eller åtgärder som slutar på `Test`.</span><span class="sxs-lookup"><span data-stu-id="128ce-115">The [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) uses this xUnit integration to run any functions or operations ending in `Test`.</span></span>
<span data-ttu-id="128ce-116">Följande funktion används till exempel för att se till att <xref:microsoft.quantum.canon.fst> och <xref:microsoft.quantum.canon.snd> fungerar både för att returnera rätt utdata i ett representativt exempel.</span><span class="sxs-lookup"><span data-stu-id="128ce-116">For instance, the following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="128ce-117">Om resultatet av `Fst` eller `Snd` är felaktigt används `fail`-instruktionen för att göra testet misslyckat.</span><span class="sxs-lookup"><span data-stu-id="128ce-117">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

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

<span data-ttu-id="128ce-118">Mer komplicerade villkor kan kontrol leras med hjälp av metoderna i [avsnittet test](xref:microsoft.quantum.libraries.diagnostics) i standard biblioteks guiden.</span><span class="sxs-lookup"><span data-stu-id="128ce-118">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="128ce-119">Följande test kontrollerar till exempel att `H(q); X(q); H(q);` som anropas av <xref:microsoft.quantum.canon.applywith> gör samma sak som `Z(q)`.</span><span class="sxs-lookup"><span data-stu-id="128ce-119">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="128ce-120">När du lägger till nya funktioner, är det en bra idé att även lägga till nya tester för att se till att ditt bidrag gör det.</span><span class="sxs-lookup"><span data-stu-id="128ce-120">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="128ce-121">Detta hjälper resten av communityn att underhålla och utveckla din funktion, och särskilt hjälper andra utvecklare att se att de kan lita på din funktion.</span><span class="sxs-lookup"><span data-stu-id="128ce-121">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="128ce-122">Detta fungerar på ett annat sätt, även om!</span><span class="sxs-lookup"><span data-stu-id="128ce-122">This works the other way around, too!</span></span>
> <span data-ttu-id="128ce-123">Om det finns en befintlig funktion som saknar test, kan vi hjälpa oss att lägga till test täckning till ett bra bidrag till communityn.</span><span class="sxs-lookup"><span data-stu-id="128ce-123">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="128ce-124">Lokalt kan du köra enhets test med Visual Studio Test Explorer eller kommandot `dotnet test`, så att du kan kontrol lera ditt bidrag innan du öppnar en pull-begäran.</span><span class="sxs-lookup"><span data-stu-id="128ce-124">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="128ce-125">När vi avvisar en pull-begäran</span><span class="sxs-lookup"><span data-stu-id="128ce-125">When We'll Reject a Pull Request</span></span> ##

<span data-ttu-id="128ce-126">Ibland avvisar vi pull-begäran för ett bidrag.</span><span class="sxs-lookup"><span data-stu-id="128ce-126">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="128ce-127">Om detta inträffar kan det inte betyda att det är dåligt, eftersom det finns ett antal orsaker till att vi kanske inte kan acceptera ett visst bidrag.</span><span class="sxs-lookup"><span data-stu-id="128ce-127">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="128ce-128">I de flesta fall är ett bidrag till Quantum Programming-communityn en riktigt bra, men det är inte rätt ställe att utveckla databasen i Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="128ce-128">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="128ce-129">I sådana fall rekommenderar vi starkt att du skapar din egen lagrings plats---delar av styrkan i Quantum Development Kit är att det är enkelt att skapa och distribuera egna bibliotek med GitHub och NuGet.org, på samma sätt som vi distribuerar Canon och kemi bibliotek idag.</span><span class="sxs-lookup"><span data-stu-id="128ce-129">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="128ce-130">Vid andra tillfällen kan vi avvisa ett användbart bidrag helt enkelt eftersom vi ännu inte är redo att underhålla och utveckla det.</span><span class="sxs-lookup"><span data-stu-id="128ce-130">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="128ce-131">Det kan vara svårt att göra allt, så vi planerar ut vilka funktioner vi kan arbeta med som en översikt.</span><span class="sxs-lookup"><span data-stu-id="128ce-131">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="128ce-132">Detta kan vara ett annat fall där en funktion släpps som ett bibliotek från tredje part kan göra mycket bra.</span><span class="sxs-lookup"><span data-stu-id="128ce-132">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="128ce-133">Du kan också be om hjälp med att ändra en funktion som passar bättre i vår översikt så att vi kan utföra det bästa arbetet med den.</span><span class="sxs-lookup"><span data-stu-id="128ce-133">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="128ce-134">Vi kommer också att be om ändringar i en pull-begäran om den kräver mer dokumentation eller enhets test för att hjälpa oss att använda den, eller om den är tillräckligt stor från resten av de Q #-bibliotek som det gör det svårare för användarna att hitta din funktion.</span><span class="sxs-lookup"><span data-stu-id="128ce-134">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="128ce-135">I dessa fall kommer vi att försöka erbjuda några råd i kod granskningar om vad som kan läggas till eller ändras för att göra ditt bidrag enklare för oss att ta med.</span><span class="sxs-lookup"><span data-stu-id="128ce-135">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="128ce-136">Slutligen kan vi inte ta emot bidrag som skadar den Quantum Computing-gruppen, enligt beskrivningen i [Microsofts regler för öppen källkod för uppförande](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="128ce-136">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="128ce-137">Vi vill se till att bidragen betjänar hela den Quantum data bearbetnings gruppen, både i den aktuella underbara mångfalden och i framtiden när den växer för att bli ännu mer.</span><span class="sxs-lookup"><span data-stu-id="128ce-137">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="128ce-138">Vi uppskattar din hjälp att realisera detta mål.</span><span class="sxs-lookup"><span data-stu-id="128ce-138">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="128ce-139">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="128ce-139">Next steps</span></span> ##

<span data-ttu-id="128ce-140">Tack för att du hjälper till att göra Quantum Development Kit till en fantastisk resurs för hela Quantum Programming-gruppen!</span><span class="sxs-lookup"><span data-stu-id="128ce-140">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="128ce-141">Om du vill veta mer kan du fortsätta med följande guide på Q #-format.</span><span class="sxs-lookup"><span data-stu-id="128ce-141">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="128ce-142">Läs mer om rikt linjer för Q #-format</span><span class="sxs-lookup"><span data-stu-id="128ce-142">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)
