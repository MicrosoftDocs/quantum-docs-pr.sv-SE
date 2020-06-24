---
title: 'Typ konverteringar i Q # standard-bibliotek'
description: 'Lär dig mer om vanliga och användardefinierade typ konverterings funktioner i Q # standard-bibliotek.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275742"
---
# <a name="type-conversions"></a>Typ konverteringar #

Q # är ett **starkt skrivet** språk.
I synnerhet har Q # inte implicit omvandling mellan olika typer. Är till exempel `1 + 2.0` inte ett giltigt Q #-uttryck.
I stället innehåller Q # en mängd olika typ konverterings funktioner för att skapa nya värden av en specifik typ.

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

Slutligen tillhandahåller Q # standard-biblioteket ett antal användardefinierade typer, till exempel <xref:microsoft.quantum.math.complex> och <xref:microsoft.quantum.arithmetic.littleendian> .
Tillsammans med de här typerna innehåller standard biblioteket funktioner som <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
