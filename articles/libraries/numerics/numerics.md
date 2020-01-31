---
title: Använda det numeriska biblioteket | Microsoft Docs
description: Använda det numeriska biblioteket
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821039"
---
# <a name="using-the-numerics-library"></a>Använda det numeriska biblioteket

## <a name="overview"></a>Översikt

Det numeriska biblioteket består av tre komponenter

1. **Basic Integer-beräkning** med heltal Adders och Comparators
1. **Hög nivå av heltals funktioner** som bygger på de grundläggande funktionerna. den omfattar multiplikation, Division, inversion osv.  för signerade och osignerade heltal.
1. **Aritmetiska funktioner** med fast punkt med fast punkt-initiering, tillägg, multiplikation, ömsesidig, polynom utvärdering och mätning.

Alla dessa komponenter kan nås med hjälp av en enda `open`-instruktion:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Typer

Det numeriska biblioteket stöder följande typer

1. **`LittleEndian`** : en qubit mat ris `qArr : Qubit[]` som representerar ett heltal där `qArr[0]` anger den minst signifikanta biten.
1. **`SignedLittleEndian`** : samma som `LittleEndian`, förutom att det representerar ett signerat heltal som lagras i två komplement.
1. **`FixedPoint`** : representerar ett reellt tal som består av en qubit mat ris `qArr2 : Qubit[]` och en binär punkt positions `pos`, som räknar antalet binära siffror till vänster om den binära punkten. `qArr2` lagras på samma sätt som `SignedLittleEndian`.

## <a name="operations"></a>Operations

Det finns flera olika åtgärder för var och en av de tre typerna ovan:

1. **`LittleEndian`**
    - Lägger
    - Jämförelse
    - Multiplikation
    - Squaring
    - Division (med rest)

1. **`SignedLittleEndian`**
    - Lägger
    - Jämförelse
    - Inversion av modulo 2-komplement
    - Multiplikation
    - Squaring

1. **`FixedPoint`**
    - Förberedelse/initiering till ett klassiskt värde
    - Addition (klassisk konstant eller annan Quantum Fixed-Point)
    - Jämförelse
    - Multiplikation
    - Squaring
    - Polynom utvärdering med specialisering för jämna och udda funktioner
    - Motsvarighet (1/x)
    - Mått (klassisk dubbel)

Mer information och detaljerad dokumentation för var och en av dessa åtgärder finns i referens dokument för Q #-bibliotek på [docs.Microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Exempel: heltals tillägg

Som ett grundläggande exempel bör du ta hänsyn till åtgärden $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ det vill säga en åtgärd som tar ett n-qubit heltal $x $ och en n-eller (n + 1)-qubit registrera sig $y $ som indatamängdar, varav den senare mappas till sum $ (x + y) $. Observera att summan är beräknad med modulo $2 ^ n $ om $y $ lagras i ett $n $-bitars register.

Med hjälp av Quantum Development Kit kan du använda den här åtgärden på följande sätt:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Exempel: utvärdering av utjämna funktioner

Om du vill utvärdera mjuka funktioner som $ \sin (x) $ på en Quantum-dator, där $x $ är ett Quantum `FixedPoint`-nummer, innehåller biblioteken med Quantum Development Kit-paket åtgärder `EvaluatePolynomialFxP` och `Evaluate[Even/Odd]PolynomialFxP`.

Det första, `EvaluatePolynomialFxP`, gör det möjligt att utvärdera en polynom av formatet $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ där $d $ anger *graden*. För att göra det är allt det som behövs de polynoma koefficienterna `[a_0,..., a_d]` (av typ `Double[]`), indata-`x : FixedPoint` och utdata `y : FixedPoint` (ursprungligen noll):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Resultatet, $P (x) = 1 + 2x $, kommer att lagras i `yFxP`.

Den andra, `EvaluateEvenPolynomialFxP`och den tredje `EvaluateOddPolynomialFxP`är specialiseringar för fall av jämna respektive udda funktioner. Det vill säga för en jämn/udda funktion $f (x) $ och $ $ P_ {jämna} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ approximeras bra genom att $P _ {t.o.m.} (x) $ eller $P _ {udda} (x): = x\cdot P_ {jämna} (x) $.
I Q # kan dessa två fall hanteras på följande sätt:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
som utvärderar $P _ {t.o.m.} (x) = 1 + 2x ^ 2 $ och
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
som utvärderar $P _ {udda} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Fler exempel

Du hittar fler exempel i [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum).

Kom igång genom att klona lagrings platsen och öppna undermappen `Numerics`:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

`cd` till en av exempel mapparna och kör exemplet via

```bash
dotnet run
```
