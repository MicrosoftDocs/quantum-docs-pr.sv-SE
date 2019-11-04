---
title: Vektorer och matriser | Microsoft Docs
description: Vektorer och matriser
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183751"
---
# <a name="vectors-and-matrices"></a>Vektorer och matriser

En del bekant med vektorer och matriser är viktigt för att förstå Quantum Computing. Vi ger en kort introduktion nedan och intresserade läsare rekommenderas att läsa en standard referens för linjära algebra, till exempel *Strang, G. (1993). Introduktion till linjär algebra (vol. 3). Wellesley, MA: Wellesley-Cambridge press* eller a online Reference, till exempel [linjär algebra](http://joshua.smcvt.edu/linearalgebra/).

En kolumn vektor (eller bara [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ of dimension (eller storlek) $n $ är en samling $n $ komplexa tal $ (v_1, v_2, \ldots, V_n) $ ordnade som en kolumn:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ V_n \end{bmatrix} $ $

Normen för en Vector $v $ definieras som $ \sqrt{\sum\_i | v\_i | ^ 2} $. En Vector anses vara av enhets norm (eller också kallas den för en [*enhets vektor*](https://en.wikipedia.org/wiki/Unit_vector)) om dess norm är $1 $. Det [*angränsande av en vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ betecknas $v ^ \dagger $ och definieras som följande rad vektor där $\*$ anger det komplexa konjugatet.

$ $ \begin{bmatrix}v_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix}v_1 ^ * & \cdots & V_n ^ * \end{bmatrix} $ $

Det vanligaste sättet att multiplicera två vektorer är genom den [*inre produkten*](https://en.wikipedia.org/wiki/Inner_product_space), även kallat en punkt produkt.  Den inre produkten ger projektionen av en Vector till en annan och är värdefull för att beskriva hur man uttrycker en Vector som en summa av andra enklare vektorer.  Den inre produkten mellan $u $ och $v $, betecknad $ \left\langle u, v\right\rangle $ definieras som

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Den här notationen tillåter också att en Vector-$v $ skrivs som $ \sqrt{\langle v, v\rangle} $.

Vi kan multiplicera en Vector med ett tal $c $ för att skapa en ny Vector vars poster multipliceras med $c $. Vi kan också lägga till två vektorer $u $ och $v $ för att skapa en ny Vector vars poster är summan av posterna i $u $ och $v $. Dessa åtgärder beskrivs nedan:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots @no__ t_10_ \\ V_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

En [*matris*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) med storlek $m \times n $ är en samling $mn $ komplexa tal ordnade i $m $-rader och $n $-kolumner enligt nedan:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {mn}\\t_11_ \end{bmatrix}. $ $

Observera att en Vector med dimension $n $ bara är en matris med storlek $n \times $1. Precis som med vektorer kan vi multiplicera en matris med ett tal $c $ för att hämta en ny matris där varje post multipliceras med $c $, och vi kan lägga till två matriser av samma storlek för att skapa en ny matris vars poster är summan av respektive poster för de två matriserna. 

## <a name="matrix-multiplication-and-tensor-products"></a>Matris-och beskrivares produkter

Vi kan också multiplicera två matriser $M $ of dimension $m \times n $ och $N $ dimension $n \times p $ för att få en ny matris $P $ of dimension $m \times p $ enligt följande:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {mn} \end{bmatrix} BEGIN {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1P}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2p}\\\\ \ddots\\\\ N_ {N1} ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1P}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2p}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{bmatrix} \end{align}

var posterna för $P $ är $P _ {IK} = \sum_j M_ {N_} {JK} $. Posten $P _{11}$ är till exempel den inre produkten av den första raden i $M $ med den första kolumnen i $N $. Observera att eftersom en Vector bara är ett specialfall av en matris, sträcker sig denna definition till multiplikation med mat ris vektorer. 

Alla matriser som vi anser är antingen fyrkantiga matriser, där antalet rader och kolumner är lika med, eller vektorer, som motsvarar endast $1 $-kolumnen. En speciell klammer är [*identitets mat*](https://en.wikipedia.org/wiki/Identity_matrix)ris, med namnet $ \boldone $, som har alla dess diagonala element lika med $1 $ och återstående element som motsvarar $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

För en fyrkantig matris $A $ säger vi att en matris $B $ är [*inversen*](https://en.wikipedia.org/wiki/Invertible_matrix) om $AB = BA = \boldone $. Inversen till en matris behöver inte finnas, men när den finns är den unik och vi betecknar den $A ^{-1}$. 

För alla matriser $M $ är den angränsande eller konjugatingen av $M $ en matris $N $ så att $N _ {M_} = {Ji} ^\*$. Det angränsande av $M $ är vanligt vis betecknad $M ^ \dagger $. Vi säger att en matris $U $ är [*enhetlig*](https://en.wikipedia.org/wiki/Unitary_matrix) om $UU ^ \Dagger = u ^ \dagger U = \boldone $ eller motsvarande, $U ^{-1} = U ^ \dagger $.  Kanske är den viktigaste egenskapen för enhetliga matriser att de behåller normen i en Vector.  Detta inträffar eftersom 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

En matris $M $ sägs vara [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) om $M = M ^ \dagger $.

Slutligen är bevarans [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (eller Kronecker produkt) av två matriser $M $ i storlek $m \times n $ och $N $ i storlek $p \times q $ är en större matris $P = M\otimes n $ i storlek $MP \times NQ $, och hämtas från $M $ och $N $ enligt följande:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ M_ {M1} ~ ~ \cdots ~ ~ M_ {mn} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots @no__ t_8_ \\ N_ {P1} ~ ~ \cdots ~ ~ N_ {PQ} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {PQ} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {PQ} \end{bmatrix}\\\\ \ddots M_\\\Begin{bmatrix} {M1} N_ \\ ~ ~ \ cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {PQ} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {mn} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {PQ} \end {bmatrix} \end{bmatrix}.
\end{align}

Detta demonstreras bättre med några exempel:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} @no__ t_10_ \\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ en d \\\\ en e \\\\ b c \\\\ b d \\\\ be\end {bmatrix} $ $

och

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ BF \\t_15_ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ CH \ GD \ DH \end{bmatrix}.
$$

En slutgiltig, användbar, utgångs konvention som omger betecknings produkter är att, för alla vektorer $v $ eller Matrix $M $, $v ^ {\otimes n} $ eller $M ^ {\otimes n} $ är kort hand för en $n $-viknings produkt med upprepade nivåer.  Exempel:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ end {bmatrix}.
\end{align}

