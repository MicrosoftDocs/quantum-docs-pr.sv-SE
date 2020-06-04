---
title: 'Q # fil struktur'
description: 'Beskriver strukturen och syntaxen för en Q #-fil.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327466"
---
# <a name="q-file-structure"></a>Q # fil struktur

Varje Q #-åtgärd, funktion och användardefinierad typ definieras i ett namn område.

En Q #-fil består av en sekvens med *namn områdes deklarationer*.
Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner.
En namn områdes deklaration får innehålla valfritt antal av varje typ av deklaration, och i vilken ordning som helst.
Följ dessa länkar om du vill ha mer information om att deklarera [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types), [åtgärder](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)och [funktioner](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) inom ett namn område.

Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.
I synnerhet dokumentations kommentarer (mer information nedan) för ett namn område före deklarationen.

## <a name="namespace-declarations"></a>Namn områdes deklarationer

En Q #-fil har vanligt vis exakt en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.
Namespace-deklarationer får inte vara kapslade.

Samma namnrymd kan deklareras i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.
I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.

En namn områdes deklaration består av nyckelordet `namespace` följt av namnet på namn området, en öppen klammerparentes `{` , de deklarationer som finns i namn området och en avslutande klammerparentes `}` .
Namn rymds namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.` .
Till exempel, `MyQuantumStuff` och `Microsoft.Quantum.Intrinsic` är giltiga namn områdes namn.
Enligt konvention är symbolerna i namn områdes namnet versaler, men det är inget krav.

Referenser till typer eller callables som deklarerats senare i en fil löses korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.

## <a name="open-directives"></a>Öppna direktiv

I ett namn områdes block `open` kan direktivet användas för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.
Ett sådant `open` direktiv består av `open` nyckelordet följt av namn området som ska öppnas och ett avslutande semikolon.

> [!NOTE] 
> Alla `open` direktiv måste finnas före eventuella `function` -, `operation` -eller- `newtype` deklarationer i blocket namespace.

Alternativt kan ett kort namn för det öppna namn området definieras så att alla element från det namn området kan (och behöver) kvalificeras av det definierade korta namnet. Till exempel, med följande namn rymds deklaration och öppna direktiv,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

om en åtgärd som vi deklarerar använder en åtgärd `Op` från `Microsoft.Quantum.Intrinsic` , skulle vi kalla den genom att bara använda `Op` .
Men om vi ville ha ett anrop till en viss funktion `Fn` från `Microsoft.Quantum.Math` skulle vi behöva anropa det med `Math.Fn` .

`open`Direktivet gäller hela namn områdes blocket i en fil.
Om vi till exempel skulle definiera ytterligare ett namn område i samma Q #-fil som `NS` ovan, skulle alla åtgärder/funktioner/typer som definierats i den andra namn rymden inte ha åtkomst till något från `Microsoft.Quantum.Intrinsic` eller `Microsoft.Quantum.Math` om vi upprepade de öppna direktiven i fråga. 

En typ eller en anropad typ som har definierats i en annan namnrymd som *inte* är öppen i det aktuella namn området måste refereras till av sitt fullständigt kvalificerade namn.
Till exempel måste en åtgärd `Op` som heter från `X.Y` namn området refereras till av sitt fullständigt kvalificerade namn `X.Y.Op` , om inte `X.Y` namn området har öppnats tidigare i det aktuella blocket. Som nämnts ovan, även om `X` namn området har öppnats, är det inte möjligt att referera till åtgärden som `Y.Op` .
Om ett kort namn `Z` för `X.Y` har definierats i namn området och filen, `Op` måste det kallas `Z.Op` . 

Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open` direktiv.
Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.

Q # följer samma regler för namngivning som andra .NET-språk.
Q # stöder dock inte relativa referenser till namn områden.
Det vill säga, om namn området `a.b` har öppnats, matchas inte en referens till en åtgärd `c.d` med namnet i en åtgärd med fullständigt namn *not* `a.b.c.d` .

## <a name="formatting"></a>Formatering

De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;` .
Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block (se nedan) kräver inte ett avslutande semikolon.
Varje instruktions Beskrivning noterar om avslutande semikolon krävs.

Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.
Att ha flera instruktioner på en enda rad bör undvikas.

## <a name="statement-blocks"></a>Instruktions block

Q #-instruktioner grupperas i uttrycks block.
Ett instruktions block börjar med en inledande `{` och slutar med en stängning `}` .

Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.

## <a name="comments"></a>Kommentarer

Kommentarer börjar med två snedstreck, `//` och fortsätter till slutet av raden.
En kommentar kan visas var som helst i en Q #-källfil.

## <a name="documentation-comments"></a>Dokumentations kommentarer

Kommentarer som börjar med tre snedstreck, `///` behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.
I så fall tas deras innehåll som dokumentation för den definierade typen av anropad eller användardefinierad typ, som för andra .NET-språk.

I `///` kommentarer är text som ska visas som en del av API-dokumentationen formaterad som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.
Som tillägg till markdown kan kors referenser till åtgärder, funktioner och användardefinierade typer i Q # inkluderas med `@"<ref target>"` , där `<ref target>` ersätts av det fullständigt kvalificerade namnet på det kod objekt som refereras till.
Alternativt kan en dokumentations motor också ha stöd för ytterligare markdown-tillägg.

Ett exempel:

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
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

## <a name="next-steps"></a>Nästa steg

Lär dig mer om [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions) i Q #.