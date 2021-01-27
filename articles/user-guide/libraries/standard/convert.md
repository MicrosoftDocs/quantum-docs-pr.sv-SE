---
title: Typ konverteringar i Q# standard biblioteken
description: Lär dig mer om vanliga och användardefinierade typ konverterings funktioner i Q# standard biblioteken.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858027"
---
# <a name="type-conversions"></a>Typ konverteringar #

Q# är ett **starkt inskrivet** språk.
I synnerhet är det Q# inte implicit att konvertera mellan olika typer. Till exempel `1 + 2.0` är inte ett giltigt Q# uttryck.
I stället Q# tillhandahåller en mängd olika typ konverterings funktioner för att skapa nya värden av en specifik typ.

Till exempel har utdatatypen <xref:Microsoft.Quantum.Core.Length> `Int` , så dess utdata måste först konverteras till en `Double` innan den kan användas som en del av ett flytt ALS uttryck.
Detta kan göras med hjälp av <xref:Microsoft.Quantum.Convert.IntAsDouble> funktionen:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:Microsoft.Quantum.Convert>Namn området innehåller vanliga typ konverterings funktioner för att arbeta med de grundläggande inbyggda typerna, till exempel,,, `Int` `Double` `BigInt` `Result` och `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:Microsoft.Quantum.Convert>Namn området innehåller också vissa fler exotiska konverteringar, till exempel `FunctionAsOperation` , som konverterar funktioner `'T -> 'U` till nya åtgärder `'T => 'U` .

Slutligen Q# tillhandahåller standard biblioteket ett antal användardefinierade typer, till exempel <xref:Microsoft.Quantum.Math.Complex> och <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Tillsammans med de här typerna innehåller standard biblioteket funktioner som <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
