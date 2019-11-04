---
title: 'Q #-metoder – gå vidare | Microsoft Docs'
description: 'Q #-tekniker – gå vidare'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183309"
---
# <a name="going-further"></a>Gå vidare #

Nu när du har sett hur du skriver intressanta Quantum-program i Q # går det här avsnittet vidare genom att introducera några fler avancerade ämnen som bör vara användbara i framtiden.

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a>Allmänna åtgärder och funktioner ##

> [!TIP]
> Det här avsnittet förutsätter grundläggande kunskaper om [generiska i C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generiska i F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ mallar](https://docs.microsoft.com/cpp/cpp/templates-cpp)eller liknande metoder för metaprogramming på andra språk.

Många funktioner och åtgärder som vi kanske vill definiera stämmer inte överens med typerna av deras indata, utan att bara implicit använda sina typer via en annan funktion eller åtgärd.
Anta till exempel att *mappnings* konceptet är gemensamt för många funktionella språk; med en Function $f (x) $ och en samling värden $\{x_1, x_2, \dots, x_n\}$, returnerar kartan en ny samling $\{f (x_1), f (x_2), \dots, f (x_n)\}$.
För att implementera detta i Q # kan vi dra nytta av att funktionerna är första klass.
Nu ska vi skriva ut ett snabbt exempel på `Map`, med ★ som plats hållare medan vi tar reda på vilka typer vi behöver.

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

OBS! den här funktionen ser mycket likadan ut oavsett vilka faktiska typer som vi ersätter i.
En karta från heltal till Paulis, till exempel, ser ut ungefär likadant som en karta från flytt ALS nummer till strängar:

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Vi kan i princip skriva en version av `Map` för varje par av typer som vi stöter på, men detta ger ett antal svårigheter.
Om vi till exempel upptäcker ett fel i `Map`måste vi se till att korrigeringen tillämpas enhetligt i alla versioner av `Map`.
Om vi konstruerar en ny tupel eller UDT, måste du dessutom också skapa en ny `Map` för att gå vidare med den nya typen.
Även om det här är ett litet antal sådana funktioner, och vi samlar in fler och fler funktioner i samma formulär som `Map`, blir kostnaden för att introducera nya typer orimligt stor i relativt kort ordning.

Mycket av detta problem, men från att vi inte har gett kompilatorn den information som krävs för att identifiera hur de olika versionerna av `Map` är relaterade.
Vi vill att kompilatorn ska behandla `Map` som en typ av matematisk funktion från Q # *typer* till q # functions.
Den här begreppet är formell genom att tillåta att funktioner och åtgärder har *typ parametrar*, samt deras vanliga tuple-parametrar.
I exemplen ovan vill vi tänka på `Map` som har typ parametrar `Int, Pauli` i det första fallet och `Double, String` i det andra fallet.
För det mesta kan dessa typ parametrar sedan användas som om de var vanliga: vi använder värden av typen parametrar för att skapa matriser och tupler, anropa funktioner och åtgärder och tilldela till vanliga variabler eller föränderligt.

> [!NOTE]
> Det mest extrema fallet med indirekt beroende är att av qubits, där ett Q #-program inte kan förlita sig på strukturen för `Qubit` typen, men **måste** skicka sådana typer till andra funktioner och funktioner.

I exemplet ovan kan vi se att vi behöver `Map` att ha typ parametrar, ett för att representera indata till `fn` och ett för att representera utdata från `fn`.
I Q # skrivs detta genom att lägga till vinkelparenteser (det vill säga `<>`, inte bromsar $ \braket{}$!) efter namnet på en funktion eller åtgärd i dess deklaration, och genom att ange varje typ parameter.
Namnet på varje typ parameter måste börja med en Ticket `'`, vilket indikerar att det är en typ parameter och inte en vanlig typ (kallas även *konkret* typ).
För `Map`skriver vi därför:

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Observera att definitionen av `Map<'Input, 'Output>` ser mycket likt de versioner vi skrev ut tidigare.
Den enda skillnaden är att vi uttryckligen har informerat kompilatorn att `Map` inte direkt är beroende av vad `'Input` och `'Output` är, men fungerar för två typer genom att använda dem indirekt via `fn`.
När vi har definierat `Map<'Input, 'Output>` på det här sättet kan vi anropa det som om det var en vanlig funktion:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Att skriva allmänna funktioner och åtgärder är en plats där "tupel-in-tupel" är ett mycket användbart sätt att tänka på när det gäller Q #-funktioner och-åtgärder.
> Eftersom varje funktion tar exakt en indata och returnerar exakt en utdata, matchar indata typen `'T -> 'U` *alla* Q #-funktioner.
> På samma sätt kan alla åtgärder skickas till inmatade typer `'T => 'U`.

Som ett andra exempel bör du tänka på utmaningen med att skriva en funktion som returnerar kompositionen av två andra funktioner:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Här måste vi ange exakt vad `A`, `B`och `C` är, vilket begränsar verktyget för vår nya `Compose`-funktion.
Efter allt är `Compose` bara beroende av `A`, `B`och `C` *via* `innerFn` och `outerFn`.
Alternativt kan vi lägga till typ parametrar till `Compose` som anger att det fungerar för *alla* `A`, `B`och `C`, så länge parametrarna matchar de som förväntas av `innerFn` och `outerFn`:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Standard biblioteken för Q # innehåller en mängd olika typer av typ parametrar och funktioner som gör det lättare att uttrycka ett kontroll flöde med högre ordning.
Dessa beskrivs ytterligare i guiden för [Q # standard library](xref:microsoft.quantum.libraries.standard.intro).

## <a name="borrowing-qubits"></a>Låna qubits ##

Upplånings metoden gör det möjligt att allokera qubits som kan användas som Scratch-utrymme under en beräkning. Dessa qubits är vanligt vis inte i rent tillstånd, dvs. de är inte nödvändigt vis initierade i ett känt tillstånd som $ \ket{0}$. En pratar också om "smutsig" qubits när deras tillstånd är okänt och kan till och med vara Entangled med andra delar av Quantum-datorns minne. Bland de kända användnings fallen av smutsig qubits är implementeringar av multi-styrda CNOT-portar som bara kräver mycket få qubits och implementering av steg.

I filen Canon finns exempel som använder nyckelordet `borrowing`, till exempel funktionen `MultiControlledXBorrow` som definieras nedan.
Om `controls` anger de kontroll-qubits som ska läggas till i en `X`-åtgärd, läggs en övergripande av `Length(controls)-2` många smutsig ancillas till av den här implementeringen.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Observera att den omfattande användningen av `With` Combinator----i formulär som är tillämplig för åtgärder som stöder intilliggande, d.v.s. `WithA`---har gjorts i det här exemplet, vilket är ett lämpligt programmerings format som att lägga till kontrollen till strukturer som bara omfattar `With` sprider kontroll till den inre åtgärden. Ytterligare information om detta utöver `body` av åtgärden är att en implementering av åtgärdens `controlled`s huvuddel uttryckligen tillhandahölls, i stället för att en `controlled auto`-instruktion används. Orsaken till detta är att vi vet från strukturen på kretsen som gör det enkelt att lägga till ytterligare kontroller som är fördelaktiga jämfört med att lägga till kontrollen till varje enskild grind i `body`. 

Det är ett sätt att jämföra den här koden med en annan Canon Function-`MultiControlledXClean` som uppnår samma mål för att implementera en multiplicering-kontrollerad `X`-åtgärd, men som använder flera rena qubits med `using` mekanismen. 
