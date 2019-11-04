---
title: 'Q # standard bibliotek – typ konverteringar | Microsoft Docs'
description: 'Q # standard bibliotek – typ konverteringar'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184482"
---
# <a name="type-conversions"></a>Typ konverteringar #

Q # är ett **starkt skrivet** språk.
I synnerhet har Q # inte implicit omvandling mellan olika typer. `1 + 2.0` är till exempel inte ett giltigt Q #-uttryck.
I stället innehåller Q # en mängd olika typ konverterings funktioner för att skapa nya värden av en specifik typ.

Till exempel har <xref:microsoft.quantum.core.length> utdatatypen `Int`, så dess utdata måste först konverteras till en `Double` innan den kan användas som en del av ett flytt ALS uttryck.
Detta kan göras med hjälp av funktionen <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>-namnrymden innehåller vanliga typ konverterings funktioner för att arbeta med de grundläggande inbyggda typerna, till exempel `Int`, `Double`, `BigInt`, `Result`och `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>-namnrymden innehåller också vissa fler exotiska konverteringar, till exempel `FunctionAsOperation`, som konverterar funktioner `'T -> 'U` till nya åtgärder `'T => 'U`.

Slutligen tillhandahåller Q # standard-biblioteket ett antal användardefinierade typer, till exempel <xref:microsoft.quantum.math.complex> och <xref:microsoft.quantum.arithmetic.littleendian>.
Tillsammans med de här typerna innehåller standard biblioteket funktioner som <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
