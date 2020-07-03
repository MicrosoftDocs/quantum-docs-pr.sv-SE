---
title: 'Q # fil struktur'
description: 'Beskriver strukturen och syntaxen för en Q #-fil.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884175"
---
# <a name="q-file-structure"></a>Q # fil struktur

En Q #-fil består av en sekvens med *namn områdes deklarationer*.
Varje namn områdes deklaration innehåller deklarationer för användardefinierade typer, åtgärder och funktioner och kan innehålla valfritt antal varje typ av deklaration och i vilken ordning som helst.
Mer information om deklarationer i ett namn område finns i [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types), [åtgärder](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)och [funktioner](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

Den enda text som kan visas utanför en namn områdes deklaration är kommentarer.
I synnerhet är dokumentations kommentarer för ett namn område före deklarationen. Mer information finns i [dokumentations kommentarer](#documentation-comments) i den här artikeln. 

## <a name="namespace-declarations"></a>Namn områdes deklarationer

En Q #-fil har vanligt vis bara en namn områdes deklaration, men kan ha ingen (och vara tom eller bara innehålla kommentarer) eller innehålla flera namn områden.
Namespace-deklarationer kan inte kapslas.

Du kan deklarera samma namnrymd i flera Q #-filer som kompileras tillsammans, så länge det inte finns någon typ, åtgärd eller funktions deklaration med samma namn.
I synnerhet är det inte tillåtet att definiera samma typ i samma namnrymd i flera filer, även om deklarationerna är identiska.

En namn områdes deklaration består av nyckelordet `namespace` , följt av namnet på namn området och de deklarationer som finns i namn området som omges av klammerparenteser `{ }` .
Namn rymds namn följer .NET-mönstret för en sekvens med en eller flera juridiska symboler avgränsade med punkter `.` .
Till exempel `MyQuantumStuff` och `Microsoft.Quantum.Intrinsic` är giltiga namn områdes namn.
I konvention är det dock inte obligatoriskt att använda versaler i namn områdes namn.

Referenser till typer eller callables som deklarerats närmare i en fil matchas korrekt. Det finns inget behov av typen, åtgärden eller funktions deklarationen att föregå en referens till den.

## <a name="open-directives"></a>Öppna direktiv

I ett namn områdes block använder du `open` direktivet för att importera alla typer och callables som har deklarerats i ett visst namn område och referera till dem med hjälp av okvalificerade namn.
Ett sådant `open` direktiv består av `open` nyckelordet följt av namn området som ska öppnas och ett avslutande semikolon.

> [!NOTE] 
> Alla `open` direktiv måste finnas före eventuella `function` -, `operation` -eller- `newtype` deklarationer i blocket namespace.

Alternativt kan du definiera ett kort namn för det öppnade namn området. Om ett kort namn har definierats måste du kvalificera alla element från det namn området med det definierade korta namnet. Till exempel, med följande namn rymds deklaration och öppna direktiv,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

om en deklarerad åtgärd använder en åtgärd `Op` från `Microsoft.Quantum.Intrinsic` , anropar du den genom att bara använda `Op` .
För att anropa en viss funktion `Fn` från `Microsoft.Quantum.Math` måste du dock anropa den med hjälp av `Math.Fn` .

`open`Direktivet gäller hela namn områdes blocket i en fil.
Om du definierar ytterligare ett namn område i samma Q #-fil som `NS` tidigare, skulle alla åtgärder/funktioner/typer som definierats i den andra namn rymden inte ha åtkomst till något från `Microsoft.Quantum.Intrinsic` eller `Microsoft.Quantum.Math` om du inte upprepade de öppna direktiven där. 

Om du vill referera till en typ eller en anropad typ som är definierad i en annan namnrymd som *inte* är öppen i det aktuella namn området, måste du referera till den efter dess fullständiga namn.
Till exempel, med en åtgärd `Op` som heter från `X.Y` namn området:

* Du måste referera till det med fullständigt kvalificerat namn `X.Y.Op` , om inte `X.Y` namn området har öppnats tidigare i det aktuella blocket. 
* Även om `X` namn området öppnas är det inte möjligt att referera till åtgärden som `Y.Op` .
* Om du har definierat det korta namnet `Z` för `X.Y` i namn området och filen måste du referera till `Op` som `Z.Op` . 

Det är vanligt vis bättre att inkludera ett namn område med hjälp av ett `open` direktiv.
Att använda ett fullständigt kvalificerat namn krävs om två namn rymder definierar konstruktioner med samma namn och den aktuella källan använder konstruktioner från båda.

Q # följer samma regler för namngivning som andra .NET-språk.
Q # stöder dock inte relativa referenser till namn områden.
Om namn området till exempel `a.b` är öppet matchas inte en referens till en åtgärd `c.d` med *not* namnet med fullständigt namn `a.b.c.d` .

## <a name="formatting"></a>Formatering

De flesta Q #-instruktioner och direktiv slutar med ett avslutande semikolon `;` .
Instruktioner och deklarationer som `for` och `operation` som slutar med ett instruktions block (se följande avsnitt) kräver inte ett avslutande semikolon.
Varje instruktions Beskrivning noterar om avslutande semikolon krävs.

Instruktioner, som uttryck, deklarationer och direktiv, kan delas upp över flera rader.
Undvik att placera flera instruktioner på en enda rad.

## <a name="statement-blocks"></a>Instruktions block

Q #-instruktioner grupperas i instruktions block, vilka ingår i klammerparenteser `{ }` . Ett instruktions block börjar med en inledande `{` och slutar med en stängning `}` .

Ett instruktions block som är lexikalt omslutet i ett annat block anses vara ett under block av det innehåll ande blocket. innehåller och underordnade block kallas även för yttre och inre block.

## <a name="comments"></a>Kommentarer

Kommentarer börjar med två snedstreck, `//` och fortsätter till slutet av raden.
En kommentar kan finnas var som helst i en Q #-källfil.

## <a name="documentation-comments"></a>Dokumentations kommentarer

Kommentarer som börjar med tre snedstreck, `///` behandlas särskilt av kompilatorn när de visas omedelbart före en namnrymd, åtgärd, specialisering, funktion eller typ definition.
I så fall behandlar kompileraren dem som dokumentation för den definierade typen av anropad eller användardefinierad typ, samma som andra .NET-språk.

I `///` kommentarer är text som ska visas som en del av API-dokumentationen formaterad som [markdown](https://daringfireball.net/projects/markdown/syntax), med olika delar av dokumentationen som anges av särskilt namngivna huvuden.
I markdown använder du `@"<ref target>"` tillägget för kors referens åtgärder, funktioner och användardefinierade typer i Q #. Ersätt `<ref target>` med det fullständigt kvalificerade namnet på det refererade kodvärdet.
Olika dokumentations motorer kan också ha stöd för ytterligare markdown-tillägg.

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

Följande namn är giltiga som dokumentation kommentars rubriker.

- **Sammanfattning**: en kort sammanfattning av beteendet för en funktion eller åtgärd eller syftet med en typ. Det första stycket i sammanfattningen används för hov rings information. Det bör vara oformaterad text.
- **Beskrivning**: en beskrivning av beteendet för en funktion eller åtgärd, eller syftet med en typ. Tillsammans utgör sammanfattningen och beskrivningen den genererade dokumentations filen för funktionen, åtgärden eller typen.
  Beskrivningen stöder LaTeX symboler och ekvationer som är formaterade i rad.
- **Inmatade**: en beskrivning av indataströmmen för en funktion eller funktion.
  Kan innehålla ytterligare markdown-underavsnitt som anger varje element i indataströmmen.
- **Utdata**: en beskrivning av tuppeln som returneras av en åtgärd eller funktion.
- **Typ parametrar**: ett tomt avsnitt som innehåller ett ytterligare underavsnitt för varje generisk typ parameter.
- **Exempel**: ett kort exempel på en åtgärd, funktion eller typ som används.
- **Anmärkningar**: Diverse Prose som beskriver viss aspekt av åtgärden, funktionen eller typen.
- **Se även**: en lista över fullständigt kvalificerade namn som visar relaterade funktioner, åtgärder eller användardefinierade typer.
- **Referenser**: en lista över referenser och citat för det dokumenterade objektet.

## <a name="next-steps"></a>Nästa steg

Lär dig mer om [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions) i Q #.