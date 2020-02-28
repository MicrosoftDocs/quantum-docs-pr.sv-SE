---
title: 'Microsoft Q # stil guide'
description: 'Lär dig mer om namngivning, indatamängd, dokumentation och formatering för Q #-program och-bibliotek.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3c8e432378ec563a197a5b87000c3e90cadb8e18
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907451"
---
# <a name="q-style-guide"></a>Stil guide för Q # #
## <a name="general-conventions"></a>Allmänna konventioner ##

De konventioner som föreslås i den här guiden är avsedda att hjälpa till att göra program och bibliotek skrivna i Q # lättare att läsa och förstå.

## <a name="guidance"></a>Riktlinjer

Vi rekommenderar:

- Bortse aldrig från en konvention om du inte gör det avsiktligt för att tillhandahålla mer läsbar och begriplig kod för dina användare.

## <a name="naming-conventions"></a>Namngivnings konventioner ##

Vid erbjudandet från Quantum Development Kit strävar vi efter funktions-och åtgärds namn som hjälper fantastiska utvecklare att skriva program som är lätta att läsa och som minimerar överraskningen.
En viktig del av detta är att när vi väljer namn för funktioner, åtgärder och typer, upprättar vi den *vokabulär* som programmerare använder för att uttrycka Quantum-koncept. med våra val kan vi antingen hjälpa dig eller hindra dem att kommunicera tydligt.
På så sätt får vi ett ansvar för oss att se till att namnen vi presenterar ger klarhet i stället för skymt.
I det här avsnittet beskriver vi hur vi uppfyller denna skyldighet i termer av uttryckliga rikt linjer som hjälper oss att göra det bästa med utvecklings gruppen för Q-nummer.

### <a name="operations-and-functions"></a>Åtgärder och funktioner ###

Ett av de första saker som ett namn bör fastställa är om en specifik symbol representerar en funktion eller en åtgärd.
Skillnaden mellan Functions och Operations är avgörande för att förstå hur ett kod block beter sig.
För att kunna kommunicera mellan funktioner och åtgärder för användare, förlitar vi oss på att det finns Quantum åtgärder i Q #-modeller genom användning av sido effekter.
Det vill säga en åtgärd *gör* något.

Funktionen kontrast beskriver däremot de matematiska relationerna mellan data.
Uttrycket `Sin(PI() / 2.0)` *är* `1.0`och innebär ingenting om status för ett program eller dess qubits.

Med sammanfattningen fungerar åtgärder saker och ting.
Den här skillnaden antyder att vi namnger åtgärder som verb och fungerar som substantiv.

> [!NOTE]
> När en användardefinierad typ deklareras, definieras en ny funktion som konstruerar instanser av den typen implicit på samma gång.
> Från och med detta perspektiv ska användardefinierade typer namnges som substantiv, så att både själva typen och konstruktorn-funktionen har konsekventa namn.

Om det är rimligt bör du se till att åtgärds namnen börjar med verb som tydligt anger vilken åtgärd som vidtas.
Några exempel:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Ett förtjänar särskilt omnämnande är när en åtgärd tar en annan åtgärd som inmatad och anropar den.
I sådana fall är åtgärden som vidtas av inläsnings åtgärden inte klar när den yttre åtgärden definieras, så att det högra verbet inte är omedelbart klart.
Vi rekommenderar verb `Apply`, som i `ApplyIf`, `ApplyToEach`och `ApplyToFirst`.
Andra verb kan vara användbara även i det här fallet, som i `IterateThroughCartesianPower`.

| Verb | Förväntad påverkan |
| ---- | ------ |
| Använd | En åtgärd som angetts som indata kallas |
| Assert | En hypotes om resultatet av en möjlig Quantum-mätning kontrol leras av en simulator |
| Beräkningen | Ett klassiskt värde returneras som representerar en uppskattning som skapats från en eller flera mätningar |
| Mått | En Quantum-mätning utförs och resultatet returneras till användaren |
| Förbereda | Ett visst register av qubits initieras i ett visst tillstånd |
| Exempel | Ett klassiskt värde returneras slumpmässigt från en distribution |

För functions, rekommenderar vi att du undviker användningen av verb som prioriterar vanliga Substantiv (se rikt linjer för rätt Substantiv nedan) eller adjektiv:

- `ConstantArray`
- `Head`
- `LookupFunction`

I nästan alla fall föreslår vi i stort sett att du använder tidigare Participles, om det är lämpligt att ange att ett funktions namn är starkt anslutet till en åtgärd eller en sido effekt någon annan stans i ett Quantum-program.
Exempel: `ControlledOnInt` använder participle-formen av verbet "Control" för att ange att funktionen fungerar som en adjektiv för att ändra dess argument.
Det här namnet har ytterligare fördelar med att matcha semantiken för de inbyggda `Controlled` Functor, enligt beskrivningen nedan.
På samma sätt kan du använda _agent Substantiv_ för att skapa Function-och UDT-namn från åtgärds namn, som i fallet med namnet `Encoder` för en UDT som är starkt kopplad till `Encode`.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Använd verb för åtgärds namn.
- Använd Substantiv eller adjektiv för funktions namn.
- Använd Substantiv för användardefinierade typer och attribut.
- För alla anrops bara namn använder du `CamelCase` i starka preferenser för att `pascalCase`, `snake_case`eller `ANGRY_CASE`. Se särskilt till att anrops bara namn börjar med versaler.
- För alla lokala variabler använder du `pascalCase` i starka preferenser för att `CamelCase`, `snake_case`eller `ANGRY_CASE`. Se särskilt till att lokala variabler börjar med små bokstäver.
- Undvik att använda under streck `_` i funktions-och åtgärds namn. om det behövs ytterligare nivåer av hierarkin, använder du namn områden och namn områdes Ali Aset.

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Namn | Beskrivning |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Rensa användningen av ett verb ("reflektera") för att ange hur åtgärden ska fungera. |
| ☒ | <s>`operation XRotation`</s> | Användning av en Substantiv-fras föreslår funktion i stället för åtgärd. |
| ☒ | <s>`operation search_oracle`</s> | Användning av `snake_case` bestrider Q #-notation. |
| ☒ | <s>`operation Search_Oracle`</s> | Användning av under streck till åtgärds namn bestrider Q #-notation. |
| ☑ | `function StatePreparationOracle` | Användning av Substantiv fras föreslår att funktionen returnerar en åtgärd. |
| ☑ | `function EqualityFact` | Clear use of Substantiv ("faktumet") för att indikera att detta är en funktion, medan adjektiv. |
| ☒ | <s>`function GetRotationAngles`</s> | Användning av verb ("Get") föreslår att detta är en åtgärd. |
| ☑ | `newtype GeneratorTerm` | Användningen av Substantiv frasen avser tydligt resultatet av att anropa UDT-konstruktorn. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | Användning av verbfras föreslår att UDT-konstruktorn är en åtgärd. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | Användningen av Substantiv frasen kommunicerar användningen av attributet. |

***

### <a name="shorthand-and-abbreviations"></a>Kort och förkortningar ###

Ovanstående råd trots detta är att det finns många former av kort som ser gemensam och genomgripande användning i Quantum Computing.
Vi rekommenderar att du använder ett befintligt och vanligt kort ställe där det finns, särskilt för åtgärder som är unika för driften av mål datorn.
Vi kan till exempel välja namnet `X` i stället för `ApplyX`och `Rz` i stället för `RotateAboutZ`.
Vid användning av sådant kort ska åtgärds namnen vara alla versaler (t. ex.: `MAJ`).

En del Försiktighet krävs vid tillämpning av denna konvention när det gäller vanliga akronymer och initialisms, till exempel "QFT" för "Quantum Fourier Transform".
Vi föreslår följande allmänna .NET-konventioner för användning av akronymer och initialisms i fullständiga namn, vilket föreskriver att:

- akronymer och initialisms med två bokstäver anges i versaler (t. ex.: `BE` för "big-endian").
- alla längre akronymer och initialisms är namngivna i `CamelCase` (t. ex.: `Qft` för "Quantum Fourier Transform")

Därför kan en åtgärd som implementerar QFT anropas `QFT` som kort eller skrivs ut som `ApplyQft`.

För de flesta vanliga åtgärder och funktioner kan det vara önskvärt att ange ett namn på kort texten som ett _alias_ i ett längre format:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Betrakta ofta godkända och vanliga namn på kort skrift vid behov.
- Använd versaler för kort skrift.
- Använd versaler för korta (två bokstäver) akronymer och initialisms.
- Använd `CamelCase` för längre (tre eller fler bokstäver) akronymer och initialisms.

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Namn | Beskrivning |
|---|------|-------------|
| ☑ | `X` | Välförstått kort för "tillämpa en $X $-transformering" |
| ☑ | `CNOT` | Välförståttt snabb kort för "styrd-NOT" |
| ☒ | <s>`Cnot`</s> | Kort får inte finnas i `CamelCase`. |
| ☑ | `ApplyQft` | Vanlig inledande "QFT" visas som en del av ett långt format namn. |
| ☑ | `QFT` | Vanlig inledande "QFT" visas som en del av ett kort namn. |



***


### <a name="proper-nouns-in-names"></a>Rätt Substantiv i namn ###

I fysik är det vanligt att namnge saker efter att den första personen har publicerat dem, men de flesta icke-physicists är inte bekanta med allas namn och all historik.
Att förlita sig på namngivnings konventioner från fysiken kan därför ge en betydande barriär för att registrera sig, eftersom användare från andra bakgrunder måste lära sig ett stort antal ogenomskinliga namn för att kunna använda vanliga åtgärder och begrepp.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Därför rekommenderar vi att när rimliga, vanliga substantiv som beskriver ett koncept antas i starka preferenser till rätt substantiv som beskriver ett Koncepts publicerings historik.
Som ett särskilt exempel kallas funktionen för enkel kontrollerad växling och dubblerad kontrollerade inte åtgärder för åtgärderna "Fredkin" och "Toffoli" i den akademiska dokumentationen, men identifieras i Q # främst som `CSWAP` och `CCNOT`.
I båda fallen ger kommentarer till API-dokumentation synonyma namn baserat på korrekta substantiv, tillsammans med alla lämpliga citat tecken.

Den här inställningen är särskilt viktig, men det är särskilt viktigt att viss användning av rätt Substantiv alltid är nödvändig: Q # följer tradition som har angetts av många klassiska språk, till exempel, och refererar till `Bool` typer i referens till boolesk logik, som i sin tur har värdet George bool.
Några Quantum-koncept kan liknas på liknande sätt, inklusive `Pauli` typ som är inbyggd på språket Q #.
Genom att minimera användningen av rätt substantiv, om sådan användning inte är nödvändig, minskar vi effekten där rätt Substantiv inte kan undvikas rimligen.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance) 

Vi rekommenderar:

- Undvik att använda rätt Substantiv i namn.

# <a name="examples"></a>[Exempel](#tab/examples)

***

### <a name="type-conversions"></a>Typ konverteringar ###

Eftersom Q # är ett starkt och statiskt typ språk kan ett värde av en typ endast användas som ett värde av en annan typ med hjälp av ett explicit anrop till en typ konverterings funktion.
Detta är i motsats till språk som tillåter att värden ändrar typer implicit (t. ex.: typ befordran) eller genom databyte.
Resultatet är att typ konverterings funktioner spelar en viktig roll i Q # biblioteks utveckling och utgör ett av de vanligaste besluten om namngivning.
Vi noterar dock att eftersom typ konverteringen alltid är _deterministisk_, kan de skrivas som funktioner och därmed omfattas av ovanstående råd.
I synnerhet rekommenderar vi att typ konverterings funktioner aldrig ska namnges som verb (t. ex.: `ConvertToX`) eller adverb-betecknings fraser (`ToX`), men ska vara namngivna som adjektiv förpositions fraser som anger käll-och mål typerna (`XAsY`).
När du anger mat ris typer i typ konverterings funktions namn rekommenderar vi stenografiska `Arr`.
Spärr av exceptionella omständigheter, vi rekommenderar att alla typ konverterings funktioner får namnet med `As` så att de snabbt kan identifieras.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Om en funktion konverterar ett värde av typen `X` till ett värde av typen `Y`använder du antingen namnet `AsY` eller `XAsY`.

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Namn | Beskrivning |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | Förpositionen "till" resulterar i en verbfras som indikerar en åtgärd och inte en funktion. |
| ☒ | <s>`AsDouble`</s> | Indatatypen är inte klar från funktions namnet. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Indata-och utmatnings typer visas i fel ordning. |
| ☑ | `ResultArrAsBoolArr` | Både typerna av indata och utdata är tydliga. |

***

### <a name="private-or-internal-names"></a>Privata eller interna namn ###

I många fall är ett namn enbart avsett för användning internt i ett bibliotek eller projekt, och är inte en garanterad del av API: et som erbjuds av ett bibliotek.
Det är praktiskt att tydligt ange att det här är fallet när du namnger funktioner och åtgärder så att oavsiktliga beroenden i intern kod görs uppenbara.
Om en åtgärd eller funktion inte är avsedd för direkt användning, utan bör istället användas av en matchande anrops funktion som fungerar genom partiell tillämpning, bör du överväga att använda ett namn som börjar med `_` för det anrop som används delvis.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Om en funktion, åtgärd eller användardefinierad typ inte är en del av det offentliga API: t för ett Q #-bibliotek eller program, se till att dess namn börjar med ett inledande under streck (`_`).

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Namn | Beskrivning |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | Under streck `_` ska inte visas i slutet av namnet. |
| ☑ | `_ApplyDecomposedOperation` | Under streck `_` i början visar tydligt att den här åtgärden endast är för intern användning. |

***

### <a name="variants"></a>Varianter ###

Även om den här begränsningen inte finns kvar i framtida versioner av Q #, är det i själva fallet att det ofta finns grupper med relaterade åtgärder eller funktioner som särskiljs genom att functors stöd för indata eller av konkreta typer av argument.
Dessa grupper kan särskiljas med hjälp av samma rot namn, följt av en eller två bokstäver som anger dess variant.

| Huvudnamnssuffix | Betydelse |
|--------|---------|
| `A` | Indatatyp förväntades stödja `Adjoint` |
| `C` | Indatatyp förväntades stödja `Controlled` |
| `CA` | Förväntad information som stöd för `Controlled` och `Adjoint` |
| `I` | Indata eller indata är av typen `Int` |
| `D` | Indata eller indata är av typen `Double` |
| `L` | Indata eller indata är av typen `BigInt` |

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Om en funktion eller åtgärd inte är relaterad till liknande funktioner eller åtgärder som stöds av typerna och Functor stöd för deras indata, ska du inte använda ett suffix.
- Om en funktion eller åtgärd är relaterad till liknande funktioner eller åtgärder av typen och Functor stöd för deras indata, använder du suffix som i tabellen ovan för att skilja mellan varianter.

# <a name="examples"></a>[Exempel](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argument och variabler ###

Ett viktigt mål för Q #-koden för en funktion eller åtgärd är att den är lätt att läsa och förstå.
På samma sätt bör namnen på indata-och typ argumenten kommunicera hur en funktion eller ett argument ska användas när det har angetts.


# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- För alla variabel-och typnamn använder du `pascalCase` i starka preferenser för att `CamelCase`, `snake_case`eller `ANGRY_CASE`.
- Inmatade namn ska vara beskrivande. Undvik ett eller två bokstavs namn där det är möjligt.
- Åtgärder och funktioner som accepterar exakt ett typ argument bör ange argumentet Type genom att `T` när dess roll är uppenbar.
- Om en funktion eller åtgärd tar flera typ argument, eller om rollen för ett enda typ argument inte är uppenbar, bör du överväga att använda ett kort kapitaliserat ord som föregås av `T` (t. ex.: `TOutput`) för varje typ.
- Ta inte med typnamn i argument och variabel namn. den här informationen kan och bör tillhandahållas av din utvecklings miljö.
- Anger skalära typer med deras literala namn (`flagQubit`) och mat ris typer med en plural (`measResults`).
  För qubits är det särskilt att överväga sådana typer av `Register` där namnet refererar till en sekvens av qubits som är nära relaterade på något sätt.
- Variabler som används som index i matriser ska börja med `idx` och bör vara singular (t. ex.: `things[idxThing]`).
  Undvik starkt att använda variabel namn med enkla bokstäver som index. Överväg att använda `idx` minst.
- Variabler som används för att lagra mat ris längder måste börja med `n` och måste vara plural (t. ex.: `nThings`).

# <a name="examples"></a>[Exempel](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Användardefinierad typ med namnet objekt ###

Namngivna objekt i användardefinierade typer ska namnges som `CamelCase`, även i indata till UDT-konstruktörer.
Detta hjälper till att tydligt separera namngivna objekt från referenser till lokalt begränsade variabler när accessor notation används (t. ex.: `callable::Apply`) eller kopia-och-uppdaterings notation (`set arr w/= Data <- newData`).

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Namngivna objekt i UDT-konstruktörer ska namnges som `CamelCase`. det vill säga att de börjar med inledande versaler.
- Namngivna objekt som löses till åtgärder ska namnges som verb faser.
- Namngivna objekt som inte matchas till åtgärder ska namnges som Substantiv-fraser.
- För UDTs som radbryts, ska ett enda namngivet objekt som kallas `Apply` definieras.

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Bitar | Beskrivning |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Namnet `Apply` är en `CamelCase`formaterad verbfras som föreslår att det namngivna objektet är en åtgärd. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Namngivna objekt ska börja med en inledande versal bokstav. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Namngivna objekt som löses till Functions ska namnges som Substantiv fraser, inte som verb fraser. |

***

## <a name="input-conventions"></a>Inmatade konventioner ##

När en utvecklare anropar en åtgärd eller funktion måste de olika inmatningarna till denna åtgärd eller funktion anges i en viss ordning, vilket ökar den kognitiva belastningen som en utvecklare behöver för att kunna använda ett bibliotek.
I synnerhet är det ofta en störande uppgift att bli medlem i inloggade beställningar: program mera en implementering av en Quantum-algoritm.
Även om det omfattande IDE-stödet kan minimera detta till en stor del, kan det vara bättre att utforma och följa gemensamma konventioner för att minimera den kognitiva belastningen som införs av ett API.

Där det är möjligt kan det vara bra att minska antalet indata som förväntas av en åtgärd eller funktion, så att rollen för varje indata är mer direkt uppenbar både för utvecklare som anropar den åtgärden eller funktionen och för utvecklare som läser koden senare.
Särskilt när det inte är möjligt eller rimligt att minska antalet argument till en åtgärd eller funktion, är det viktigt att ha en konsekvent ordning som minimerar den överraskning som en användare har när de förutsäger ordningen på indata.

Vi rekommenderar att du använder en konvention för beställning av ingångar som i stor utsträckning härleds från att tänka på partiell program som en generalisering av currying f (x, y) ≡ f (x) (y).
För att delvis använda de första argumenten bör det därför leda till ett anrop som är användbart i sin egen rätt när det är rimligt.
Följ den här principen, Överväg att använda följande argument ordning:

- Klassiska icke-anrops bara argument, till exempel vinklar, vektorer med befogenheter osv.
- Anrops bara argument (Functions och argument).
  Om både funktioner och åtgärder vidtas som argument, bör du överväga att placera åtgärder efter-funktioner.
- Samlingar som används av anrops bara argument på samma sätt som `Map`, `Iter`, `Enumerate`och `Fold`.
- Qubit-argument som används som kontroller.
- Qubit-argument används som mål.

Överväg en åtgärd `ApplyPhaseEstimationIteration` för användning i fas uppskattning som tar en vinkel och en Oracle, så att du kan ändra vinkeln till `Rz` modifierad av en matris med olika skalnings faktorer och sedan kontrol lera program i Oracle.
Vi beställer indata till `ApplyPhaseEstimationIteration` på följande sätt:

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
Som ett specialfall av att minimera överraskningen efterliknar vissa funktioner och åtgärder beteendet hos den inbyggda functors-`Adjoint` och `Controlled`.
`ControlledOnInt<'T>` har till exempel typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, till exempel `ControlledOnInt<Qubit[]>(5, _)` fungerar som `Controlled` Functor, men på villkoret att kontroll registret representerar tillståndet $ \ket{5} = \ket{101}$.
Därför förväntar sig en utvecklare att indata till `ControlledOnInt` placera det anropande som transformeras sist, och att den resulterande åtgärden tar som indata `(Qubit[], 'T)`---samma ordning som resultatet av `Controlled` Functor.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Använd ingångs ordningar som är förenliga med användningen av partiellt program.
- Använd ingångs ordningar konsekvent med inbyggda functors.
- Placera alla klassiska indata före eventuella Quantum-indata.

# <a name="examples"></a>[Exempel](#tab/examples)

***

## <a name="documentation-conventions"></a>Dokumentationskonventioner ##

Med Q #-språket kan du bifoga dokumentation till åtgärder, funktioner och användardefinierade typer genom att använda särskilt formaterade dokumentations kommentarer.
De här dokumentations kommentarerna är små [DocFX markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) -dokument som kan användas för att beskriva syftet med varje åtgärd, funktion och användardefinierad typ, vilka indata varje förväntar sig, och så vidare.`///`
Den kompilator som medföljer Quantum Development Kit extraherar dessa kommentarer och använder dem för att hjälpa utskrivna-dokumentation som liknar den i https://docs.microsoft.com/quantum.
På samma sätt använder den språk server som ingår i Quantum Development Kit dessa kommentarer för att ge användarna hjälp när de hovrar över symboler i sin Q #-kod.
Genom att använda dokumentations kommentarer kan du därför hjälpa användarna att förstå kod genom att ange en användbar referens för detaljer som inte är lätta att använda i de andra konventionerna i det här dokumentet.

<div class="nextstepaction">
    [Dokumentation kommentar syntax referens](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

För att effektivt kunna använda den här funktionen för att hjälpa användarna, rekommenderar vi att du håller några saker i åtanke när du skriver dokumentations kommentarer.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance)

Vi rekommenderar:

- Varje offentlig funktion, åtgärd och användardefinierad typ ska genast föregås av en dokumentations kommentar.
- Som minst bör varje dokumentations kommentar innehålla följande avsnitt:
    - Sammanfattning
    - Indata
    - Utdata (om tillämpligt)
- Se till att alla sammanfattningar är två meningar eller mindre. Om du behöver mer utrymme kan du ange ett `# Description` avsnitt direkt efter `# Summary` med fullständig information.
- Om det är rimligt bör du inte inkludera matematik i sammanfattningar, eftersom alla klienter inte har stöd för TeX notation i sammanfattningar. Observera att när du skriver Prose-dokument (t. ex. TeX eller markdown) kan det vara bättre att använda längre linje längd.
- Ange alla relevanta matematiska uttryck i avsnittet `# Description`.
- När du ska beskriva indata upprepar du inte typerna av varje indata som kan härledas av kompileraren och risken som introducerar inkonsekvens.
- Ange lämpliga exempel, var och en i ett eget `# Example` avsnitt.
- Beskriv kortfattat varje exempel innan du registrerar kod.
- Citera alla relevanta akademiska publikationer (t. ex. dokument, förhandlingar, blogg inlägg och alternativa implementeringar) i en `# References`-sektion som en punkt lista med länkar.
- Se till att alla käll hänvisnings länkar är permanenta och oföränderliga identifierare (DOIs eller arXiv siffror), där det är möjligt.
- När en åtgärd eller funktion är relaterad till andra åtgärder eller funktioner efter Functor varianter, listar du andra varianter som punkter i avsnittet `# See Also`.
- Lämna en tom kommentar rad mellan nivå 1-avsnitt (`/// #`), men lämna inte en tom rad mellan nivå 2 (`/// ##`) avsnitt.

# <a name="examples"></a>[Exempel](#tab/examples)

#### <a name=""></a>☑ ####

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

## <a name="formatting-conventions"></a>Formatera konventioner ##

Förutom föregående förslag är det bra att hjälpa till att göra kod så läslig som möjligt att använda konsekventa formateringsregler.
Sådan formatering av regler efter art tenderar att vara något godtycklig och starkt uppdaterad till personliga smak uppgifter.
Vi rekommenderar dock att du underhåller en konsekvent uppsättning format konventioner inom en grupp medarbetare och särskilt för stora Q #-projekt, till exempel Quantum Development Kit.
Dessa regler kan tillämpas automatiskt med hjälp av det format verktyg som är integrerat med Q #-kompilatorn.

# <a name="guidance"></a>[Riktlinjer](#tab/guidance) 

Vi rekommenderar:

- Använd fyra blank steg i stället för flikar för portabilitet.
  I VS-kod:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Rad brytning vid 79 tecken där det är rimligt.
- Använd blank steg runt binära operatorer.
- Använd blank steg på båda sidorna av kolon som används för typ anteckningar.
- Använd ett enda blank steg efter kommatecken i matris-och tuple-litteraler (t. ex.: i indata till funktioner och åtgärder).
- Använd inte blank steg efter Function-, operation-eller UDT-namn eller efter `@` i Attribute-deklarationer.
- Varje deklaration för attribut bör finnas på en egen rad.

# <a name="examples"></a>[Exempel](#tab/examples)

|   | Bitar | Beskrivning |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Använd blank steg runt binära operatorer. |
| ☒ | <s>`target:Qubit`</s> | Använd blank steg runt Skriv anteckningens kolon. |
| ☑ | `Example(a, b, c)` | Objekt i indataströmmen har rätt avstånd för läsbarhet. |
| ☒ | <s>`Example (a, b, c)`</s> | Blank steg ska undertryckas efter Function-, operation-eller UDT-namn. |

***

