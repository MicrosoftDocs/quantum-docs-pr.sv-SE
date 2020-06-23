---
title: Introduktion till kvantmatematikbiblioteket | Microsoft Docs
description: Introduktion till kvantmatematikbiblioteket
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273966"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="2be03-103">Introduktion till kvantmatematikbiblioteket</span><span class="sxs-lookup"><span data-stu-id="2be03-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="2be03-104">Många kvantalgoritmer använder [orakel](xref:microsoft.quantum.concepts.oracles) som utvärderar matematiska funktioner på en superposition av indata.</span><span class="sxs-lookup"><span data-stu-id="2be03-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="2be03-105">Till utvärderar huvudkomponenten i Shors algoritm $f(x) = a^x\operatornamn{mod} N$ för en fast $a$, numret att faktorisera $N$ samt $x$ ett $2n$-kvantbitheltal i en enhetlig superposition över alla $2n$-bitssträngar.</span><span class="sxs-lookup"><span data-stu-id="2be03-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="2be03-106">För att Shors algoritm ska kunna köras på en faktisk kvantdator måste den här funktionen skrivas i termer av måldatorns interna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2be03-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="2be03-107">Med hjälp av den binära representationen av $x$ med $x_i$ som anger $i$:e biten med räkning från den minst signifikanta biten kan $f(x)$ skrivas som $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatornamn{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="2be03-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="2be03-108">Detta kan i sin tur skrivas som en produkt (mod N) med termerna $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="2be03-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="2be03-109">Funktionen $f(x)$ kan därmed implementeras med hjälp av en sekvens med $2n$ (modulära) multiplikationer med $a^{2^i}$ förutsatt att $x_i$ inte är noll.</span><span class="sxs-lookup"><span data-stu-id="2be03-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="2be03-110">Konstanterna $a^{2^i}$ kan förhandsberäknas och reduceras modulo N innan algoritmen körs.</span><span class="sxs-lookup"><span data-stu-id="2be03-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="2be03-111">Den här sekvensen med kontrollerade modulära multiplikationer kan förenklas ytterligare: Varje multiplikation kan utföras med hjälp av en sekvens med $n$ kontrollerade modulära additioner, och varje modulär addition kan skapas från en vanlig addition och en jämförelseoperator.</span><span class="sxs-lookup"><span data-stu-id="2be03-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="2be03-112">Eftersom det krävs så många steg för att nå en faktisk implementering skulle det vara mycket användbart att ha sådan funktionalitet tillgänglig från början.</span><span class="sxs-lookup"><span data-stu-id="2be03-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="2be03-113">Detta är anledningen till att Quantum Development Kit har stöd för en mängd olika numeriska funktioner.</span><span class="sxs-lookup"><span data-stu-id="2be03-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="2be03-114">Funktioner</span><span class="sxs-lookup"><span data-stu-id="2be03-114">Functionality</span></span>

<span data-ttu-id="2be03-115">Utöver den heltalsaritmetik som vi har gått igenom hittills tillhandahåller matematikbiblioteket</span><span class="sxs-lookup"><span data-stu-id="2be03-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="2be03-116">Funktioner för (o)signerade heltal (multiplikation, kvadratrot, division med rest, inversion, ...) med ett eller två kvantheltal som indata</span><span class="sxs-lookup"><span data-stu-id="2be03-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="2be03-117">Funktioner för fast punkt (lägg till/subtrahera, multiplicera, kvadratrot, 1/x, polynomisk utvärdering) med ett eller två kvanttal med fast punkt som indata</span><span class="sxs-lookup"><span data-stu-id="2be03-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="2be03-118">Komma igång</span><span class="sxs-lookup"><span data-stu-id="2be03-118">Getting started</span></span>

<span data-ttu-id="2be03-119">Om du vill komma igång med matematikbiblioteket kan du läsa [installationsguiden](xref:microsoft.quantum.numerics.installation) och läsa mer om hur du [använder matematikbiblioteket](xref:microsoft.quantum.numerics.usage).</span><span class="sxs-lookup"><span data-stu-id="2be03-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
