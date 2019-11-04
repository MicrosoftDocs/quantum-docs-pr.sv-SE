---
title: Introduktion till kvantmatematikbiblioteket | Microsoft Docs
description: Introduktion till kvantmatematikbiblioteket
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442443"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Introduktion till kvantmatematikbiblioteket

Många kvantalgoritmer använder [orakel](xref:microsoft.quantum.concepts.oracles) som utvärderar matematiska funktioner på en superposition av indata.
Till utvärderar huvudkomponenten i Shors algoritm $f(x) = a^x\operatornamn{mod} N$ för en fast $a$, numret att faktorisera $N$ samt $x$ ett $2n$-kvantbitheltal i en enhetlig superposition över alla $2n$-bitssträngar.

För att Shors algoritm ska kunna köras på en faktisk kvantdator måste den här funktionen skrivas i termer av måldatorns interna åtgärder.
Med hjälp av den binära representationen av $x$ med $x_i$ som anger $i$:e biten med räkning från den minst signifikanta biten kan $f(x)$ skrivas som $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatornamn{mod} N$.
Detta kan i sin tur skrivas som en produkt (mod N) med termerna $a^{2^i x_i}=(a^{2^i})^{x_i}$. Funktionen $f(x)$ kan därmed implementeras med hjälp av en sekvens med $2n$ (modulära) multiplikationer med $a^{2^i}$ förutsatt att $x_i$ inte är noll. Konstanterna $a^{2^i}$ kan förhandsberäknas och reduceras modulo N innan algoritmen körs.

Den här sekvensen med kontrollerade modulära multiplikationer kan förenklas ytterligare: Varje multiplikation kan utföras med hjälp av en sekvens med $n$ kontrollerade modulära additioner, och varje modulär addition kan skapas från en vanlig addition och en jämförelseoperator.


Eftersom det krävs så många steg för att nå en faktisk implementering skulle det vara mycket användbart att ha sådan funktionalitet tillgänglig från början.
Detta är anledningen till att Quantum Development Kit har stöd för en mängd olika numeriska funktioner.


## <a name="functionality"></a>Funktioner

Utöver den heltalsaritmetik som vi har gått igenom hittills tillhandahåller matematikbiblioteket

 - Funktioner för (o)signerade heltal (multiplikation, kvadratrot, division med rest, inversion, ...) med ett eller två kvantheltal som indata
 - Funktioner för fast punkt (lägg till/subtrahera, multiplicera, kvadratrot, 1/x, polynomisk utvärdering) med ett eller två kvanttal med fast punkt som indata

## <a name="getting-started"></a>Komma igång

Om du vill komma igång med matematikbiblioteket kan du läsa [installationsguiden](xref:microsoft.quantum.numerics.installation) och läsa mer om hur du [använder matematikbiblioteket](xref:microsoft.quantum.numerics.usage).
