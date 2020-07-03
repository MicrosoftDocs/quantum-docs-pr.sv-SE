---
title: 'Microsoft Q # stil guide'
description: 'Lär dig mer om namngivning, indatamängd, dokumentation och formatering för Q #-program och-bibliotek.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3ddb5d67b972f69df1774b476a10e74dd16d97b7
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884197"
---
# <a name="q-style-guide"></a><span data-ttu-id="24283-103">Stil guide för Q #</span><span class="sxs-lookup"><span data-stu-id="24283-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="24283-104">Allmänna konventioner</span><span class="sxs-lookup"><span data-stu-id="24283-104">General Conventions</span></span> ##

<span data-ttu-id="24283-105">De konventioner som föreslås i den här guiden är avsedda att hjälpa till att göra program och bibliotek skrivna i Q # lättare att läsa och förstå.</span><span class="sxs-lookup"><span data-stu-id="24283-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="24283-106">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-106">Guidance</span></span>

<span data-ttu-id="24283-107">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-107">We suggest:</span></span>

- <span data-ttu-id="24283-108">Bortse aldrig från en konvention om du inte gör det avsiktligt för att tillhandahålla mer läsbar och begriplig kod för dina användare.</span><span class="sxs-lookup"><span data-stu-id="24283-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="24283-109">Namngivnings konventioner</span><span class="sxs-lookup"><span data-stu-id="24283-109">Naming Conventions</span></span> ##

<span data-ttu-id="24283-110">Vid erbjudandet från Quantum Development Kit strävar vi efter funktions-och åtgärds namn som hjälper fantastiska utvecklare att skriva program som är lätta att läsa och som minimerar överraskningen.</span><span class="sxs-lookup"><span data-stu-id="24283-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="24283-111">En viktig del av detta är att när vi väljer namn för funktioner, åtgärder och typer, upprättar vi den *vokabulär* som programmerare använder för att uttrycka Quantum-koncept. med våra val kan vi antingen hjälpa dig eller hindra dem att kommunicera tydligt.</span><span class="sxs-lookup"><span data-stu-id="24283-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="24283-112">På så sätt får vi ett ansvar för oss att se till att namnen vi presenterar ger klarhet i stället för skymt.</span><span class="sxs-lookup"><span data-stu-id="24283-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="24283-113">I det här avsnittet beskriver vi hur vi uppfyller denna skyldighet i termer av uttryckliga rikt linjer som hjälper oss att göra det bästa med utvecklings gruppen för Q-nummer.</span><span class="sxs-lookup"><span data-stu-id="24283-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="24283-114">Åtgärder och funktioner</span><span class="sxs-lookup"><span data-stu-id="24283-114">Operations and Functions</span></span> ###

<span data-ttu-id="24283-115">Ett av de första saker som ett namn bör fastställa är om en specifik symbol representerar en funktion eller en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="24283-116">Skillnaden mellan Functions och Operations är avgörande för att förstå hur ett kod block beter sig.</span><span class="sxs-lookup"><span data-stu-id="24283-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="24283-117">För att kunna kommunicera mellan funktioner och åtgärder för användare, förlitar vi oss på att det finns Quantum åtgärder i Q #-modeller genom användning av sido effekter.</span><span class="sxs-lookup"><span data-stu-id="24283-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="24283-118">Det vill säga en åtgärd *gör* något.</span><span class="sxs-lookup"><span data-stu-id="24283-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="24283-119">Funktionen kontrast beskriver däremot de matematiska relationerna mellan data.</span><span class="sxs-lookup"><span data-stu-id="24283-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="24283-120">Uttrycket `Sin(PI() / 2.0)` *är* `1.0` och innebär ingenting om status för ett program eller dess qubits.</span><span class="sxs-lookup"><span data-stu-id="24283-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="24283-121">Med sammanfattningen fungerar åtgärder saker och ting.</span><span class="sxs-lookup"><span data-stu-id="24283-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="24283-122">Den här skillnaden antyder att vi namnger åtgärder som verb och fungerar som substantiv.</span><span class="sxs-lookup"><span data-stu-id="24283-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="24283-123">När en användardefinierad typ deklareras, definieras en ny funktion som konstruerar instanser av den typen implicit på samma gång.</span><span class="sxs-lookup"><span data-stu-id="24283-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="24283-124">Från och med detta perspektiv ska användardefinierade typer namnges som substantiv, så att både själva typen och konstruktorn-funktionen har konsekventa namn.</span><span class="sxs-lookup"><span data-stu-id="24283-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="24283-125">Om det är rimligt bör du se till att åtgärds namnen börjar med verb som tydligt anger vilken åtgärd som vidtas.</span><span class="sxs-lookup"><span data-stu-id="24283-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="24283-126">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="24283-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="24283-127">Ett förtjänar särskilt omnämnande är när en åtgärd tar en annan åtgärd som inmatad och anropar den.</span><span class="sxs-lookup"><span data-stu-id="24283-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="24283-128">I sådana fall är åtgärden som vidtas av inläsnings åtgärden inte klar när den yttre åtgärden definieras, så att det högra verbet inte är omedelbart klart.</span><span class="sxs-lookup"><span data-stu-id="24283-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="24283-129">Vi rekommenderar verbet `Apply` , som i `ApplyIf` , `ApplyToEach` och `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="24283-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="24283-130">Andra verb kan vara användbara även i det här fallet, som i `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="24283-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="24283-131">Verb</span><span class="sxs-lookup"><span data-stu-id="24283-131">Verb</span></span> | <span data-ttu-id="24283-132">Förväntad påverkan</span><span class="sxs-lookup"><span data-stu-id="24283-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="24283-133">Använd</span><span class="sxs-lookup"><span data-stu-id="24283-133">Apply</span></span> | <span data-ttu-id="24283-134">En åtgärd som angetts som indata kallas</span><span class="sxs-lookup"><span data-stu-id="24283-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="24283-135">Assert</span><span class="sxs-lookup"><span data-stu-id="24283-135">Assert</span></span> | <span data-ttu-id="24283-136">En hypotes om resultatet av en möjlig Quantum-mätning kontrol leras av en simulator</span><span class="sxs-lookup"><span data-stu-id="24283-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="24283-137">Beräkning</span><span class="sxs-lookup"><span data-stu-id="24283-137">Estimate</span></span> | <span data-ttu-id="24283-138">Ett klassiskt värde returneras som representerar en uppskattning som skapats från en eller flera mätningar</span><span class="sxs-lookup"><span data-stu-id="24283-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="24283-139">Mått</span><span class="sxs-lookup"><span data-stu-id="24283-139">Measure</span></span> | <span data-ttu-id="24283-140">En Quantum-mätning utförs och resultatet returneras till användaren</span><span class="sxs-lookup"><span data-stu-id="24283-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="24283-141">Förbereda</span><span class="sxs-lookup"><span data-stu-id="24283-141">Prepare</span></span> | <span data-ttu-id="24283-142">Ett visst register av qubits initieras i ett visst tillstånd</span><span class="sxs-lookup"><span data-stu-id="24283-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="24283-143">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-143">Sample</span></span> | <span data-ttu-id="24283-144">Ett klassiskt värde returneras slumpmässigt från en distribution</span><span class="sxs-lookup"><span data-stu-id="24283-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="24283-145">För functions, rekommenderar vi att du undviker användningen av verb som prioriterar vanliga Substantiv (se rikt linjer för rätt Substantiv nedan) eller adjektiv:</span><span class="sxs-lookup"><span data-stu-id="24283-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="24283-146">I nästan alla fall föreslår vi i stort sett att du använder tidigare Participles, om det är lämpligt att ange att ett funktions namn är starkt anslutet till en åtgärd eller en sido effekt någon annan stans i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="24283-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="24283-147">Till exempel `ControlledOnInt` används del participle-formen av verbet "Control" för att ange att funktionen fungerar som en adjektiv för att ändra dess argument.</span><span class="sxs-lookup"><span data-stu-id="24283-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="24283-148">Det här namnet har ytterligare fördelar med att matcha semantiken för de inbyggda `Controlled` Functor, enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="24283-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="24283-149">På samma sätt kan du använda _agent Substantiv_ för att skapa Function-och UDT-namn från åtgärds namn, som i fallet med namnet `Encoder` på en UDT som är starkt associerad med `Encode` .</span><span class="sxs-lookup"><span data-stu-id="24283-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-150">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-151">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-151">We suggest:</span></span>

- <span data-ttu-id="24283-152">Använd verb för åtgärds namn.</span><span class="sxs-lookup"><span data-stu-id="24283-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="24283-153">Använd Substantiv eller adjektiv för funktions namn.</span><span class="sxs-lookup"><span data-stu-id="24283-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="24283-154">Använd Substantiv för användardefinierade typer och attribut.</span><span class="sxs-lookup"><span data-stu-id="24283-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="24283-155">För alla namn som kan anropas använder `CamelCase` du i stark preferens till `pascalCase` , `snake_case` eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24283-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="24283-156">Se särskilt till att anrops bara namn börjar med versaler.</span><span class="sxs-lookup"><span data-stu-id="24283-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="24283-157">För alla lokala variabler använder `pascalCase` du i stark preferens till `CamelCase` , `snake_case` eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24283-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="24283-158">Se särskilt till att lokala variabler börjar med små bokstäver.</span><span class="sxs-lookup"><span data-stu-id="24283-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="24283-159">Undvik att använda under streck `_` i funktions-och åtgärds namn. om det behövs ytterligare nivåer av hierarkin använder du namn rymder och namn rymds alias.</span><span class="sxs-lookup"><span data-stu-id="24283-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-160">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-161">Name</span><span class="sxs-lookup"><span data-stu-id="24283-161">Name</span></span> | <span data-ttu-id="24283-162">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24283-163">☑</span><span class="sxs-lookup"><span data-stu-id="24283-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="24283-164">Rensa användningen av ett verb ("reflektera") för att ange hur åtgärden ska fungera.</span><span class="sxs-lookup"><span data-stu-id="24283-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="24283-165">☒</span><span class="sxs-lookup"><span data-stu-id="24283-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="24283-166">Användning av en Substantiv-fras föreslår funktion i stället för åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="24283-167">☒</span><span class="sxs-lookup"><span data-stu-id="24283-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="24283-168">Användning av `snake_case` bryter mot Q #-notation.</span><span class="sxs-lookup"><span data-stu-id="24283-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="24283-169">☒</span><span class="sxs-lookup"><span data-stu-id="24283-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="24283-170">Användning av under streck till åtgärds namn bestrider Q #-notation.</span><span class="sxs-lookup"><span data-stu-id="24283-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="24283-171">☑</span><span class="sxs-lookup"><span data-stu-id="24283-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="24283-172">Användning av Substantiv fras föreslår att funktionen returnerar en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="24283-173">☑</span><span class="sxs-lookup"><span data-stu-id="24283-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="24283-174">Clear use of Substantiv ("faktumet") för att indikera att detta är en funktion, medan adjektiv.</span><span class="sxs-lookup"><span data-stu-id="24283-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="24283-175">☒</span><span class="sxs-lookup"><span data-stu-id="24283-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="24283-176">Användning av verb ("Get") föreslår att detta är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="24283-177">☑</span><span class="sxs-lookup"><span data-stu-id="24283-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="24283-178">Användningen av Substantiv frasen avser tydligt resultatet av att anropa UDT-konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="24283-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="24283-179">☒</span><span class="sxs-lookup"><span data-stu-id="24283-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="24283-180">Användning av verbfras föreslår att UDT-konstruktorn är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="24283-181">☑</span><span class="sxs-lookup"><span data-stu-id="24283-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="24283-182">Användningen av Substantiv frasen kommunicerar användningen av attributet.</span><span class="sxs-lookup"><span data-stu-id="24283-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="entry-points"></a><span data-ttu-id="24283-183">Startpunkter</span><span class="sxs-lookup"><span data-stu-id="24283-183">Entry Points</span></span>

<span data-ttu-id="24283-184">När du definierar en start punkt i ett Q #-program, identifierar Q #-kompilatorn [ `@EntryPoint()` attributet](xref:microsoft.quantum.core.entrypoint) och kräver att start punkterna har ett visst namn (t. ex.: `main` , `Main` eller `__main__` ).</span><span class="sxs-lookup"><span data-stu-id="24283-184">When defining an entry point into a Q# program, the Q# compiler recognizes the [`@EntryPoint()` attribute](xref:microsoft.quantum.core.entrypoint) rather requiring that entry points have a particular name (e.g.: `main`, `Main`, or `__main__`).</span></span>
<span data-ttu-id="24283-185">Det vill säga från en Q #-utvecklare är start punkter vanliga åtgärder som är kommenterade `@EntryPoint()` .</span><span class="sxs-lookup"><span data-stu-id="24283-185">That is, from the perspective of a Q# developer, entry points are ordinary operations annotated with `@EntryPoint()`.</span></span>
<span data-ttu-id="24283-186">Dessutom kan Q #-startpunkter vara ingångs punkter för ett helt program (d.v.s.: i Q # fristående körbara filer) eller kan vara ett gränssnitt mellan ett Q #-program och värd programmet för ett program (d.v.s.: när du använder Q # med python eller .NET), så att namnet "Main" kan vara missvisande när det tillämpas på en start punkt för Q #.</span><span class="sxs-lookup"><span data-stu-id="24283-186">Moreover, Q# entry points may be entry points for an entire application (i.e.: in Q# standalone executables), or may be an interface between a Q# program and the host program for an application (i.e.: when using Q# with Python or .NET), such that the name "main" could be misleading when applied to a Q# entry point.</span></span>

<span data-ttu-id="24283-187">Vi rekommenderar att du använder namngivnings punkter för att återspegla användningen av `@EntryPoint()` attributet genom att följa de allmänna råd som anges ovan.</span><span class="sxs-lookup"><span data-stu-id="24283-187">We suggest using naming entry points to reflect the use of the `@EntryPoint()` attribute by using the general advice for naming operations listed above.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="24283-188">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-188">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-189">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-189">We suggest:</span></span>

- <span data-ttu-id="24283-190">Ge inte namn på Start punkts åtgärder som "Main".</span><span class="sxs-lookup"><span data-stu-id="24283-190">Do not name entry point operations as "main."</span></span>
- <span data-ttu-id="24283-191">Namn start punkt åtgärder som vanliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="24283-191">Name entry point operations as ordinary operations.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-192">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-192">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-193">Name</span><span class="sxs-lookup"><span data-stu-id="24283-193">Name</span></span> | <span data-ttu-id="24283-194">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-194">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24283-195">☑</span><span class="sxs-lookup"><span data-stu-id="24283-195">☑</span></span> | `@EntryPoint() operation RunSimulation` | <span data-ttu-id="24283-196">Kommunicerar tydligt syftet med start punkten via åtgärds namn.</span><span class="sxs-lookup"><span data-stu-id="24283-196">Clearly communicates purpose of entry point through operation name.</span></span> |
| <span data-ttu-id="24283-197">☒</span><span class="sxs-lookup"><span data-stu-id="24283-197">☒</span></span> | <s>`@EntryPoint() operation Main`</s> | <span data-ttu-id="24283-198">Användning av `Main` är inte tydligt syftet med start punkten och är redundant med `@EntryPoint()` attribut.</span><span class="sxs-lookup"><span data-stu-id="24283-198">Use of `Main` doesn't clearly communicate purpose of entry point, and is redundant with `@EntryPoint()` attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="24283-199">Kort och förkortningar</span><span class="sxs-lookup"><span data-stu-id="24283-199">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="24283-200">Ovanstående råd trots detta är att det finns många former av kort som ser gemensam och genomgripande användning i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="24283-200">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="24283-201">Vi rekommenderar att du använder ett befintligt och vanligt kort ställe där det finns, särskilt för åtgärder som är unika för driften av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="24283-201">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="24283-202">Exempelvis väljer vi namnet `X` i stället för `ApplyX` , och `Rz` istället för `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="24283-202">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="24283-203">Vid användning av sådant kort ska åtgärds namnen vara alla versaler (t. ex.: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="24283-203">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="24283-204">En del Försiktighet krävs vid tillämpning av denna konvention när det gäller vanliga akronymer och initialisms, till exempel "QFT" för "Quantum Fourier Transform".</span><span class="sxs-lookup"><span data-stu-id="24283-204">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="24283-205">Vi föreslår följande allmänna .NET-konventioner för användning av akronymer och initialisms i fullständiga namn, vilket föreskriver att:</span><span class="sxs-lookup"><span data-stu-id="24283-205">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="24283-206">akronymer och initialisms med två bokstäver anges i versaler (t. ex.: `BE` för "big-endian").</span><span class="sxs-lookup"><span data-stu-id="24283-206">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="24283-207">alla längre akronymer och initialisms är namngivna i `CamelCase` (t. ex.: `Qft` "Quantum Fourier Transform")</span><span class="sxs-lookup"><span data-stu-id="24283-207">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="24283-208">Därför kan en åtgärd som implementerar QFT anropas `QFT` som stenografisk eller skrivas ut som `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="24283-208">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="24283-209">För de flesta vanliga åtgärder och funktioner kan det vara önskvärt att ange ett namn på kort texten som ett _alias_ i ett längre format:</span><span class="sxs-lookup"><span data-stu-id="24283-209">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="24283-210">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-210">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-211">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-211">We suggest:</span></span>

- <span data-ttu-id="24283-212">Betrakta ofta godkända och vanliga namn på kort skrift vid behov.</span><span class="sxs-lookup"><span data-stu-id="24283-212">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="24283-213">Använd versaler för kort skrift.</span><span class="sxs-lookup"><span data-stu-id="24283-213">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="24283-214">Använd versaler för korta (två bokstäver) akronymer och initialisms.</span><span class="sxs-lookup"><span data-stu-id="24283-214">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="24283-215">Används `CamelCase` för längre (tre eller fler bokstäver) akronymer och initialisms.</span><span class="sxs-lookup"><span data-stu-id="24283-215">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-216">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-216">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-217">Name</span><span class="sxs-lookup"><span data-stu-id="24283-217">Name</span></span> | <span data-ttu-id="24283-218">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-218">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24283-219">☑</span><span class="sxs-lookup"><span data-stu-id="24283-219">☑</span></span> | `X` | <span data-ttu-id="24283-220">Välförstått kort för "tillämpa en $X $-transformering"</span><span class="sxs-lookup"><span data-stu-id="24283-220">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="24283-221">☑</span><span class="sxs-lookup"><span data-stu-id="24283-221">☑</span></span> | `CNOT` | <span data-ttu-id="24283-222">Välförståttt snabb kort för "styrd-NOT"</span><span class="sxs-lookup"><span data-stu-id="24283-222">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="24283-223">☒</span><span class="sxs-lookup"><span data-stu-id="24283-223">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="24283-224">Snabb kort bör inte vara i `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="24283-224">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="24283-225">☑</span><span class="sxs-lookup"><span data-stu-id="24283-225">☑</span></span> | `ApplyQft` | <span data-ttu-id="24283-226">Vanlig inledande "QFT" visas som en del av ett långt format namn.</span><span class="sxs-lookup"><span data-stu-id="24283-226">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="24283-227">☑</span><span class="sxs-lookup"><span data-stu-id="24283-227">☑</span></span> | `QFT` | <span data-ttu-id="24283-228">Vanlig inledande "QFT" visas som en del av ett kort namn.</span><span class="sxs-lookup"><span data-stu-id="24283-228">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="24283-229">Rätt Substantiv i namn</span><span class="sxs-lookup"><span data-stu-id="24283-229">Proper Nouns in Names</span></span> ###

<span data-ttu-id="24283-230">I fysik är det vanligt att namnge saker efter att den första personen har publicerat dem, men de flesta icke-physicists är inte bekanta med allas namn och all historik.</span><span class="sxs-lookup"><span data-stu-id="24283-230">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="24283-231">Att förlita sig på namngivnings konventioner från fysiken kan därför ge en betydande barriär för att registrera sig, eftersom användare från andra bakgrunder måste lära sig ett stort antal ogenomskinliga namn för att kunna använda vanliga åtgärder och begrepp.</span><span class="sxs-lookup"><span data-stu-id="24283-231">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="24283-232">Därför rekommenderar vi att när rimliga, vanliga substantiv som beskriver ett koncept antas i starka preferenser till rätt substantiv som beskriver ett Koncepts publicerings historik.</span><span class="sxs-lookup"><span data-stu-id="24283-232">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="24283-233">Som ett särskilt exempel kallas den oavsiktligt kontrollerade VÄXLINGen och den dubblerade kontrollerade inte åtgärderna "Fredkin" och "Toffoli"-åtgärder i den akademiska dokumentationen, men de identifieras i Q # främst som `CSWAP` och `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="24283-233">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="24283-234">I båda fallen ger kommentarer till API-dokumentation synonyma namn baserat på korrekta substantiv, tillsammans med alla lämpliga citat tecken.</span><span class="sxs-lookup"><span data-stu-id="24283-234">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="24283-235">Den här inställningen är särskilt viktig, men det är särskilt viktigt att viss användning av rätt Substantiv alltid är nödvändig: Q # följer tradition som har angetts av många klassiska språk, till exempel, och refererar till `Bool` typer i referens till boolesk logik, som i sin tur har värdet George bool.</span><span class="sxs-lookup"><span data-stu-id="24283-235">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="24283-236">Några Quantum-koncept har liknande namn på liknande sätt, inklusive den `Pauli` typ som är inbyggd på språket Q #.</span><span class="sxs-lookup"><span data-stu-id="24283-236">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="24283-237">Genom att minimera användningen av rätt substantiv, om sådan användning inte är nödvändig, minskar vi effekten där rätt Substantiv inte kan undvikas rimligen.</span><span class="sxs-lookup"><span data-stu-id="24283-237">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-238">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-238">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="24283-239">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-239">We suggest:</span></span>

- <span data-ttu-id="24283-240">Undvik att använda rätt Substantiv i namn.</span><span class="sxs-lookup"><span data-stu-id="24283-240">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-241">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-241">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="24283-242">Typ konverteringar</span><span class="sxs-lookup"><span data-stu-id="24283-242">Type Conversions</span></span> ###

<span data-ttu-id="24283-243">Eftersom Q # är ett starkt och statiskt typ språk kan ett värde av en typ endast användas som ett värde av en annan typ med hjälp av ett explicit anrop till en typ konverterings funktion.</span><span class="sxs-lookup"><span data-stu-id="24283-243">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="24283-244">Detta är i motsats till språk som tillåter att värden ändrar typer implicit (t. ex.: typ befordran) eller genom databyte.</span><span class="sxs-lookup"><span data-stu-id="24283-244">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="24283-245">Resultatet är att typ konverterings funktioner spelar en viktig roll i Q # biblioteks utveckling och utgör ett av de vanligaste besluten om namngivning.</span><span class="sxs-lookup"><span data-stu-id="24283-245">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="24283-246">Vi noterar dock att eftersom typ konverteringen alltid är _deterministisk_, kan de skrivas som funktioner och därmed omfattas av ovanstående råd.</span><span class="sxs-lookup"><span data-stu-id="24283-246">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="24283-247">I synnerhet rekommenderar vi att typ konverterings funktioner aldrig ska namnges som verb (t. ex.: `ConvertToX` ) eller adverb-förpositions fraser ( `ToX` ), men ska vara namngivna som adjektiv befattnings fraser som anger käll-och mål typerna ( `XAsY` ).</span><span class="sxs-lookup"><span data-stu-id="24283-247">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="24283-248">När du anger mat ris typer i typ konverterings funktions namn rekommenderar vi kort skrift `Arr` .</span><span class="sxs-lookup"><span data-stu-id="24283-248">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="24283-249">Spärr av exceptionella omständigheter, vi rekommenderar att alla typer av konverterings funktioner får namnet med hjälp av `As` så att de snabbt kan identifieras.</span><span class="sxs-lookup"><span data-stu-id="24283-249">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-250">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-250">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-251">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-251">We suggest:</span></span>

- <span data-ttu-id="24283-252">Om en funktion konverterar ett värde av typen `X` till ett värde av typen `Y` använder du antingen namnet `AsY` eller `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="24283-252">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-253">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-253">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-254">Name</span><span class="sxs-lookup"><span data-stu-id="24283-254">Name</span></span> | <span data-ttu-id="24283-255">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-255">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24283-256">☒</span><span class="sxs-lookup"><span data-stu-id="24283-256">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="24283-257">Förpositionen "till" resulterar i en verbfras som indikerar en åtgärd och inte en funktion.</span><span class="sxs-lookup"><span data-stu-id="24283-257">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="24283-258">☒</span><span class="sxs-lookup"><span data-stu-id="24283-258">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="24283-259">Indatatypen är inte klar från funktions namnet.</span><span class="sxs-lookup"><span data-stu-id="24283-259">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="24283-260">☒</span><span class="sxs-lookup"><span data-stu-id="24283-260">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="24283-261">Indata-och utmatnings typer visas i fel ordning.</span><span class="sxs-lookup"><span data-stu-id="24283-261">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="24283-262">☑</span><span class="sxs-lookup"><span data-stu-id="24283-262">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="24283-263">Både typerna av indata och utdata är tydliga.</span><span class="sxs-lookup"><span data-stu-id="24283-263">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="24283-264">Privata eller interna namn</span><span class="sxs-lookup"><span data-stu-id="24283-264">Private or Internal Names</span></span> ###

<span data-ttu-id="24283-265">I många fall är ett namn enbart avsett för användning internt i ett bibliotek eller projekt, och är inte en garanterad del av API: et som erbjuds av ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="24283-265">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="24283-266">Det är praktiskt att tydligt ange att det här är fallet när du namnger funktioner och åtgärder så att oavsiktliga beroenden i intern kod görs uppenbara.</span><span class="sxs-lookup"><span data-stu-id="24283-266">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="24283-267">Om en åtgärd eller funktion inte är avsedd för direkt användning, utan bör istället användas av en matchande anrops funktion som fungerar genom partiell tillämpning, bör du överväga att använda ett namn som börjar med `internal` nyckelordet för det anrops bara som används delvis.</span><span class="sxs-lookup"><span data-stu-id="24283-267">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-268">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-268">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-269">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-269">We suggest:</span></span>

- <span data-ttu-id="24283-270">Om en funktion, åtgärd eller användardefinierad typ inte är en del av det offentliga API: t för ett Q #-bibliotek eller program, kontrollerar du att den har marker ATS som intern genom att placera `internal` nyckelordet före `function` , `operation` eller- `newtype` deklarationen.</span><span class="sxs-lookup"><span data-stu-id="24283-270">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-271">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-271">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-272">Name</span><span class="sxs-lookup"><span data-stu-id="24283-272">Name</span></span> | <span data-ttu-id="24283-273">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-273">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24283-274">☒</span><span class="sxs-lookup"><span data-stu-id="24283-274">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="24283-275">Använd inte ett under streck `_` för att ange att den här åtgärden endast är för intern användning.</span><span class="sxs-lookup"><span data-stu-id="24283-275">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="24283-276">☑</span><span class="sxs-lookup"><span data-stu-id="24283-276">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="24283-277">`internal`Nyckelordet i början visar tydligt att den här åtgärden endast är för intern användning.</span><span class="sxs-lookup"><span data-stu-id="24283-277">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***
### <a name="variants"></a><span data-ttu-id="24283-278">Varianter</span><span class="sxs-lookup"><span data-stu-id="24283-278">Variants</span></span> ###

<span data-ttu-id="24283-279">Även om den här begränsningen inte finns kvar i framtida versioner av Q #, är det i själva fallet att det ofta finns grupper med relaterade åtgärder eller funktioner som särskiljs genom att functors stöd för indata eller av konkreta typer av argument.</span><span class="sxs-lookup"><span data-stu-id="24283-279">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="24283-280">Dessa grupper kan särskiljas med hjälp av samma rot namn, följt av en eller två bokstäver som anger dess variant.</span><span class="sxs-lookup"><span data-stu-id="24283-280">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="24283-281">Huvudnamnssuffix</span><span class="sxs-lookup"><span data-stu-id="24283-281">Suffix</span></span> | <span data-ttu-id="24283-282">Innebörd</span><span class="sxs-lookup"><span data-stu-id="24283-282">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="24283-283">Indatatyp förväntades stödja`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="24283-283">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="24283-284">Indatatyp förväntades stödja`Controlled`</span><span class="sxs-lookup"><span data-stu-id="24283-284">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="24283-285">Indatatyp förväntades stödja `Controlled` och`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="24283-285">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="24283-286">Indata eller indata är av typen`Int`</span><span class="sxs-lookup"><span data-stu-id="24283-286">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="24283-287">Indata eller indata är av typen`Double`</span><span class="sxs-lookup"><span data-stu-id="24283-287">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="24283-288">Indata eller indata är av typen`BigInt`</span><span class="sxs-lookup"><span data-stu-id="24283-288">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="24283-289">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-289">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-290">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-290">We suggest:</span></span>

- <span data-ttu-id="24283-291">Om en funktion eller åtgärd inte är relaterad till liknande funktioner eller åtgärder som stöds av typerna och Functor stöd för deras indata, ska du inte använda ett suffix.</span><span class="sxs-lookup"><span data-stu-id="24283-291">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="24283-292">Om en funktion eller åtgärd är relaterad till liknande funktioner eller åtgärder av typen och Functor stöd för deras indata, använder du suffix som i tabellen ovan för att skilja mellan varianter.</span><span class="sxs-lookup"><span data-stu-id="24283-292">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-293">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-293">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="24283-294">Argument och variabler</span><span class="sxs-lookup"><span data-stu-id="24283-294">Arguments and Variables</span></span> ###

<span data-ttu-id="24283-295">Ett viktigt mål för Q #-koden för en funktion eller åtgärd är att den är lätt att läsa och förstå.</span><span class="sxs-lookup"><span data-stu-id="24283-295">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="24283-296">På samma sätt bör namnen på indata-och typ argumenten kommunicera hur en funktion eller ett argument ska användas när det har angetts.</span><span class="sxs-lookup"><span data-stu-id="24283-296">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="24283-297">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-298">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-298">We suggest:</span></span>

- <span data-ttu-id="24283-299">För alla variabel-och typnamn använder `pascalCase` du i stark preferens till `CamelCase` , `snake_case` , eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24283-299">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="24283-300">Inmatade namn ska vara beskrivande. Undvik ett eller två bokstavs namn där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="24283-300">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="24283-301">Åtgärder och funktioner som accepterar exakt ett typ argument bör ange argumentet Type med `T` när dess roll är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="24283-301">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="24283-302">Om en funktion eller åtgärd tar flera typ argument, eller om rollen för ett enda typ argument inte är uppenbar, bör du överväga att använda ett kort kapitaliserat ord som föregås av `T` (t. ex.: `TOutput` ) för varje typ.</span><span class="sxs-lookup"><span data-stu-id="24283-302">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="24283-303">Ta inte med typnamn i argument och variabel namn. den här informationen kan och bör tillhandahållas av din utvecklings miljö.</span><span class="sxs-lookup"><span data-stu-id="24283-303">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="24283-304">Känneteckna skalära typer med deras literala namn ( `flagQubit` ) och mat ris typer med en plural ( `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="24283-304">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="24283-305">För matriser med qubits bör du tänka på att se till att dessa typer `Register` anges genom att namnet syftar på en sekvens av qubits som är nära relaterad på något sätt.</span><span class="sxs-lookup"><span data-stu-id="24283-305">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="24283-306">Variabler som används som index i matriser måste börja med `idx` och måste vara i singular (t. ex.: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="24283-306">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="24283-307">Undvik starkt att använda variabel namn med enkla bokstäver som index. Överväg att minst använda `idx` .</span><span class="sxs-lookup"><span data-stu-id="24283-307">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="24283-308">Variabler som används för att lagra mat ris längder måste börja med `n` och måste vara plural (t. ex.: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="24283-308">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-309">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-309">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="24283-310">Användardefinierad typ med namnet objekt</span><span class="sxs-lookup"><span data-stu-id="24283-310">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="24283-311">Namngivna objekt i användardefinierade typer ska namnges som `CamelCase` , även i indata till UDT-konstruktörer.</span><span class="sxs-lookup"><span data-stu-id="24283-311">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="24283-312">Detta hjälper till att tydligt separera namngivna objekt från referenser till lokalt begränsade variabler när accessorns notation används (t. ex.: `callable::Apply` ) eller kopia-och-Update-notation ( `set arr w/= Data <- newData` ).</span><span class="sxs-lookup"><span data-stu-id="24283-312">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-313">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-313">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-314">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-314">We suggest:</span></span>

- <span data-ttu-id="24283-315">Namngivna objekt i UDT-konstruktörer ska namnges som `CamelCase` , det vill säga de ska börja med inledande versaler.</span><span class="sxs-lookup"><span data-stu-id="24283-315">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="24283-316">Namngivna objekt som löses till åtgärder ska namnges som verb faser.</span><span class="sxs-lookup"><span data-stu-id="24283-316">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="24283-317">Namngivna objekt som inte matchas till åtgärder ska namnges som Substantiv-fraser.</span><span class="sxs-lookup"><span data-stu-id="24283-317">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="24283-318">För UDTs som omsluter åtgärder, ska ett enda namngivet objekt som kallas `Apply` definieras.</span><span class="sxs-lookup"><span data-stu-id="24283-318">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-319">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-319">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-320">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="24283-320">Snippet</span></span> | <span data-ttu-id="24283-321">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-321">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="24283-322">☑</span><span class="sxs-lookup"><span data-stu-id="24283-322">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="24283-323">Namnet `Apply` är en `CamelCase` formaterad verbfras som föreslår att det namngivna objektet är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24283-323">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="24283-324">☒</span><span class="sxs-lookup"><span data-stu-id="24283-324">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="24283-325">Namngivna objekt ska börja med en inledande versal bokstav.</span><span class="sxs-lookup"><span data-stu-id="24283-325">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="24283-326">☒</span><span class="sxs-lookup"><span data-stu-id="24283-326">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="24283-327">Namngivna objekt som löses till Functions ska namnges som Substantiv fraser, inte som verb fraser.</span><span class="sxs-lookup"><span data-stu-id="24283-327">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="24283-328">Inmatade konventioner</span><span class="sxs-lookup"><span data-stu-id="24283-328">Input Conventions</span></span> ##

<span data-ttu-id="24283-329">När en utvecklare anropar en åtgärd eller funktion måste de olika inmatningarna till denna åtgärd eller funktion anges i en viss ordning, vilket ökar den kognitiva belastningen som en utvecklare behöver för att kunna använda ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="24283-329">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="24283-330">I synnerhet är det ofta en störande uppgift att bli medlem i inloggade beställningar: program mera en implementering av en Quantum-algoritm.</span><span class="sxs-lookup"><span data-stu-id="24283-330">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="24283-331">Även om det omfattande IDE-stödet kan minimera detta till en stor del, kan det vara bättre att utforma och följa gemensamma konventioner för att minimera den kognitiva belastningen som införs av ett API.</span><span class="sxs-lookup"><span data-stu-id="24283-331">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="24283-332">Där det är möjligt kan det vara bra att minska antalet indata som förväntas av en åtgärd eller funktion, så att rollen för varje indata är mer direkt uppenbar både för utvecklare som anropar den åtgärden eller funktionen och för utvecklare som läser koden senare.</span><span class="sxs-lookup"><span data-stu-id="24283-332">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="24283-333">Särskilt när det inte är möjligt eller rimligt att minska antalet argument till en åtgärd eller funktion, är det viktigt att ha en konsekvent ordning som minimerar den överraskning som en användare har när de förutsäger ordningen på indata.</span><span class="sxs-lookup"><span data-stu-id="24283-333">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="24283-334">Vi rekommenderar att du använder en konvention för beställning av ingångar som i stor utsträckning härleds från att tänka på partiell program som en generalisering av currying f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="24283-334">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="24283-335">För att delvis använda de första argumenten bör det därför leda till ett anrop som är användbart i sin egen rätt när det är rimligt.</span><span class="sxs-lookup"><span data-stu-id="24283-335">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="24283-336">Följ den här principen, Överväg att använda följande argument ordning:</span><span class="sxs-lookup"><span data-stu-id="24283-336">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="24283-337">Klassiska icke-anrops bara argument, till exempel vinklar, vektorer med befogenheter osv.</span><span class="sxs-lookup"><span data-stu-id="24283-337">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="24283-338">Anrops bara argument (Functions och argument).</span><span class="sxs-lookup"><span data-stu-id="24283-338">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="24283-339">Om både funktioner och åtgärder vidtas som argument, bör du överväga att placera åtgärder efter-funktioner.</span><span class="sxs-lookup"><span data-stu-id="24283-339">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="24283-340">Samlingar som har åtgärd ATS av anrops bara argument på samma sätt som `Map` ,, `Iter` `Enumerate` och `Fold` .</span><span class="sxs-lookup"><span data-stu-id="24283-340">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="24283-341">Qubit-argument som används som kontroller.</span><span class="sxs-lookup"><span data-stu-id="24283-341">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="24283-342">Qubit-argument används som mål.</span><span class="sxs-lookup"><span data-stu-id="24283-342">Qubit arguments used as targets.</span></span>

<span data-ttu-id="24283-343">Överväg en åtgärd `ApplyPhaseEstimationIteration` för användning i fas uppskattning som tar en vinkel och en Oracle, passerar vinkeln till `Rz` modifierad av en matris med olika skalnings faktorer och kontrollerar sedan program i Oracle.</span><span class="sxs-lookup"><span data-stu-id="24283-343">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="24283-344">Vi beställer indata till `ApplyPhaseEstimationIteration` på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="24283-344">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="24283-345">Som ett särskilt fall av att minimera överraskningen efterliknar vissa funktioner och åtgärder beteendet hos de inbyggda functors `Adjoint` och `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="24283-345">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="24283-346">Till exempel `ControlledOnInt<'T>` har typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` , som fungerar som `ControlledOnInt<Qubit[]>(5, _)` `Controlled` Functor, men på villkoret att kontroll registret representerar tillståndet $ \ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="24283-346">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="24283-347">Därför förväntar sig en utvecklare att de indata som ska `ControlledOnInt` anropas för att anropas senast och att den resulterande åtgärden tar som indata `(Qubit[], 'T)` ---samma ordning som resultatet av `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="24283-347">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-348">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-348">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-349">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-349">We suggest:</span></span>

- <span data-ttu-id="24283-350">Använd ingångs ordningar som är förenliga med användningen av partiellt program.</span><span class="sxs-lookup"><span data-stu-id="24283-350">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="24283-351">Använd ingångs ordningar konsekvent med inbyggda functors.</span><span class="sxs-lookup"><span data-stu-id="24283-351">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="24283-352">Placera alla klassiska indata före eventuella Quantum-indata.</span><span class="sxs-lookup"><span data-stu-id="24283-352">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-353">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-353">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="24283-354">Dokumentations konventioner</span><span class="sxs-lookup"><span data-stu-id="24283-354">Documentation Conventions</span></span> ##

<span data-ttu-id="24283-355">Med Q #-språket kan du bifoga dokumentation till åtgärder, funktioner och användardefinierade typer genom att använda särskilt formaterade dokumentations kommentarer.</span><span class="sxs-lookup"><span data-stu-id="24283-355">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="24283-356">De kommentarer som anges med tredubbla snedstreck ( `///` ) är små [DocFX markdown-](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokument som kan användas för att beskriva syftet med varje åtgärd, funktion och användardefinierad typ, vilka data som förväntas, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="24283-356">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="24283-357">Den kompilator som medföljer Quantum Development Kit extraherar dessa kommentarer och använder dem för att hjälpa utskrivna-dokumentationen som på https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="24283-357">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="24283-358">På samma sätt använder den språk server som ingår i Quantum Development Kit dessa kommentarer för att ge användarna hjälp när de hovrar över symboler i sin Q #-kod.</span><span class="sxs-lookup"><span data-stu-id="24283-358">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="24283-359">Genom att använda dokumentations kommentarer kan du därför hjälpa användarna att förstå kod genom att ange en användbar referens för detaljer som inte är lätta att använda i de andra konventionerna i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="24283-359">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="24283-360">
    [Dokumentation kommentar syntax referens](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="24283-360">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="24283-361">För att effektivt kunna använda den här funktionen för att hjälpa användarna, rekommenderar vi att du håller några saker i åtanke när du skriver dokumentations kommentarer.</span><span class="sxs-lookup"><span data-stu-id="24283-361">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-362">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-362">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24283-363">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-363">We suggest:</span></span>

- <span data-ttu-id="24283-364">Varje offentlig funktion, åtgärd och användardefinierad typ ska genast föregås av en dokumentations kommentar.</span><span class="sxs-lookup"><span data-stu-id="24283-364">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="24283-365">Som minst bör varje dokumentations kommentar innehålla följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24283-365">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="24283-366">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="24283-366">Summary</span></span>
    - <span data-ttu-id="24283-367">Indata</span><span class="sxs-lookup"><span data-stu-id="24283-367">Input</span></span>
    - <span data-ttu-id="24283-368">Utdata (om tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="24283-368">Output (if applicable)</span></span>
- <span data-ttu-id="24283-369">Se till att alla sammanfattningar är två meningar eller mindre.</span><span class="sxs-lookup"><span data-stu-id="24283-369">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="24283-370">Om du behöver mer utrymme anger du ett `# Description` avsnitt direkt efter `# Summary` fullständig information.</span><span class="sxs-lookup"><span data-stu-id="24283-370">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="24283-371">Om det är rimligt bör du inte inkludera matematik i sammanfattningar, eftersom alla klienter inte har stöd för TeX notation i sammanfattningar.</span><span class="sxs-lookup"><span data-stu-id="24283-371">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="24283-372">Observera att när du skriver Prose-dokument (t. ex. TeX eller markdown) kan det vara bättre att använda längre linje längd.</span><span class="sxs-lookup"><span data-stu-id="24283-372">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="24283-373">Ange alla relevanta matematiska uttryck i `# Description` avsnittet.</span><span class="sxs-lookup"><span data-stu-id="24283-373">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="24283-374">När du ska beskriva indata upprepar du inte typerna av varje indata som kan härledas av kompileraren och risken som introducerar inkonsekvens.</span><span class="sxs-lookup"><span data-stu-id="24283-374">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="24283-375">Ange lämpliga exempel, var och en i sitt eget `# Example` avsnitt.</span><span class="sxs-lookup"><span data-stu-id="24283-375">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="24283-376">Beskriv kortfattat varje exempel innan du registrerar kod.</span><span class="sxs-lookup"><span data-stu-id="24283-376">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="24283-377">Citera alla relevanta akademiska publikationer (t. ex. dokument, förhandlingar, blogg inlägg och alternativa implementeringar) i ett `# References` avsnitt som en punkt lista med länkar.</span><span class="sxs-lookup"><span data-stu-id="24283-377">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="24283-378">Se till att alla käll hänvisnings länkar är permanenta och oföränderliga identifierare (DOIs eller arXiv siffror), där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="24283-378">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="24283-379">När en åtgärd eller funktion är relaterad till andra åtgärder eller funktioner efter Functor varianter, listar du andra varianter som punkter i `# See Also` avsnittet.</span><span class="sxs-lookup"><span data-stu-id="24283-379">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="24283-380">Lämna en tom kommentars rad mellan nivå 1 ( `/// #` ), men lämna inte en tom rad mellan nivå 2 ( `/// ##` ) avsnitt.</span><span class="sxs-lookup"><span data-stu-id="24283-380">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-381">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-381">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="24283-382">☑</span><span class="sxs-lookup"><span data-stu-id="24283-382">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="24283-383">Formatera konventioner</span><span class="sxs-lookup"><span data-stu-id="24283-383">Formatting Conventions</span></span> ##

<span data-ttu-id="24283-384">Förutom föregående förslag är det bra att hjälpa till att göra kod så läslig som möjligt att använda konsekventa formateringsregler.</span><span class="sxs-lookup"><span data-stu-id="24283-384">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="24283-385">Sådan formatering av regler efter art tenderar att vara något godtycklig och starkt uppdaterad till personliga smak uppgifter.</span><span class="sxs-lookup"><span data-stu-id="24283-385">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="24283-386">Vi rekommenderar dock att du underhåller en konsekvent uppsättning format konventioner inom en grupp medarbetare och särskilt för stora Q #-projekt, till exempel Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="24283-386">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="24283-387">Dessa regler kan tillämpas automatiskt med hjälp av det format verktyg som är integrerat med Q #-kompilatorn.</span><span class="sxs-lookup"><span data-stu-id="24283-387">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24283-388">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24283-388">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="24283-389">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24283-389">We suggest:</span></span>

- <span data-ttu-id="24283-390">Använd fyra blank steg i stället för flikar för portabilitet.</span><span class="sxs-lookup"><span data-stu-id="24283-390">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="24283-391">I VS-kod:</span><span class="sxs-lookup"><span data-stu-id="24283-391">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="24283-392">Rad brytning vid 79 tecken där det är rimligt.</span><span class="sxs-lookup"><span data-stu-id="24283-392">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="24283-393">Använd blank steg runt binära operatorer.</span><span class="sxs-lookup"><span data-stu-id="24283-393">Use spaces around binary operators.</span></span>
- <span data-ttu-id="24283-394">Använd blank steg på båda sidorna av kolon som används för typ anteckningar.</span><span class="sxs-lookup"><span data-stu-id="24283-394">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="24283-395">Använd ett enda blank steg efter kommatecken i matris-och tuple-litteraler (t. ex.: i indata till funktioner och åtgärder).</span><span class="sxs-lookup"><span data-stu-id="24283-395">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="24283-396">Använd inte blank steg efter Function-, operation-eller UDT-namn eller efter `@` deklarationerna i Attribute.</span><span class="sxs-lookup"><span data-stu-id="24283-396">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="24283-397">Varje deklaration för attribut bör finnas på en egen rad.</span><span class="sxs-lookup"><span data-stu-id="24283-397">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24283-398">Exempel</span><span class="sxs-lookup"><span data-stu-id="24283-398">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24283-399">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="24283-399">Snippet</span></span> | <span data-ttu-id="24283-400">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24283-400">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="24283-401">☒</span><span class="sxs-lookup"><span data-stu-id="24283-401">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="24283-402">Använd blank steg runt binära operatorer.</span><span class="sxs-lookup"><span data-stu-id="24283-402">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="24283-403">☒</span><span class="sxs-lookup"><span data-stu-id="24283-403">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="24283-404">Använd blank steg runt Skriv anteckningens kolon.</span><span class="sxs-lookup"><span data-stu-id="24283-404">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="24283-405">☑</span><span class="sxs-lookup"><span data-stu-id="24283-405">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="24283-406">Objekt i indataströmmen har rätt avstånd för läsbarhet.</span><span class="sxs-lookup"><span data-stu-id="24283-406">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="24283-407">☒</span><span class="sxs-lookup"><span data-stu-id="24283-407">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="24283-408">Blank steg ska undertryckas efter Function-, operation-eller UDT-namn.</span><span class="sxs-lookup"><span data-stu-id="24283-408">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***
