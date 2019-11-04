---
title: 'Q #-instruktioner | Microsoft Docs'
description: 'Q #-instruktioner'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184873"
---
# <a name="statements-and-other-constructs"></a>Instruktioner och andra konstruktioner

## <a name="comments"></a>Kommentarer

Kommentarer börjar med två snedstreck, `//`och fortsätter till slutet av raden.
En kommentar kan visas var som helst i en Q #-källfil.

### <a name="documentation-comments"></a>Dokumentations kommentarer

Kommentarer som börjar med tre snedstreck, `///`, behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.
I så fall tas deras innehåll som dokumentation för den definierade typen av anropad eller användardefinierad typ, som för andra .NET-språk.

I `///` kommentarer formateras text som en del av API-dokumentationen som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.
Som tillägg till markdown kan kors referenser till åtgärder, funktioner och användardefinierade typer i Q # inkluderas med hjälp av `@"<ref target>"`, där `<ref target>` ersätts av det fullständigt kvalificerade namnet på det kod objekt som refereras till.
Alternativt kan en dokumentations motor också ha stöd för ytterligare markdown-tillägg.

Exempel:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

Följande namn identifieras som dokumentations kommentars rubriker.

- **Sammanfattning**: en kort sammanfattning av beteendet för en funktion eller åtgärd, eller av syftet av en typ. Det första stycket i sammanfattningen används för hov rings information. Det bör vara oformaterad text.
- **Beskrivning**: en beskrivning av beteendet för en funktion eller åtgärd, eller syftet med en typ. Sammanfattningen och beskrivningen sammanfogas för att bilda den genererade dokumentations filen för funktionen, åtgärden eller typen.
  Beskrivningen får innehålla infogade symboler och ekvationer med LaTeX-format.
- **Inmatade**: en beskrivning av indataströmmen för en funktion eller funktion.
  Kan innehålla ytterligare markdown-underavsnitt som anger varje enskilt element i indataströmmen.
- **Utdata**: en beskrivning av tuppeln som returneras av en åtgärd eller funktion.
- **Typ parametrar**: ett tomt avsnitt som innehåller ytterligare ett underavsnitt för varje generisk typ parameter.
- **Exempel**: ett kort exempel på en åtgärd, funktion eller typ som används.
- **Anmärkningar**: Diverse Prose som beskriver viss aspekt av åtgärden, funktionen eller typen.
- **Se även**: en lista över fullständigt kvalificerade namn som visar relaterade funktioner, åtgärder eller användardefinierade typer.
- **Referenser**: en lista över referenser och citat för det objekt som dokumenteras.

## <a name="namespaces"></a>Namnområden

Varje Q #-åtgärd, funktion och användardefinierad typ definieras i ett namn område.
Q # följer samma regler för namngivning som andra .NET-språk.
Q # stöder dock inte relativa referenser till namn områden.
Det vill säga, om namn området `a.b` har öppnats, matchas inte en referens till ett åtgärds namn `c.d` till en åtgärd med fullständigt namn `a.b.c.d`.

I ett namn områdes block kan `open`-direktivet användas för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn. Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet. `open`-direktivet gäller hela namn områdes blocket i en fil.

En typ eller en anropad typ som har definierats i en annan namnrymd som inte är öppen i det aktuella namn området måste refereras till av sitt fullständigt kvalificerade namn.
Till exempel måste en åtgärd som heter `Op` i namn området `X.Y` refereras till av dess fullständigt kvalificerade namn `X.Y.Op`, om inte `X.Y`-namnområdet har öppnats tidigare i det aktuella blocket. Som nämnts ovan, även om `X`-namnområdet har öppnats, går det inte att referera till åtgärden som `Y.Op`.
Om ett kort namn `Z` för `X.Y` har definierats i det namn området och filen måste `Op` kallas `Z.Op`. 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open`-direktiv.
Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.

## <a name="formatting"></a>Formatering

De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;`.
Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block kräver inte ett avslutande semikolon.
Varje instruktions Beskrivning noterar om avslutande semikolon krävs.

Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.
Att ha flera instruktioner på en enda rad bör undvikas.

## <a name="statement-blocks"></a>Instruktions block

Q #-instruktioner grupperas i uttrycks block.
Ett instruktions block börjar med en inledande `{` och slutar med en stängnings `}`.

Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.

## <a name="symbol-binding-and-assignment"></a>Symbol bindning och tilldelning

Q # skiljer sig mellan föränderligt och oföränderliga symboler.
I allmänhet uppmuntras användningen av oföränderliga symboler eftersom den tillåter kompilatorn att utföra mer optimeringar.

Den vänstra sidan av bindningen består av en symbol tupel och den högra sidan av ett uttryck.

Eftersom alla Q #-typer är värde typer – med qubits tar en lite speciell roll – en "kopia" skapas när ett värde är kopplat till en symbol eller när en symbol har bundits. Detta är att säga att Q # är detsamma som om en kopia skapades för tilldelningen. Detta omfattar även matriser. Naturligtvis i praktiken är det bara de relevanta delarna som faktiskt återskapas vid behov. 

### <a name="tuple-deconstruction"></a>Tupel och avkonstruktion

Om den högra sidan av bindningen är en tupel, kan denna tupel bli inbyggd vid tilldelningen.
Sådana dekonstruktioner kan omfatta kapslade tupler och all fullständig eller delvis inbyggnad är giltig så länge formen på tuppeln till höger är kompatibel med formen på symbolens tupel.
Tuple-inkonstruktion kan också användas när den högra sidan av `=` är ett par värdes uttryck.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Oföränderliga symboler

Oföränderliga symboler binds med hjälp av `let`-instruktionen.
Detta är ungefär detsamma som variabel deklaration och initiering på språk som C#, förutom att Q #-symboler, när det är kopplat, inte kan ändras. `let` bindningar är oföränderliga.

En oföränderlig bindning består av nyckelordet `let`följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda symbolerna till och ett avslutande semikolon.
Typen för den eller de kopplade symbolerna härleds baserat på uttrycket på den högra sidan.

### <a name="mutable-symbols"></a>Föränderligt symboler

Föränderligt-symboler definieras och initieras med hjälp av `mutable`-instruktionen.
Symboler som har deklarerats och bundits som en del av en `mutable`-instruktion kan vara kopplade till ett annat värde senare i koden. 

En föränderligt bindnings instruktion består av nyckelordet `mutable`, följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda symbolerna till och ett avslutande semikolon.
Typen för den eller de kopplade symbolerna härleds baserat på uttrycket på den högra sidan. Om en symbol har bundits igen senare i koden, ändras inte dess typ, och det gräns värde som måste vara kompatibelt med den typen.

### <a name="rebinding-of-mutable-symbols"></a>OMBINDNING av föränderligt symboler

En föränderligt-variabel kan bindas om med hjälp av en `set`-instruktion.
En sådan OMBINDNING består av nyckelordet `set`, följt av en symbol-eller Symbols tupel, ett likhets tecken `=`, ett uttryck för att binda om symbolerna till och ett avslutande semikolon.
Värdet måste vara kompatibelt med typ (er) för symbolerna som den är kopplad till.

#### <a name="apply-and-reassign-statement"></a>Instruktionen tillämpa och omtilldela

En särskild typ av Set-sats som vi refererar till som en sats för att tillämpa och omtilldela är ett bekvämt sätt att sammanfoga om den högra sidan består av en binär Operators applikation och resultatet måste bindas till det vänstra argumentet till operatorn. Exempel:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
ökar värdet för räknaren `counter` i varje iteration av `for`-loopen. Koden ovan motsvarar 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Liknande instruktioner är tillgängliga för alla binära operatorer där typen för den vänstra sidan matchar uttrycks typen. Detta ger till exempel ett bekvämt sätt att ackumulera värden:
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Instruktionen Uppdatera och omtilldela

Det finns en liknande sammanfogning för kopiera-och-uppdatera-uttryck på den högra sidan. Det finns ett uttryck för uppdatering och omtilldelning för namngivna objekt i användardefinierade typer samt för mat ris objekt.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

Om det finns matriser innehåller våra standard bibliotek nödvändiga verktyg för många vanliga behov av initiering och manipulering av matris, och därför kan du undvika att behöva uppdatera mat ris objekt på den första platsen. Uppdaterings-och omtilldelnings instruktioner ger ett alternativ om det behövs:

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> Undvik onödig användning av uppdaterings-och omtilldelnings instruktioner genom att använda de verktyg som finns i <xref:microsoft.quantum.arrays>.

Funktionen
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
Du kan till exempel enkelt använda funktionen `ConstantArray` i `Microsoft.Quantum.Arrays`och returnera ett kopierings-och-uppdaterings uttryck:

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a>Bindnings omfång

I allmänhet ligger symbol bindningar utanför definitions området och blir instabil i slutet av uttrycks blocket som de inträffar i.
Det finns två undantag till den här regeln:

- Bindningen för loop-variabeln i en `for`-slinga är inom omfånget för for-slingan, men inte efter slutet av slingan.
- Alla tre delar av en `repeat`/`until` slinga (bröd texten, testet och korrigeringen) behandlas som ett enda omfång, så symboler som är kopplade till bröd texten är tillgängliga i testet och i korrigeringen.

För båda typerna av slingor körs varje steg genom slingan i sin egen omfattning, så bindningar från ett tidigare pass är inte tillgängliga i ett senare pass.

Symbol bindningar från yttre block ärvs av inre block.
En symbol får bara bindas en gång per block. Det är inte tillåtet att definiera en symbol med samma namn som en annan symbol inom omfånget (ingen "skuggning").
Följande sekvenser är juridiska:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

och

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

Men detta skulle vara ogiltigt:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

som skulle:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>Kontrollflöde

### <a name="for-loop"></a>For-slinga

Instruktionen `for` stöder iteration över ett heltals intervall eller över en matris.
Instruktionen består av nyckelordet `for`, en öppen parentes `(`följt av en symbol eller symbol tupel, nyckelordet `in`, ett uttryck av typen `Range` eller matris, en avslutande parentes `)`och ett instruktions block.

Instruktions blocket (bröd texten i slingan) körs upprepade gånger, med de definierade symbolerna (loop-variabeln) som är kopplade till varje värde i intervallet eller matrisen.
Observera att om intervall uttrycket utvärderas till ett tomt intervall eller en matris, körs inte bröd texten alls.
Uttrycket utvärderas fullständigt innan det går in i loopen och ändras inte när slingan körs.

Bindningen för de deklarerade symbolerna är oföränderlig och följer samma regler som andra variabel bindningar. I synnerhet är det möjligt att Destruct, t. ex. mat ris objekt för en iteration över en matris vid tilldelning till loop-variabeln (s).

Exempel:

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Loop-variabeln binds vid varje ingång till loop-texten och är obunden i slutet av bröd texten.
I synnerhet är loop-variabeln inte kopplad efter att for-slingan har slutförts.

### <a name="repeat-until-success-loop"></a>Upprepa-tills-lyckad-slinga

Instruktionen `repeat` stöder Quantum-mönstret "Upprepa tills lyckat".
Det består av nyckelordet `repeat`följt av ett instruktions block ( _loop_ -texten), nyckelordet `until`, ett booleskt uttryck och antingen ett avslutande semikolon eller nyckelordet `fixup` följt av ett annat instruktions block ( _korrigeringen_).
Loop-texten, villkoret och korrigeringen betraktas som alla som ett enda omfång, så symboler som är kopplade till texten är tillgängliga i villkoret och korrigeringen.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

Loop-texten körs och sedan utvärderas villkoret.
Om villkoret är sant slutförs instruktionen. annars utförs korrigeringen och instruktionen körs igen från och med loop-texten.
Observera att om du slutför körningen av korrigeringen avslutas omfånget för instruktionen, så att symbol bindningar som görs under bröd texten eller korrigeringen inte är tillgängliga i efterföljande upprepningar.

Följande kod är till exempel en Probabilistic-krets som implementerar en viktig rotations grind $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ med Hadamard-och T-grindarna.
Slingan upphör om 8/5 upprepningar i genomsnitt.
Se [*REPEAT-until-lyckades: icke-deterministisk dekomposition av Single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick och Svore, 2014) för mer information.

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> Undvik att använda repetitions-till-Slutför-slingor inuti functions. Motsvarande funktioner tillhandahålls av while-slingor i functions. 

### <a name="while-loop"></a>While-slinga

Upprepa-tills-lyckad-mönster har en mycket Quantum-speciell connotation. De används ofta i vissa klasser av Quantum-algoritmer – därför är den dedikerade språk konstruktionen i Q #. Loopar som bryts baserat på ett villkor och vars körnings längd alltså är okänd vid kompileringen måste dock hanteras med särskild försiktighet i en Quantum-körning. Deras användning i functions å andra sidan är problematisk, eftersom dessa endast innehåller kod som ska köras på konventionell (icke-Quantum) maskin vara. 

Q # stöder därför endast användningen av while-slingor i functions. En `while`-instruktion består av nyckelordet `while`, en öppen parentes `(`, ett villkor (t. ex. ett booleskt uttryck), en avslutande parentes `)`och ett instruktions block.
Instruktions blocket (bröd texten i slingan) körs så länge villkoret utvärderas till `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Villkors instruktion

Instruktionen `if` stöder villkorlig körning.
Det består av nyckelordet `if`, en öppen parentes `(`, ett booleskt uttryck, en avslutande parentes `)`och ett instruktions block ( _then_ -block).
Detta kan följas av valfri mängd Else-If-satser, som består av nyckelordet `elif`, en öppen parentes `(`, ett booleskt uttryck, en högerparentes `)`och ett instruktions block ( _Else-If-_ block).
Slutligen kan instruktionen avslutas med en Else-sats som består av nyckelordet `else` följt av ett annat instruktions block ( _Else_ -blocket).
Villkoret utvärderas och om det är sant körs blocket.
Om villkoret är falskt utvärderas det första Else-If-villkoret. om det är sant körs det Else-If-blocket.
Annars testas det andra-IF-blocket, och sedan den tredje, och så vidare tills en sats med ett True-villkor påträffas eller det inte finns några Else If-satser.
Om det ursprungliga IF-villkoret och alla Else-If-satser utvärderas till false körs Else-blocket om ett har angetts.

Observera att det körs på det egna omfånget.
Bindningar som görs inuti ett then-, Else-If-eller Else-block visas inte efter slutet av IF-instruktionen.

Exempel:

```qsharp
if (result == One) {
    X(target);
} 
```

eller

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>returrelaterade

Return-instruktionen avslutar körningen av en åtgärd eller funktion och returnerar ett värde till anroparen.
Det består av nyckelordet `return`följt av ett uttryck av lämplig typ och ett avslutande semikolon.

Ett anrop som returnerar en tom tupel, `()`, kräver ingen Return-instruktion.
Om en tidig avslutning önskas kan `return ()` användas i det här fallet.
Callables som returnerar någon annan typ kräver en slutgiltig Return-instruktion.

Det finns inget maximalt antal retur uttryck i en åtgärd.
Kompilatorn kan generera en varning om instruktioner följer en Return-instruktion i ett block.

Exempel:

```qsharp
return 1;
```

eller

```qsharp
return ();
```

eller

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Kanske

Instruktionen Error avslutar körningen av en åtgärd och returnerar ett felvärde till anroparen.
Det består av nyckelordet `fail`följt av en sträng och ett avslutande semikolon.
Strängen returneras till den klassiska driv rutinen som fel meddelande.

Det finns ingen begränsning för antalet misslyckande uttryck i en åtgärd.
Kompilatorn kan generera en varning om instruktioner följer en felaktig instruktion i ett block.

Exempel:

```qsharp
fail $"Impossible state reached";
```

eller

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Hantering av qubit

Observera att ingen av dessa instruktioner tillåts i bröd texten i en funktion.
De är endast giltiga inom åtgärder.

### <a name="clean-qubits"></a>Rengör qubits

Instruktionen `using` används för att hämta nya qubits för användning under ett instruktions block.
Qubits är garanterat att initieras till beräknings `Zero`s tillstånd.
Qubits ska vara i beräknings `Zero`s tillstånd i slutet av instruktions blocket. simulatorer uppmuntras att genomdriva detta.

Instruktionen består av nyckelordet `using`följt av en öppen parentes `(`, en bindning, en avslutande parentes `)`och instruktions blocket som qubits är tillgängligt i.
Bindningen följer samma mönster som `let`-satser: antingen en symbol eller en tupel med symboler, följt av ett likhets tecken `=`, och antingen ett enda värde eller en matchande tupel av initierare.
Initierare är tillgängliga antingen för en enskild qubit, anges som `Qubit()`eller en matris med qubits, som anges av `Qubit[`, ett `Int` uttryck och `]`.

Exempel:

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a>Smutsig qubits

`borrowing`-instruktionen används för att hämta qubits för tillfällig användning. Instruktionen består av nyckelordet `borrowing`följt av en öppen parentes `(`, en bindning, en avslutande parentes `)`och instruktions blocket som qubits är tillgängligt i.
Bindningen följer samma mönster och regler som i en `using`-instruktion.

Exempel:

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

De lånade qubits är i ett okänt tillstånd och hamnar utanför definitions området i slutet av instruktions blocket.
Låntagaren åtar sig att lämna qubits i samma tillstånd som de var i när de lånades, d.v.s. deras tillstånd i början och i slutet av instruktions blocket förväntas vara detsamma.
Detta tillstånd är i synnerhet inte nödvändigt vis ett klassiskt läge, som i de flesta fall bör låne omfång inte innehålla mätningar. 

Sådana qubits kallas ofta "smutsig Ancilla".
Se [*factoring med hjälp av 2n + 2 qubits med Toffoli-baserad modulär multiplikation*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler och Svore 2017) för ett exempel på smutsig Ancilla användning.

När du lånar qubits försöker systemet först att fylla i begäran från qubits som används men som inte har öppnats under bröd texten i `borrowing`-instruktionen.
Om det inte finns tillräckligt med sådan qubits, kommer den att allokera nya qubits för att slutföra begäran.

## <a name="conjugations"></a>Conjugations

Till skillnad från klassiska bitar är det något mer engagerande att frigöra Quantum-minne eftersom qubits kan ha oönskade effekter på den återstående beräkningen om qubits fortfarande är Entangled. Detta kan undvikas genom att du avregistrerar utförda beräkningar innan du frigör minnet. Ett vanligt mönster i Quantum Computing är därför följande: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: nytt: från och med vår 0,9-utgåva har vi stöd för en conjugation-instruktion som implementerar omvandlingen ovan. Med den här instruktionen kan åtgärds `ApplyWith` implementeras på följande sätt:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
En sådan conjugation-instruktion är självklart mycket mer användbar om den yttre och inre omvandlingen inte är tillgänglig som åtgärder, men är i stället bekvämare att beskriva genom ett block som består av flera instruktioner. 

Den inverterade omvandlingen för de instruktioner som definierats inom blocket genereras automatiskt av kompileraren och körs när Apply-blocket har slutförts. Eftersom alla föränderligt-variabler som används som en del av inom-blocket inte kan bindas om i Apply-blocket, garanteras den genererade omvandlingen som det angränsande av beräkningen i avsnittet-block. 

## <a name="expression-evaluation-statements"></a>Utvärderings satser för uttryck

Ett anrops uttryck av typen `Unit` kan användas som en instruktion.
Detta används främst för att anropa åtgärder på qubits som returnerar `Unit` eftersom syftet med instruktionen är att ändra implicit Quantum-tillstånd.
Uttrycks utvärderings uttryck kräver ett avslutande semikolon.

Exempel:

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
