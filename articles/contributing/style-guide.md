---
title: 'Microsoft Q # stil guide'
description: 'Lär dig mer om namngivning, indatamängd, dokumentation och formatering för Q #-program och-bibliotek.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: dfb2b1779e3ddc77fc74697bc4dc2904b1a0c70f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426931"
---
# <a name="q-style-guide"></a><span data-ttu-id="24d0f-103">Stil guide för Q #</span><span class="sxs-lookup"><span data-stu-id="24d0f-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="24d0f-104">Allmänna konventioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-104">General Conventions</span></span> ##

<span data-ttu-id="24d0f-105">De konventioner som föreslås i den här guiden är avsedda att hjälpa till att göra program och bibliotek skrivna i Q # lättare att läsa och förstå.</span><span class="sxs-lookup"><span data-stu-id="24d0f-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="24d0f-106">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-106">Guidance</span></span>

<span data-ttu-id="24d0f-107">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-107">We suggest:</span></span>

- <span data-ttu-id="24d0f-108">Bortse aldrig från en konvention om du inte gör det avsiktligt för att tillhandahålla mer läsbar och begriplig kod för dina användare.</span><span class="sxs-lookup"><span data-stu-id="24d0f-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="24d0f-109">Namngivnings konventioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-109">Naming Conventions</span></span> ##

<span data-ttu-id="24d0f-110">Vid erbjudandet från Quantum Development Kit strävar vi efter funktions-och åtgärds namn som hjälper fantastiska utvecklare att skriva program som är lätta att läsa och som minimerar överraskningen.</span><span class="sxs-lookup"><span data-stu-id="24d0f-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="24d0f-111">En viktig del av detta är att när vi väljer namn för funktioner, åtgärder och typer, upprättar vi den *vokabulär* som programmerare använder för att uttrycka Quantum-koncept. med våra val kan vi antingen hjälpa dig eller hindra dem att kommunicera tydligt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="24d0f-112">På så sätt får vi ett ansvar för oss att se till att namnen vi presenterar ger klarhet i stället för skymt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="24d0f-113">I det här avsnittet beskriver vi hur vi uppfyller denna skyldighet i termer av uttryckliga rikt linjer som hjälper oss att göra det bästa med utvecklings gruppen för Q-nummer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="24d0f-114">Åtgärder och funktioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-114">Operations and Functions</span></span> ###

<span data-ttu-id="24d0f-115">Ett av de första saker som ett namn bör fastställa är om en specifik symbol representerar en funktion eller en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="24d0f-116">Skillnaden mellan Functions och Operations är avgörande för att förstå hur ett kod block beter sig.</span><span class="sxs-lookup"><span data-stu-id="24d0f-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="24d0f-117">För att kunna kommunicera mellan funktioner och åtgärder för användare, förlitar vi oss på att det finns Quantum åtgärder i Q #-modeller genom användning av sido effekter.</span><span class="sxs-lookup"><span data-stu-id="24d0f-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="24d0f-118">Det vill säga en åtgärd *gör* något.</span><span class="sxs-lookup"><span data-stu-id="24d0f-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="24d0f-119">Funktionen kontrast beskriver däremot de matematiska relationerna mellan data.</span><span class="sxs-lookup"><span data-stu-id="24d0f-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="24d0f-120">Uttrycket `Sin(PI() / 2.0)` *är* `1.0` och innebär ingenting om status för ett program eller dess qubits.</span><span class="sxs-lookup"><span data-stu-id="24d0f-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="24d0f-121">Med sammanfattningen fungerar åtgärder saker och ting.</span><span class="sxs-lookup"><span data-stu-id="24d0f-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="24d0f-122">Den här skillnaden antyder att vi namnger åtgärder som verb och fungerar som substantiv.</span><span class="sxs-lookup"><span data-stu-id="24d0f-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="24d0f-123">När en användardefinierad typ deklareras, definieras en ny funktion som konstruerar instanser av den typen implicit på samma gång.</span><span class="sxs-lookup"><span data-stu-id="24d0f-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="24d0f-124">Från och med detta perspektiv ska användardefinierade typer namnges som substantiv, så att både själva typen och konstruktorn-funktionen har konsekventa namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="24d0f-125">Om det är rimligt bör du se till att åtgärds namnen börjar med verb som tydligt anger vilken åtgärd som vidtas.</span><span class="sxs-lookup"><span data-stu-id="24d0f-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="24d0f-126">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="24d0f-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="24d0f-127">Ett förtjänar särskilt omnämnande är när en åtgärd tar en annan åtgärd som inmatad och anropar den.</span><span class="sxs-lookup"><span data-stu-id="24d0f-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="24d0f-128">I sådana fall är åtgärden som vidtas av inläsnings åtgärden inte klar när den yttre åtgärden definieras, så att det högra verbet inte är omedelbart klart.</span><span class="sxs-lookup"><span data-stu-id="24d0f-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="24d0f-129">Vi rekommenderar verbet `Apply` , som i `ApplyIf` , `ApplyToEach` och `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="24d0f-130">Andra verb kan vara användbara även i det här fallet, som i `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="24d0f-131">Verb</span><span class="sxs-lookup"><span data-stu-id="24d0f-131">Verb</span></span> | <span data-ttu-id="24d0f-132">Förväntad påverkan</span><span class="sxs-lookup"><span data-stu-id="24d0f-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="24d0f-133">Använd</span><span class="sxs-lookup"><span data-stu-id="24d0f-133">Apply</span></span> | <span data-ttu-id="24d0f-134">En åtgärd som angetts som indata kallas</span><span class="sxs-lookup"><span data-stu-id="24d0f-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="24d0f-135">Assert</span><span class="sxs-lookup"><span data-stu-id="24d0f-135">Assert</span></span> | <span data-ttu-id="24d0f-136">En hypotes om resultatet av en möjlig Quantum-mätning kontrol leras av en simulator</span><span class="sxs-lookup"><span data-stu-id="24d0f-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="24d0f-137">Beräkning</span><span class="sxs-lookup"><span data-stu-id="24d0f-137">Estimate</span></span> | <span data-ttu-id="24d0f-138">Ett klassiskt värde returneras som representerar en uppskattning som skapats från en eller flera mätningar</span><span class="sxs-lookup"><span data-stu-id="24d0f-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="24d0f-139">Mått</span><span class="sxs-lookup"><span data-stu-id="24d0f-139">Measure</span></span> | <span data-ttu-id="24d0f-140">En Quantum-mätning utförs och resultatet returneras till användaren</span><span class="sxs-lookup"><span data-stu-id="24d0f-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="24d0f-141">Förbereda</span><span class="sxs-lookup"><span data-stu-id="24d0f-141">Prepare</span></span> | <span data-ttu-id="24d0f-142">Ett visst register av qubits initieras i ett visst tillstånd</span><span class="sxs-lookup"><span data-stu-id="24d0f-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="24d0f-143">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-143">Sample</span></span> | <span data-ttu-id="24d0f-144">Ett klassiskt värde returneras slumpmässigt från en distribution</span><span class="sxs-lookup"><span data-stu-id="24d0f-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="24d0f-145">För functions, rekommenderar vi att du undviker användningen av verb som prioriterar vanliga Substantiv (se rikt linjer för rätt Substantiv nedan) eller adjektiv:</span><span class="sxs-lookup"><span data-stu-id="24d0f-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="24d0f-146">I nästan alla fall föreslår vi i stort sett att du använder tidigare Participles, om det är lämpligt att ange att ett funktions namn är starkt anslutet till en åtgärd eller en sido effekt någon annan stans i ett Quantum-program.</span><span class="sxs-lookup"><span data-stu-id="24d0f-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="24d0f-147">Till exempel `ControlledOnInt` används del participle-formen av verbet "Control" för att ange att funktionen fungerar som en adjektiv för att ändra dess argument.</span><span class="sxs-lookup"><span data-stu-id="24d0f-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="24d0f-148">Det här namnet har ytterligare fördelar med att matcha semantiken för de inbyggda `Controlled` Functor, enligt beskrivningen nedan.</span><span class="sxs-lookup"><span data-stu-id="24d0f-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="24d0f-149">På samma sätt kan du använda _agent Substantiv_ för att skapa Function-och UDT-namn från åtgärds namn, som i fallet med namnet `Encoder` på en UDT som är starkt associerad med `Encode` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-150">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-151">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-151">We suggest:</span></span>

- <span data-ttu-id="24d0f-152">Använd verb för åtgärds namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="24d0f-153">Använd Substantiv eller adjektiv för funktions namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="24d0f-154">Använd Substantiv för användardefinierade typer och attribut.</span><span class="sxs-lookup"><span data-stu-id="24d0f-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="24d0f-155">För alla namn som kan anropas använder `CamelCase` du i stark preferens till `pascalCase` , `snake_case` eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="24d0f-156">Se särskilt till att anrops bara namn börjar med versaler.</span><span class="sxs-lookup"><span data-stu-id="24d0f-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="24d0f-157">För alla lokala variabler använder `pascalCase` du i stark preferens till `CamelCase` , `snake_case` eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="24d0f-158">Se särskilt till att lokala variabler börjar med små bokstäver.</span><span class="sxs-lookup"><span data-stu-id="24d0f-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="24d0f-159">Undvik att använda under streck `_` i funktions-och åtgärds namn. om det behövs ytterligare nivåer av hierarkin använder du namn rymder och namn rymds alias.</span><span class="sxs-lookup"><span data-stu-id="24d0f-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-160">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-161">Name</span><span class="sxs-lookup"><span data-stu-id="24d0f-161">Name</span></span> | <span data-ttu-id="24d0f-162">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24d0f-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24d0f-163">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="24d0f-164">Rensa användningen av ett verb ("reflektera") för att ange hur åtgärden ska fungera.</span><span class="sxs-lookup"><span data-stu-id="24d0f-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="24d0f-165">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="24d0f-166">Användning av en Substantiv-fras föreslår funktion i stället för åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="24d0f-167">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="24d0f-168">Användning av `snake_case` bryter mot Q #-notation.</span><span class="sxs-lookup"><span data-stu-id="24d0f-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="24d0f-169">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="24d0f-170">Användning av under streck till åtgärds namn bestrider Q #-notation.</span><span class="sxs-lookup"><span data-stu-id="24d0f-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="24d0f-171">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="24d0f-172">Användning av Substantiv fras föreslår att funktionen returnerar en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="24d0f-173">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="24d0f-174">Clear use of Substantiv ("faktumet") för att indikera att detta är en funktion, medan adjektiv.</span><span class="sxs-lookup"><span data-stu-id="24d0f-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="24d0f-175">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="24d0f-176">Användning av verb ("Get") föreslår att detta är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="24d0f-177">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="24d0f-178">Användningen av Substantiv frasen avser tydligt resultatet av att anropa UDT-konstruktorn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="24d0f-179">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="24d0f-180">Användning av verbfras föreslår att UDT-konstruktorn är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="24d0f-181">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="24d0f-182">Användningen av Substantiv frasen kommunicerar användningen av attributet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="24d0f-183">Kort och förkortningar</span><span class="sxs-lookup"><span data-stu-id="24d0f-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="24d0f-184">Ovanstående råd trots detta är att det finns många former av kort som ser gemensam och genomgripande användning i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="24d0f-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="24d0f-185">Vi rekommenderar att du använder ett befintligt och vanligt kort ställe där det finns, särskilt för åtgärder som är unika för driften av mål datorn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="24d0f-186">Exempelvis väljer vi namnet `X` i stället för `ApplyX` , och `Rz` istället för `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="24d0f-187">Vid användning av sådant kort ska åtgärds namnen vara alla versaler (t. ex.: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="24d0f-188">En del Försiktighet krävs vid tillämpning av denna konvention när det gäller vanliga akronymer och initialisms, till exempel "QFT" för "Quantum Fourier Transform".</span><span class="sxs-lookup"><span data-stu-id="24d0f-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="24d0f-189">Vi föreslår följande allmänna .NET-konventioner för användning av akronymer och initialisms i fullständiga namn, vilket föreskriver att:</span><span class="sxs-lookup"><span data-stu-id="24d0f-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="24d0f-190">akronymer och initialisms med två bokstäver anges i versaler (t. ex.: `BE` för "big-endian").</span><span class="sxs-lookup"><span data-stu-id="24d0f-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="24d0f-191">alla längre akronymer och initialisms är namngivna i `CamelCase` (t. ex.: `Qft` "Quantum Fourier Transform")</span><span class="sxs-lookup"><span data-stu-id="24d0f-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="24d0f-192">Därför kan en åtgärd som implementerar QFT anropas `QFT` som stenografisk eller skrivas ut som `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="24d0f-193">För de flesta vanliga åtgärder och funktioner kan det vara önskvärt att ange ett namn på kort texten som ett _alias_ i ett längre format:</span><span class="sxs-lookup"><span data-stu-id="24d0f-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="24d0f-194">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-195">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-195">We suggest:</span></span>

- <span data-ttu-id="24d0f-196">Betrakta ofta godkända och vanliga namn på kort skrift vid behov.</span><span class="sxs-lookup"><span data-stu-id="24d0f-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="24d0f-197">Använd versaler för kort skrift.</span><span class="sxs-lookup"><span data-stu-id="24d0f-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="24d0f-198">Använd versaler för korta (två bokstäver) akronymer och initialisms.</span><span class="sxs-lookup"><span data-stu-id="24d0f-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="24d0f-199">Används `CamelCase` för längre (tre eller fler bokstäver) akronymer och initialisms.</span><span class="sxs-lookup"><span data-stu-id="24d0f-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-200">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-201">Name</span><span class="sxs-lookup"><span data-stu-id="24d0f-201">Name</span></span> | <span data-ttu-id="24d0f-202">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24d0f-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24d0f-203">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-203">☑</span></span> | `X` | <span data-ttu-id="24d0f-204">Välförstått kort för "tillämpa en $X $-transformering"</span><span class="sxs-lookup"><span data-stu-id="24d0f-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="24d0f-205">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-205">☑</span></span> | `CNOT` | <span data-ttu-id="24d0f-206">Välförståttt snabb kort för "styrd-NOT"</span><span class="sxs-lookup"><span data-stu-id="24d0f-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="24d0f-207">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="24d0f-208">Snabb kort bör inte vara i `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="24d0f-209">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="24d0f-210">Vanlig inledande "QFT" visas som en del av ett långt format namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="24d0f-211">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-211">☑</span></span> | `QFT` | <span data-ttu-id="24d0f-212">Vanlig inledande "QFT" visas som en del av ett kort namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="24d0f-213">Rätt Substantiv i namn</span><span class="sxs-lookup"><span data-stu-id="24d0f-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="24d0f-214">I fysik är det vanligt att namnge saker efter att den första personen har publicerat dem, men de flesta icke-physicists är inte bekanta med allas namn och all historik.</span><span class="sxs-lookup"><span data-stu-id="24d0f-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="24d0f-215">Att förlita sig på namngivnings konventioner från fysiken kan därför ge en betydande barriär för att registrera sig, eftersom användare från andra bakgrunder måste lära sig ett stort antal ogenomskinliga namn för att kunna använda vanliga åtgärder och begrepp.</span><span class="sxs-lookup"><span data-stu-id="24d0f-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="24d0f-216">Därför rekommenderar vi att när rimliga, vanliga substantiv som beskriver ett koncept antas i starka preferenser till rätt substantiv som beskriver ett Koncepts publicerings historik.</span><span class="sxs-lookup"><span data-stu-id="24d0f-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="24d0f-217">Som ett särskilt exempel kallas den oavsiktligt kontrollerade VÄXLINGen och den dubblerade kontrollerade inte åtgärderna "Fredkin" och "Toffoli"-åtgärder i den akademiska dokumentationen, men de identifieras i Q # främst som `CSWAP` och `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="24d0f-218">I båda fallen ger kommentarer till API-dokumentation synonyma namn baserat på korrekta substantiv, tillsammans med alla lämpliga citat tecken.</span><span class="sxs-lookup"><span data-stu-id="24d0f-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="24d0f-219">Den här inställningen är särskilt viktig, men det är särskilt viktigt att viss användning av rätt Substantiv alltid är nödvändig: Q # följer tradition som har angetts av många klassiska språk, till exempel, och refererar till `Bool` typer i referens till boolesk logik, som i sin tur har värdet George bool.</span><span class="sxs-lookup"><span data-stu-id="24d0f-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="24d0f-220">Några Quantum-koncept har liknande namn på liknande sätt, inklusive den `Pauli` typ som är inbyggd på språket Q #.</span><span class="sxs-lookup"><span data-stu-id="24d0f-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="24d0f-221">Genom att minimera användningen av rätt substantiv, om sådan användning inte är nödvändig, minskar vi effekten där rätt Substantiv inte kan undvikas rimligen.</span><span class="sxs-lookup"><span data-stu-id="24d0f-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-222">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="24d0f-223">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-223">We suggest:</span></span>

- <span data-ttu-id="24d0f-224">Undvik att använda rätt Substantiv i namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-225">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="24d0f-226">Typ konverteringar</span><span class="sxs-lookup"><span data-stu-id="24d0f-226">Type Conversions</span></span> ###

<span data-ttu-id="24d0f-227">Eftersom Q # är ett starkt och statiskt typ språk kan ett värde av en typ endast användas som ett värde av en annan typ med hjälp av ett explicit anrop till en typ konverterings funktion.</span><span class="sxs-lookup"><span data-stu-id="24d0f-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="24d0f-228">Detta är i motsats till språk som tillåter att värden ändrar typer implicit (t. ex.: typ befordran) eller genom databyte.</span><span class="sxs-lookup"><span data-stu-id="24d0f-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="24d0f-229">Resultatet är att typ konverterings funktioner spelar en viktig roll i Q # biblioteks utveckling och utgör ett av de vanligaste besluten om namngivning.</span><span class="sxs-lookup"><span data-stu-id="24d0f-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="24d0f-230">Vi noterar dock att eftersom typ konverteringen alltid är _deterministisk_, kan de skrivas som funktioner och därmed omfattas av ovanstående råd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="24d0f-231">I synnerhet rekommenderar vi att typ konverterings funktioner aldrig ska namnges som verb (t. ex.: `ConvertToX` ) eller adverb-förpositions fraser ( `ToX` ), men ska vara namngivna som adjektiv befattnings fraser som anger käll-och mål typerna ( `XAsY` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="24d0f-232">När du anger mat ris typer i typ konverterings funktions namn rekommenderar vi kort skrift `Arr` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="24d0f-233">Spärr av exceptionella omständigheter, vi rekommenderar att alla typer av konverterings funktioner får namnet med hjälp av `As` så att de snabbt kan identifieras.</span><span class="sxs-lookup"><span data-stu-id="24d0f-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-234">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-235">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-235">We suggest:</span></span>

- <span data-ttu-id="24d0f-236">Om en funktion konverterar ett värde av typen `X` till ett värde av typen `Y` använder du antingen namnet `AsY` eller `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-237">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-238">Name</span><span class="sxs-lookup"><span data-stu-id="24d0f-238">Name</span></span> | <span data-ttu-id="24d0f-239">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24d0f-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24d0f-240">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="24d0f-241">Förpositionen "till" resulterar i en verbfras som indikerar en åtgärd och inte en funktion.</span><span class="sxs-lookup"><span data-stu-id="24d0f-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="24d0f-242">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="24d0f-243">Indatatypen är inte klar från funktions namnet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="24d0f-244">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="24d0f-245">Indata-och utmatnings typer visas i fel ordning.</span><span class="sxs-lookup"><span data-stu-id="24d0f-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="24d0f-246">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="24d0f-247">Både typerna av indata och utdata är tydliga.</span><span class="sxs-lookup"><span data-stu-id="24d0f-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="24d0f-248">Privata eller interna namn</span><span class="sxs-lookup"><span data-stu-id="24d0f-248">Private or Internal Names</span></span> ###

<span data-ttu-id="24d0f-249">I många fall är ett namn enbart avsett för användning internt i ett bibliotek eller projekt, och är inte en garanterad del av API: et som erbjuds av ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="24d0f-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="24d0f-250">Det är praktiskt att tydligt ange att det här är fallet när du namnger funktioner och åtgärder så att oavsiktliga beroenden i intern kod görs uppenbara.</span><span class="sxs-lookup"><span data-stu-id="24d0f-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="24d0f-251">Om en åtgärd eller funktion inte är avsedd för direkt användning, utan bör istället användas av en matchande anrops funktion som fungerar i partiellt program, bör du överväga att använda ett namn som börjar med `_` för det anrop som används delvis.</span><span class="sxs-lookup"><span data-stu-id="24d0f-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-252">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-253">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-253">We suggest:</span></span>

- <span data-ttu-id="24d0f-254">Om en funktion, åtgärd eller användardefinierad typ inte är en del av det offentliga API: t för ett Q #-bibliotek eller program, se till att dess namn börjar med ett inledande under streck ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-255">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-256">Name</span><span class="sxs-lookup"><span data-stu-id="24d0f-256">Name</span></span> | <span data-ttu-id="24d0f-257">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24d0f-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="24d0f-258">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="24d0f-259">Under streck `_` ska inte visas i slutet av namnet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="24d0f-260">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="24d0f-261">Under streck `_` i början visar tydligt att den här åtgärden endast är för intern användning.</span><span class="sxs-lookup"><span data-stu-id="24d0f-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="24d0f-262">Varianter</span><span class="sxs-lookup"><span data-stu-id="24d0f-262">Variants</span></span> ###

<span data-ttu-id="24d0f-263">Även om den här begränsningen inte finns kvar i framtida versioner av Q #, är det i själva fallet att det ofta finns grupper med relaterade åtgärder eller funktioner som särskiljs genom att functors stöd för indata eller av konkreta typer av argument.</span><span class="sxs-lookup"><span data-stu-id="24d0f-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="24d0f-264">Dessa grupper kan särskiljas med hjälp av samma rot namn, följt av en eller två bokstäver som anger dess variant.</span><span class="sxs-lookup"><span data-stu-id="24d0f-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="24d0f-265">Huvudnamnssuffix</span><span class="sxs-lookup"><span data-stu-id="24d0f-265">Suffix</span></span> | <span data-ttu-id="24d0f-266">Betydelse</span><span class="sxs-lookup"><span data-stu-id="24d0f-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="24d0f-267">Indatatyp förväntades stödja`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="24d0f-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="24d0f-268">Indatatyp förväntades stödja`Controlled`</span><span class="sxs-lookup"><span data-stu-id="24d0f-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="24d0f-269">Indatatyp förväntades stödja `Controlled` och`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="24d0f-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="24d0f-270">Indata eller indata är av typen`Int`</span><span class="sxs-lookup"><span data-stu-id="24d0f-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="24d0f-271">Indata eller indata är av typen`Double`</span><span class="sxs-lookup"><span data-stu-id="24d0f-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="24d0f-272">Indata eller indata är av typen`BigInt`</span><span class="sxs-lookup"><span data-stu-id="24d0f-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="24d0f-273">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-274">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-274">We suggest:</span></span>

- <span data-ttu-id="24d0f-275">Om en funktion eller åtgärd inte är relaterad till liknande funktioner eller åtgärder som stöds av typerna och Functor stöd för deras indata, ska du inte använda ett suffix.</span><span class="sxs-lookup"><span data-stu-id="24d0f-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="24d0f-276">Om en funktion eller åtgärd är relaterad till liknande funktioner eller åtgärder av typen och Functor stöd för deras indata, använder du suffix som i tabellen ovan för att skilja mellan varianter.</span><span class="sxs-lookup"><span data-stu-id="24d0f-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-277">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="24d0f-278">Argument och variabler</span><span class="sxs-lookup"><span data-stu-id="24d0f-278">Arguments and Variables</span></span> ###

<span data-ttu-id="24d0f-279">Ett viktigt mål för Q #-koden för en funktion eller åtgärd är att den är lätt att läsa och förstå.</span><span class="sxs-lookup"><span data-stu-id="24d0f-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="24d0f-280">På samma sätt bör namnen på indata-och typ argumenten kommunicera hur en funktion eller ett argument ska användas när det har angetts.</span><span class="sxs-lookup"><span data-stu-id="24d0f-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="24d0f-281">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-282">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-282">We suggest:</span></span>

- <span data-ttu-id="24d0f-283">För alla variabel-och typnamn använder `pascalCase` du i stark preferens till `CamelCase` , `snake_case` , eller `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="24d0f-284">Inmatade namn ska vara beskrivande. Undvik ett eller två bokstavs namn där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="24d0f-285">Åtgärder och funktioner som accepterar exakt ett typ argument bör ange argumentet Type med `T` när dess roll är uppenbar.</span><span class="sxs-lookup"><span data-stu-id="24d0f-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="24d0f-286">Om en funktion eller åtgärd tar flera typ argument, eller om rollen för ett enda typ argument inte är uppenbar, bör du överväga att använda ett kort kapitaliserat ord som föregås av `T` (t. ex.: `TOutput` ) för varje typ.</span><span class="sxs-lookup"><span data-stu-id="24d0f-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="24d0f-287">Ta inte med typnamn i argument och variabel namn. den här informationen kan och bör tillhandahållas av din utvecklings miljö.</span><span class="sxs-lookup"><span data-stu-id="24d0f-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="24d0f-288">Känneteckna skalära typer med deras literala namn ( `flagQubit` ) och mat ris typer med en plural ( `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="24d0f-289">För matriser med qubits bör du tänka på att se till att dessa typer `Register` anges genom att namnet syftar på en sekvens av qubits som är nära relaterad på något sätt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="24d0f-290">Variabler som används som index i matriser måste börja med `idx` och måste vara i singular (t. ex.: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="24d0f-291">Undvik starkt att använda variabel namn med enkla bokstäver som index. Överväg att minst använda `idx` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="24d0f-292">Variabler som används för att lagra mat ris längder måste börja med `n` och måste vara plural (t. ex.: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-293">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="24d0f-294">Användardefinierad typ med namnet objekt</span><span class="sxs-lookup"><span data-stu-id="24d0f-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="24d0f-295">Namngivna objekt i användardefinierade typer ska namnges som `CamelCase` , även i indata till UDT-konstruktörer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="24d0f-296">Detta hjälper till att tydligt separera namngivna objekt från referenser till lokalt begränsade variabler när accessorns notation används (t. ex.: `callable::Apply` ) eller kopia-och-Update-notation ( `set arr w/= Data <- newData` ).</span><span class="sxs-lookup"><span data-stu-id="24d0f-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-297">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-298">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-298">We suggest:</span></span>

- <span data-ttu-id="24d0f-299">Namngivna objekt i UDT-konstruktörer ska namnges som `CamelCase` , det vill säga de ska börja med inledande versaler.</span><span class="sxs-lookup"><span data-stu-id="24d0f-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="24d0f-300">Namngivna objekt som löses till åtgärder ska namnges som verb faser.</span><span class="sxs-lookup"><span data-stu-id="24d0f-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="24d0f-301">Namngivna objekt som inte matchas till åtgärder ska namnges som Substantiv-fraser.</span><span class="sxs-lookup"><span data-stu-id="24d0f-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="24d0f-302">För UDTs som omsluter åtgärder, ska ett enda namngivet objekt som kallas `Apply` definieras.</span><span class="sxs-lookup"><span data-stu-id="24d0f-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-303">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-304">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="24d0f-304">Snippet</span></span> | <span data-ttu-id="24d0f-305">Description</span><span class="sxs-lookup"><span data-stu-id="24d0f-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="24d0f-306">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="24d0f-307">Namnet `Apply` är en `CamelCase` formaterad verbfras som föreslår att det namngivna objektet är en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="24d0f-308">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="24d0f-309">Namngivna objekt ska börja med en inledande versal bokstav.</span><span class="sxs-lookup"><span data-stu-id="24d0f-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="24d0f-310">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="24d0f-311">Namngivna objekt som löses till Functions ska namnges som Substantiv fraser, inte som verb fraser.</span><span class="sxs-lookup"><span data-stu-id="24d0f-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="24d0f-312">Inmatade konventioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-312">Input Conventions</span></span> ##

<span data-ttu-id="24d0f-313">När en utvecklare anropar en åtgärd eller funktion måste de olika inmatningarna till denna åtgärd eller funktion anges i en viss ordning, vilket ökar den kognitiva belastningen som en utvecklare behöver för att kunna använda ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="24d0f-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="24d0f-314">I synnerhet är det ofta en störande uppgift att bli medlem i inloggade beställningar: program mera en implementering av en Quantum-algoritm.</span><span class="sxs-lookup"><span data-stu-id="24d0f-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="24d0f-315">Även om det omfattande IDE-stödet kan minimera detta till en stor del, kan det vara bättre att utforma och följa gemensamma konventioner för att minimera den kognitiva belastningen som införs av ett API.</span><span class="sxs-lookup"><span data-stu-id="24d0f-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="24d0f-316">Där det är möjligt kan det vara bra att minska antalet indata som förväntas av en åtgärd eller funktion, så att rollen för varje indata är mer direkt uppenbar både för utvecklare som anropar den åtgärden eller funktionen och för utvecklare som läser koden senare.</span><span class="sxs-lookup"><span data-stu-id="24d0f-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="24d0f-317">Särskilt när det inte är möjligt eller rimligt att minska antalet argument till en åtgärd eller funktion, är det viktigt att ha en konsekvent ordning som minimerar den överraskning som en användare har när de förutsäger ordningen på indata.</span><span class="sxs-lookup"><span data-stu-id="24d0f-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="24d0f-318">Vi rekommenderar att du använder en konvention för beställning av ingångar som i stor utsträckning härleds från att tänka på partiell program som en generalisering av currying f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="24d0f-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="24d0f-319">För att delvis använda de första argumenten bör det därför leda till ett anrop som är användbart i sin egen rätt när det är rimligt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="24d0f-320">Följ den här principen, Överväg att använda följande argument ordning:</span><span class="sxs-lookup"><span data-stu-id="24d0f-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="24d0f-321">Klassiska icke-anrops bara argument, till exempel vinklar, vektorer med befogenheter osv.</span><span class="sxs-lookup"><span data-stu-id="24d0f-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="24d0f-322">Anrops bara argument (Functions och argument).</span><span class="sxs-lookup"><span data-stu-id="24d0f-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="24d0f-323">Om både funktioner och åtgärder vidtas som argument, bör du överväga att placera åtgärder efter-funktioner.</span><span class="sxs-lookup"><span data-stu-id="24d0f-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="24d0f-324">Samlingar som har åtgärd ATS av anrops bara argument på samma sätt som `Map` ,, `Iter` `Enumerate` och `Fold` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="24d0f-325">Qubit-argument som används som kontroller.</span><span class="sxs-lookup"><span data-stu-id="24d0f-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="24d0f-326">Qubit-argument används som mål.</span><span class="sxs-lookup"><span data-stu-id="24d0f-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="24d0f-327">Överväg en åtgärd `ApplyPhaseEstimationIteration` för användning i fas uppskattning som tar en vinkel och en Oracle, passerar vinkeln till `Rz` modifierad av en matris med olika skalnings faktorer och kontrollerar sedan program i Oracle.</span><span class="sxs-lookup"><span data-stu-id="24d0f-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="24d0f-328">Vi beställer indata till `ApplyPhaseEstimationIteration` på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="24d0f-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="24d0f-329">Som ett särskilt fall av att minimera överraskningen efterliknar vissa funktioner och åtgärder beteendet hos de inbyggda functors `Adjoint` och `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="24d0f-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="24d0f-330">Till exempel `ControlledOnInt<'T>` har typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` , som fungerar som `ControlledOnInt<Qubit[]>(5, _)` `Controlled` Functor, men på villkoret att kontroll registret representerar tillståndet $ \ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="24d0f-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="24d0f-331">Därför förväntar sig en utvecklare att de indata som ska `ControlledOnInt` anropas för att anropas senast och att den resulterande åtgärden tar som indata `(Qubit[], 'T)` ---samma ordning som resultatet av `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="24d0f-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-332">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-333">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-333">We suggest:</span></span>

- <span data-ttu-id="24d0f-334">Använd ingångs ordningar som är förenliga med användningen av partiellt program.</span><span class="sxs-lookup"><span data-stu-id="24d0f-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="24d0f-335">Använd ingångs ordningar konsekvent med inbyggda functors.</span><span class="sxs-lookup"><span data-stu-id="24d0f-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="24d0f-336">Placera alla klassiska indata före eventuella Quantum-indata.</span><span class="sxs-lookup"><span data-stu-id="24d0f-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-337">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="24d0f-338">Dokumentations konventioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-338">Documentation Conventions</span></span> ##

<span data-ttu-id="24d0f-339">Med Q #-språket kan du bifoga dokumentation till åtgärder, funktioner och användardefinierade typer genom att använda särskilt formaterade dokumentations kommentarer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="24d0f-340">De kommentarer som anges med tredubbla snedstreck ( `///` ) är små [DocFX markdown-](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) dokument som kan användas för att beskriva syftet med varje åtgärd, funktion och användardefinierad typ, vilka data som förväntas, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="24d0f-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="24d0f-341">Den kompilator som medföljer Quantum Development Kit extraherar dessa kommentarer och använder dem för att hjälpa utskrivna-dokumentationen som på https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="24d0f-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="24d0f-342">På samma sätt använder den språk server som ingår i Quantum Development Kit dessa kommentarer för att ge användarna hjälp när de hovrar över symboler i sin Q #-kod.</span><span class="sxs-lookup"><span data-stu-id="24d0f-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="24d0f-343">Genom att använda dokumentations kommentarer kan du därför hjälpa användarna att förstå kod genom att ange en användbar referens för detaljer som inte är lätta att använda i de andra konventionerna i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="24d0f-344">
    [Dokumentation kommentar syntax referens](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="24d0f-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="24d0f-345">För att effektivt kunna använda den här funktionen för att hjälpa användarna, rekommenderar vi att du håller några saker i åtanke när du skriver dokumentations kommentarer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-346">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="24d0f-347">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-347">We suggest:</span></span>

- <span data-ttu-id="24d0f-348">Varje offentlig funktion, åtgärd och användardefinierad typ ska genast föregås av en dokumentations kommentar.</span><span class="sxs-lookup"><span data-stu-id="24d0f-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="24d0f-349">Som minst bör varje dokumentations kommentar innehålla följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="24d0f-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="24d0f-350">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="24d0f-350">Summary</span></span>
    - <span data-ttu-id="24d0f-351">Indata</span><span class="sxs-lookup"><span data-stu-id="24d0f-351">Input</span></span>
    - <span data-ttu-id="24d0f-352">Utdata (om tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="24d0f-352">Output (if applicable)</span></span>
- <span data-ttu-id="24d0f-353">Se till att alla sammanfattningar är två meningar eller mindre.</span><span class="sxs-lookup"><span data-stu-id="24d0f-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="24d0f-354">Om du behöver mer utrymme anger du ett `# Description` avsnitt direkt efter `# Summary` fullständig information.</span><span class="sxs-lookup"><span data-stu-id="24d0f-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="24d0f-355">Om det är rimligt bör du inte inkludera matematik i sammanfattningar, eftersom alla klienter inte har stöd för TeX notation i sammanfattningar.</span><span class="sxs-lookup"><span data-stu-id="24d0f-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="24d0f-356">Observera att när du skriver Prose-dokument (t. ex. TeX eller markdown) kan det vara bättre att använda längre linje längd.</span><span class="sxs-lookup"><span data-stu-id="24d0f-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="24d0f-357">Ange alla relevanta matematiska uttryck i `# Description` avsnittet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="24d0f-358">När du ska beskriva indata upprepar du inte typerna av varje indata som kan härledas av kompileraren och risken som introducerar inkonsekvens.</span><span class="sxs-lookup"><span data-stu-id="24d0f-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="24d0f-359">Ange lämpliga exempel, var och en i sitt eget `# Example` avsnitt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="24d0f-360">Beskriv kortfattat varje exempel innan du registrerar kod.</span><span class="sxs-lookup"><span data-stu-id="24d0f-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="24d0f-361">Citera alla relevanta akademiska publikationer (t. ex. dokument, förhandlingar, blogg inlägg och alternativa implementeringar) i ett `# References` avsnitt som en punkt lista med länkar.</span><span class="sxs-lookup"><span data-stu-id="24d0f-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="24d0f-362">Se till att alla käll hänvisnings länkar är permanenta och oföränderliga identifierare (DOIs eller arXiv siffror), där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="24d0f-363">När en åtgärd eller funktion är relaterad till andra åtgärder eller funktioner efter Functor varianter, listar du andra varianter som punkter i `# See Also` avsnittet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="24d0f-364">Lämna en tom kommentars rad mellan nivå 1 ( `/// #` ), men lämna inte en tom rad mellan nivå 2 ( `/// ##` ) avsnitt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-365">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="24d0f-366">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="24d0f-367">Formatera konventioner</span><span class="sxs-lookup"><span data-stu-id="24d0f-367">Formatting Conventions</span></span> ##

<span data-ttu-id="24d0f-368">Förutom föregående förslag är det bra att hjälpa till att göra kod så läslig som möjligt att använda konsekventa formateringsregler.</span><span class="sxs-lookup"><span data-stu-id="24d0f-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="24d0f-369">Sådan formatering av regler efter art tenderar att vara något godtycklig och starkt uppdaterad till personliga smak uppgifter.</span><span class="sxs-lookup"><span data-stu-id="24d0f-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="24d0f-370">Vi rekommenderar dock att du underhåller en konsekvent uppsättning format konventioner inom en grupp medarbetare och särskilt för stora Q #-projekt, till exempel Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="24d0f-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="24d0f-371">Dessa regler kan tillämpas automatiskt med hjälp av det format verktyg som är integrerat med Q #-kompilatorn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="24d0f-372">Vägledning</span><span class="sxs-lookup"><span data-stu-id="24d0f-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="24d0f-373">Vi rekommenderar:</span><span class="sxs-lookup"><span data-stu-id="24d0f-373">We suggest:</span></span>

- <span data-ttu-id="24d0f-374">Använd fyra blank steg i stället för flikar för portabilitet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="24d0f-375">I VS-kod:</span><span class="sxs-lookup"><span data-stu-id="24d0f-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="24d0f-376">Rad brytning vid 79 tecken där det är rimligt.</span><span class="sxs-lookup"><span data-stu-id="24d0f-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="24d0f-377">Använd blank steg runt binära operatorer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="24d0f-378">Använd blank steg på båda sidorna av kolon som används för typ anteckningar.</span><span class="sxs-lookup"><span data-stu-id="24d0f-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="24d0f-379">Använd ett enda blank steg efter kommatecken i matris-och tuple-litteraler (t. ex.: i indata till funktioner och åtgärder).</span><span class="sxs-lookup"><span data-stu-id="24d0f-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="24d0f-380">Använd inte blank steg efter Function-, operation-eller UDT-namn eller efter `@` deklarationerna i Attribute.</span><span class="sxs-lookup"><span data-stu-id="24d0f-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="24d0f-381">Varje deklaration för attribut bör finnas på en egen rad.</span><span class="sxs-lookup"><span data-stu-id="24d0f-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="24d0f-382">Exempel</span><span class="sxs-lookup"><span data-stu-id="24d0f-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="24d0f-383">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="24d0f-383">Snippet</span></span> | <span data-ttu-id="24d0f-384">Description</span><span class="sxs-lookup"><span data-stu-id="24d0f-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="24d0f-385">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="24d0f-386">Använd blank steg runt binära operatorer.</span><span class="sxs-lookup"><span data-stu-id="24d0f-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="24d0f-387">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="24d0f-388">Använd blank steg runt Skriv anteckningens kolon.</span><span class="sxs-lookup"><span data-stu-id="24d0f-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="24d0f-389">☑</span><span class="sxs-lookup"><span data-stu-id="24d0f-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="24d0f-390">Objekt i indataströmmen har rätt avstånd för läsbarhet.</span><span class="sxs-lookup"><span data-stu-id="24d0f-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="24d0f-391">☒</span><span class="sxs-lookup"><span data-stu-id="24d0f-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="24d0f-392">Blank steg ska undertryckas efter Function-, operation-eller UDT-namn.</span><span class="sxs-lookup"><span data-stu-id="24d0f-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

