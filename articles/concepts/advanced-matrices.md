---
title: Avancerade matrisbegrepp
description: Lär dig mer om eigenvectors, Eigenvalues och Matrix-exponenter, de grundläggande verktyg som används för att beskriva och simulera Quantum-algoritmer.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- $$
- $$
- $$
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269464"
---
# <a name="advanced-matrix-concepts"></a>Avancerade mat ris koncept #

Vi utökar nu vår modifiering av matriser till [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) och [*exponentieller*](https://en.wikipedia.org/wiki/Matrix_exponential) som utgör en grundläggande uppsättning verktyg som vi behöver för att beskriva och implementera Quantum-algoritmer.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues och Eigenvectors ##

Låt $M $ vara en kvadratisk matris och $v $ vara en Vector som inte är en vektor som inte är noll (dvs. Vector med alla poster som är lika med $0 $ ).

Vi antar $ att $v är en [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) av $M $ om $MV = ka $ för en viss siffra $c $ . Vi antar att $c $ är den [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) som motsvarar eigenvector $v $ . I allmänhet kan en matris $M $ omvandla en vektor till någon annan Vector, men en eigenvector är speciell eftersom den lämnas oförändrad, förutom om den multipliceras med ett tal. Observera att om $v $ är en eigenvector med eigenvalue $c $ , är $av $ också en eigenvector (för alla $a som inte $ är noll) med samma eigenvalue.

Till exempel, för identitets mat ris, är varje Vector $v $ en eigenvector med eigenvalue $1 $ .

Ett annat exempel är om du vill ha en [*Diagonal matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ som bara innehåller poster som inte är noll i diagonalen:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & D_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .
$$

Vektorerna

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} och \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$

är eigenvectors i matrisen med Eigenvalues $d _1 $ , $d _2 $ och $d _3 $ . Om $d _1 $ , $d _2 $ och $d _3 $ är distinkta tal, är dessa vektorer (och deras multiplar) de enda eigenvectors för mat ris $D $ . I allmänhet är det enkelt att läsa av Eigenvalues och eigenvectors för en diagonal matris. Eigenvalues är alla siffror som visas i diagonalen och deras respektive eigenvectors är enhets vektorerna med en post som motsvarar $1 $ och de återstående posterna som motsvarar $0 $ .

Observera i exemplet ovan att $D eigenvectors $ utgör grunden för $3 $ -dimensionella vektorer. En basis är en uppsättning vektorer så att alla vektorer kan skrivas som en linjär kombination av dem. Mer explicit, $v _1 $ , $v _2 $ och $v _3 $ form a-basis om någon Vector $v $ kan skrivas som $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ för vissa siffror $a _1 $ , $a _2 $ och $a _3 $ .

Kom ihåg att en Hermitian-matris (även kallat eget) är en komplex fyrkantig mat ris som motsvarar dess egna komplexa konjugat, medan en enhetlig matris är en komplex fyrkantig mat ris vars invertering är lika med dess komplexa konjugat.
För Hermitian-och enhetliga matriser, som i huvudsak är de enda matriser som påträffas i Quantum Computing, finns det ett allmänt resultat som kallas för [*Spectral-satsen*](https://en.wikipedia.org/wiki/Spectral_theorem), vilket förutsätter följande: för alla Hermitian eller enhetliga matriser $M finns $ det en enhetlig $U $ som $M = U ^ \dagger D U $ för viss Diagonal matris $D $ . Dessutom är de diagonala posterna för $D $ Eigenvalues av $M $ .

Vi vet redan hur man beräknar Eigenvalues och eigenvectors för en diagonal matris $D $ . Med den här satsen vet vi att om $v $ är en eigenvector av $D $ med eigenvalue $c $ , d.v.s. $DV = ka $ , kommer $U ^ \dagger v $ att vara en eigenvector av $M $ med eigenvalue $c $ . Detta beror på att

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Mat ris exponenter
En [*mat ris exponent*](https://en.wikipedia.org/wiki/Matrix_exponential) kan också definieras i exakt analog till exponentiell funktionen.  Matrisens exponentiella $A $ kan uttryckas som

$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $

Detta är viktigt eftersom den resulterande mekaniska tids utvecklingen beskrivs av en enhetlig matris i formuläret $e ^ {iB } $ för Hermitian matrix $B $ .  Av den anledningen är framställningen av matriser en grundläggande del av Quantum data behandling och som t. ex. Q # innehåller inbyggda rutiner för att beskriva dessa åtgärder.
Det finns många sätt att beräkna en matris på en klassisk dator, och i stort sett en så stor uppskattning som en exponent är fraught med Peril.  Se [*Cleve moler och Charles Van-lånet. "Nineteen misstänkta-sätt att beräkna exponenten för en matris." SIAM granska 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) för mer information om de utmaningar som uppstår.

Det enklaste sättet att förstå hur du beräknar exponenten för en matris är genom Eigenvalues och eigenvectors i matrisen.  Mer specifikt säger Spectral-satsen ovan att för varje Hermitian eller en enhetlig matris $A $ det finns en enhetlig matris $U $ och en diagonal mat ris $D $ som $A = U ^ \dagger D U $ .  På grund av egenskaperna för unitarity har vi $A ^ 2 = U ^ \dagger D ^ 2 U $ och på samma sätt för alla power $p $ $A ^ p = U ^ \dagger D ^ p U $ .  Om vi ersätter detta i Operator definitionen för operatorn exponentiell, får vi:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {NN } ) \end{ bmatrix } U. $ $

Om du till andra ord omvandlar till eigenbasis i matrisen $A, $ motsvarar den vanliga exponenten för Eigenvalues i matrisen.  Så många åtgärder som används i Quantum Computing är det här syftet med att omvandla till eigenbasis i en matris för att förenkla utförandet av operatören exponentiellt visas ofta och är grunden bakom många Quantum-algoritmer som Trotter – Suzuki Quantum simulerings metoder som beskrivs senare i den här hand boken.

En annan användbar egenskap är om $B $ är både enhetligt och Hermitian, d.v.s. $B = b ^ {-1 } = B ^ \dagger $ sedan $B ^ 2 = \boldone $ . Genom att tillämpa den här regeln på ovanstående expansion av matrisen exponent och genom att gruppera $ \boldone $ och de $B $ villkoren tillsammans, kan det se att för alla verkliga värden $x $ identiteten

$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $


innehålla. Det här sticket är särskilt användbart eftersom det kan vara orsaken till att måtten för åtgärder i matrisen har, även om dimensionen för $B $ är exponentiellt stor för det särskilda fallet när $B $ är både enhetligt och Hermitian.
