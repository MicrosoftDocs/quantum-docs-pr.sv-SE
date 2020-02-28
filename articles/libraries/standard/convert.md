---
title: 'Typ konverteringar i Q # standard-bibliotek'
description: 'Lär dig mer om vanliga och användardefinierade typ konverterings funktioner i Q # standard-bibliotek.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907808"
---
# <a name="type-conversions"></a><span data-ttu-id="12875-103">Typ konverteringar</span><span class="sxs-lookup"><span data-stu-id="12875-103">Type Conversions</span></span> #

<span data-ttu-id="12875-104">Q # är ett **starkt skrivet** språk.</span><span class="sxs-lookup"><span data-stu-id="12875-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="12875-105">I synnerhet har Q # inte implicit omvandling mellan olika typer.</span><span class="sxs-lookup"><span data-stu-id="12875-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="12875-106">`1 + 2.0` är till exempel inte ett giltigt Q #-uttryck.</span><span class="sxs-lookup"><span data-stu-id="12875-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="12875-107">I stället innehåller Q # en mängd olika typ konverterings funktioner för att skapa nya värden av en specifik typ.</span><span class="sxs-lookup"><span data-stu-id="12875-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="12875-108">Till exempel har <xref:microsoft.quantum.core.length> utdatatypen `Int`, så dess utdata måste först konverteras till en `Double` innan den kan användas som en del av ett flytt ALS uttryck.</span><span class="sxs-lookup"><span data-stu-id="12875-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="12875-109">Detta kan göras med hjälp av funktionen <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="12875-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="12875-110"><xref:microsoft.quantum.convert>-namnrymden innehåller vanliga typ konverterings funktioner för att arbeta med de grundläggande inbyggda typerna, till exempel `Int`, `Double`, `BigInt`, `Result`och `Bool`:</span><span class="sxs-lookup"><span data-stu-id="12875-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="12875-111"><xref:microsoft.quantum.convert>-namnrymden innehåller också vissa fler exotiska konverteringar, till exempel `FunctionAsOperation`, som konverterar funktioner `'T -> 'U` till nya åtgärder `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="12875-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="12875-112">Slutligen tillhandahåller Q # standard-biblioteket ett antal användardefinierade typer, till exempel <xref:microsoft.quantum.math.complex> och <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="12875-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="12875-113">Tillsammans med de här typerna innehåller standard biblioteket funktioner som <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="12875-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
