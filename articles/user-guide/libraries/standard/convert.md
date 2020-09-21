---
title: Typ konverteringar i Q# standard biblioteken
description: Lär dig mer om vanliga och användardefinierade typ konverterings funktioner i Q# standard biblioteken.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835612"
---
# <a name="type-conversions"></a>Typ konverteringar #

Q# är ett **starkt inskrivet** språk.
I synnerhet är det Q# inte implicit att konvertera mellan olika typer. Till exempel `1 + 2.0` är inte ett giltigt Q# uttryck.
I stället Q# tillhandahåller en mängd olika typ konverterings funktioner för att skapa nya värden av en specifik typ.

Till exempel har utdatatypen <xref:microsoft.quantum.core.length> `Int` , så dess utdata måste först konverteras till en `Double` innan den kan användas som en del av ett flytt ALS uttryck.
Detta kan göras med hjälp av <xref:microsoft.quantum.convert.intasdouble> funktionen:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>Namn området innehåller vanliga typ konverterings funktioner för att arbeta med de grundläggande inbyggda typerna, till exempel,,, `Int` `Double` `BigInt` `Result` och `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>Namn området innehåller också vissa fler exotiska konverteringar, till exempel `FunctionAsOperation` , som konverterar funktioner `'T -> 'U` till nya åtgärder `'T => 'U` .

Slutligen Q# tillhandahåller standard biblioteket ett antal användardefinierade typer, till exempel <xref:microsoft.quantum.math.complex> och <xref:microsoft.quantum.arithmetic.littleendian> .
Tillsammans med de här typerna innehåller standard biblioteket funktioner som <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
