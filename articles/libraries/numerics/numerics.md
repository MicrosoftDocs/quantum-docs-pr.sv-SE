---
title: Använda det numeriska biblioteket | Microsoft Docs
description: Använda det numeriska biblioteket
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184618"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="27e93-103">Använda det numeriska biblioteket</span><span class="sxs-lookup"><span data-stu-id="27e93-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="27e93-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="27e93-104">Overview</span></span>

<span data-ttu-id="27e93-105">Det numeriska biblioteket består av tre komponenter</span><span class="sxs-lookup"><span data-stu-id="27e93-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="27e93-106">**Basic Integer-beräkning** med heltal Adders och Comparators</span><span class="sxs-lookup"><span data-stu-id="27e93-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="27e93-107">**Hög nivå av heltals funktioner** som bygger på de grundläggande funktionerna. den omfattar multiplikation, Division, inversion osv.  för signerade och osignerade heltal.</span><span class="sxs-lookup"><span data-stu-id="27e93-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="27e93-108">**Aritmetiska funktioner** med fast punkt med fast punkt-initiering, tillägg, multiplikation, ömsesidig, polynom utvärdering och mätning.</span><span class="sxs-lookup"><span data-stu-id="27e93-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="27e93-109">Alla dessa komponenter kan nås med hjälp av en enda `open`-instruktion:</span><span class="sxs-lookup"><span data-stu-id="27e93-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="27e93-110">Nodtyper</span><span class="sxs-lookup"><span data-stu-id="27e93-110">Types</span></span>

<span data-ttu-id="27e93-111">Det numeriska biblioteket stöder följande typer</span><span class="sxs-lookup"><span data-stu-id="27e93-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="27e93-112">**`LittleEndian`** : en qubit mat ris `qArr : Qubit[]` som representerar ett heltal där `qArr[0]` anger den minst signifikanta biten.</span><span class="sxs-lookup"><span data-stu-id="27e93-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="27e93-113">**`SignedLittleEndian`** : samma som `LittleEndian`, förutom att det representerar ett signerat heltal som lagras i två komplement.</span><span class="sxs-lookup"><span data-stu-id="27e93-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="27e93-114">**`FixedPoint`** : representerar ett reellt tal som består av en qubit mat ris `qArr2 : Qubit[]` och en binär punkt positions `pos`, som räknar antalet binära siffror till vänster om den binära punkten.</span><span class="sxs-lookup"><span data-stu-id="27e93-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="27e93-115">`qArr2` lagras på samma sätt som `SignedLittleEndian`.</span><span class="sxs-lookup"><span data-stu-id="27e93-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="27e93-116">Operations</span><span class="sxs-lookup"><span data-stu-id="27e93-116">Operations</span></span>

<span data-ttu-id="27e93-117">Det finns flera olika åtgärder för var och en av de tre typerna ovan:</span><span class="sxs-lookup"><span data-stu-id="27e93-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="27e93-118">Lägger</span><span class="sxs-lookup"><span data-stu-id="27e93-118">Addition</span></span>
    - <span data-ttu-id="27e93-119">Jämförelse</span><span class="sxs-lookup"><span data-stu-id="27e93-119">Comparison</span></span>
    - <span data-ttu-id="27e93-120">Multiplikation</span><span class="sxs-lookup"><span data-stu-id="27e93-120">Multiplication</span></span>
    - <span data-ttu-id="27e93-121">Squaring</span><span class="sxs-lookup"><span data-stu-id="27e93-121">Squaring</span></span>
    - <span data-ttu-id="27e93-122">Division (med rest)</span><span class="sxs-lookup"><span data-stu-id="27e93-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="27e93-123">Lägger</span><span class="sxs-lookup"><span data-stu-id="27e93-123">Addition</span></span>
    - <span data-ttu-id="27e93-124">Jämförelse</span><span class="sxs-lookup"><span data-stu-id="27e93-124">Comparison</span></span>
    - <span data-ttu-id="27e93-125">Inversion av modulo 2-komplement</span><span class="sxs-lookup"><span data-stu-id="27e93-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="27e93-126">Multiplikation</span><span class="sxs-lookup"><span data-stu-id="27e93-126">Multiplication</span></span>
    - <span data-ttu-id="27e93-127">Squaring</span><span class="sxs-lookup"><span data-stu-id="27e93-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="27e93-128">Förberedelse/initiering till ett klassiskt värde</span><span class="sxs-lookup"><span data-stu-id="27e93-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="27e93-129">Addition (klassisk konstant eller annan Quantum Fixed-Point)</span><span class="sxs-lookup"><span data-stu-id="27e93-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="27e93-130">Jämförelse</span><span class="sxs-lookup"><span data-stu-id="27e93-130">Comparison</span></span>
    - <span data-ttu-id="27e93-131">Multiplikation</span><span class="sxs-lookup"><span data-stu-id="27e93-131">Multiplication</span></span>
    - <span data-ttu-id="27e93-132">Squaring</span><span class="sxs-lookup"><span data-stu-id="27e93-132">Squaring</span></span>
    - <span data-ttu-id="27e93-133">Polynom utvärdering med specialisering för jämna och udda funktioner</span><span class="sxs-lookup"><span data-stu-id="27e93-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="27e93-134">Motsvarighet (1/x)</span><span class="sxs-lookup"><span data-stu-id="27e93-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="27e93-135">Mått (klassisk dubbel)</span><span class="sxs-lookup"><span data-stu-id="27e93-135">Measurement (classical Double)</span></span>

<span data-ttu-id="27e93-136">Mer information och detaljerad dokumentation för var och en av dessa åtgärder finns i referens dokument för Q #-bibliotek på [docs.Microsoft.com](https://docs.microsoft.com/en-us/quantum)</span><span class="sxs-lookup"><span data-stu-id="27e93-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/en-us/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="27e93-137">Exempel: heltals tillägg</span><span class="sxs-lookup"><span data-stu-id="27e93-137">Sample: Integer addition</span></span>

<span data-ttu-id="27e93-138">Som ett grundläggande exempel bör du ta hänsyn till åtgärden $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ det vill säga en åtgärd som tar ett n-qubit heltal $x $ och en n-eller (n + 1)-qubit registrera sig $y $ som indatamängdar, varav den senare mappas till sum $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="27e93-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="27e93-139">Observera att summan är beräknad med modulo $2 ^ n $ om $y $ lagras i ett $n $-bitars register.</span><span class="sxs-lookup"><span data-stu-id="27e93-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="27e93-140">Med hjälp av Quantum Development Kit kan du använda den här åtgärden på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="27e93-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="27e93-141">Exempel: utvärdering av utjämna funktioner</span><span class="sxs-lookup"><span data-stu-id="27e93-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="27e93-142">Om du vill utvärdera mjuka funktioner som $ \sin (x) $ på en Quantum-dator, där $x $ är ett Quantum `FixedPoint`-nummer, innehåller biblioteken med Quantum Development Kit-paket åtgärder `EvaluatePolynomialFxP` och `Evaluate[Even/Odd]PolynomialFxP`.</span><span class="sxs-lookup"><span data-stu-id="27e93-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="27e93-143">Det första, `EvaluatePolynomialFxP`, gör det möjligt att utvärdera en polynom av formatet $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ där $d $ anger *grader*.</span><span class="sxs-lookup"><span data-stu-id="27e93-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="27e93-144">För att göra det är allt det som behövs de polynoma koefficienterna `[a_0,..., a_d]` (av typ `Double[]`), indata-`x : FixedPoint` och utdata `y : FixedPoint` (ursprungligen noll):</span><span class="sxs-lookup"><span data-stu-id="27e93-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="27e93-145">Resultatet, $P (x) = 1 + 2x $, kommer att lagras i `yFxP`.</span><span class="sxs-lookup"><span data-stu-id="27e93-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="27e93-146">Den andra, `EvaluateEvenPolynomialFxP`och den tredje `EvaluateOddPolynomialFxP`är specialiseringar för fall av jämna respektive udda funktioner.</span><span class="sxs-lookup"><span data-stu-id="27e93-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="27e93-147">Det vill säga för en jämn/udda funktion $f (x) $ och $ $ P_ {jämna} (x) = a_0 + A_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ approximeras bra genom att $P _ {t.o.m.} (x) $ eller $P _ {udda} (x): = x\cdot P_ {jämna} (x) $ benämningar.</span><span class="sxs-lookup"><span data-stu-id="27e93-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="27e93-148">I Q # kan dessa två fall hanteras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="27e93-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="27e93-149">som utvärderar $P _ {t.o.m.} (x) = 1 + 2x ^ 2 $ och</span><span class="sxs-lookup"><span data-stu-id="27e93-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="27e93-150">som utvärderar $P _ {udda} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="27e93-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="27e93-151">Fler exempel</span><span class="sxs-lookup"><span data-stu-id="27e93-151">More samples</span></span>

<span data-ttu-id="27e93-152">Du hittar fler exempel i [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="27e93-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="27e93-153">Kom igång genom att klona lagrings platsen och öppna undermappen `Numerics`:</span><span class="sxs-lookup"><span data-stu-id="27e93-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="27e93-154">`cd` till en av exempel mapparna och kör exemplet via</span><span class="sxs-lookup"><span data-stu-id="27e93-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
