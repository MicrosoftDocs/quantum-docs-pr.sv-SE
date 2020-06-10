---
title: Qubit i Quantum Computing
description: Lär dig mer om qubits, den grundläggande informations enheten i Quantum Computing.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
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
ms.openlocfilehash: 833c9649b7fbcf8b9fde62c37246b9345fe59a92
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630346"
---
# <a name="the-qubit"></a>Qubit

Precis som BITS är det grundläggande informations objektet i klassisk data behandling, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum bitar) är det grundläggande objektet av information i Quantum Computing.  För att förstå den här korrespondensen ska vi titta på det enklaste exemplet: en enda qubit.

## <a name="representing-a-qubit"></a>Representerar en qubit

En bit, eller binär siffra, kan ha värdet antingen $0 $ eller $1 $ , men en qubit kan ha ett värde som är antingen av dessa eller en Quantum superposition på $0 $ och $1 $ .

Status för en enda qubit kan beskrivas av en tvådimensionell kolumn vektor av enhets norm, det vill säga att kvadratens storlek måste vara sum till $1 $ . Den här vektorn, som kallas Quantum State Vector, innehåller all information som behövs för att beskriva det qubit Quantum-systemet precis som en enskild bit innehåller all information som behövs för att beskriva statusen för en binär variabel.

En tvådimensionell kolumn Vector med reella eller komplexa tal med norm $1 är $ ett möjligt Quantum-tillstånd som innehas av en qubit. Därför representerar $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $ ett qubit-tillstånd om $ \alpha $ och $ \beta $ är komplexa tal som uppfyller $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ . Några exempel på giltiga Quantum State-vektorer som representerar qubits include

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } , \text { och} \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } . $ $

Quantum State-vektorerna $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ och $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ tar en speciell roll. Dessa två vektorer utgör grunden för det vektor utrymme som beskriver qubit status. Det innebär att alla Quantum State Vector kan skrivas som en summa av dessa bas vektorer. Mer specifikt kan vektorn $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ skrivas som $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Även om en rotation av dessa vektorer skulle fungera som en perfekt giltig grund för qubit, väljer vi att ge den behörigheten genom att anropa den till *beräknings grunden*.

Vi tar de här två Quantum staterna för att motsvara de två tillstånden i en klassisk bit, nämligen $0 $ och $1 $ . Standard konventionen är att välja

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , $ $

även om det motsatta valet kan göras lika bra. Därför, från det oändliga antalet möjliga qubit Quantum State Vectors, är det bara två som motsvarar tillstånd för klassiska bitar. alla andra Quantum-tillstånd gör inte det.

## <a name="measuring-a-qubit"></a>Mäta en qubit

Nu när vi vet hur man representerar en qubit kan vi få en del intuition för vad dessa tillstånd representerar genom att diskutera begreppet [*mått*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Ett mått motsvarar den formella idén "tittar" på en qubit, som direkt minimerar Quantum-tillståndet till något av de två klassiska tillstånden $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ eller $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. När en qubit som anges av metoden Quantum State Vector $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $ mäts, erhåller vi resultatet $0 $ med sannolikhet $ | \alpha | ^ 2 $ och resultatet $1 $ med sannolikhet $ | \beta | ^ 2 $ . I resultatet $0 $ är qubit nya tillstånd $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; i resultat $1 $ sitt tillstånd är $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Observera att dessa sannolikheter summerar upp till $1 på $ grund av normaliserings villkoret $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Egenskaperna för måttet innebär också att den övergripande signaturen för den Quantum-tillstånds vektorn är irrelevant. Negation av en Vector motsvarar $ \alpha \rightarrow-\alpha $ och $ \beta \rightarrow-\beta $ . Eftersom sannolikheten för att mäta $0 $ och $1 $ beror på termernas storlek i kvadraten, ändras inte sannolikheten för att infoga sådana tecken. Sådana faser kallas ofta [ `` *globala faser*](https://en.wikipedia.org/wiki/Phase_factor) , och mer allmänt kan vara av formulär $e ^ {i \phi } $ snarare än bara $ \pm 1 $ .

En slutgiltig viktig egenskap för mått är att det inte nödvändigt vis skadar alla vektorer med Quantum-tillstånd. Om vi börjar med en qubit i delstaten $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $, som motsvarar det klassiska läget $0 $ , ger detta tillstånd alltid resultatet $0 $ och lämnar Quantum-läget oförändrat. I det här fallet, om vi bara har klassiska bitar (d.v.s. qubits som är antingen $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ eller $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $), skadar inte systemet systemet. Det innebär att vi kan replikera klassiska data och ändra dem på en Quantum-dator på samma sätt som ett kan göra på en klassisk dator. Möjligheten att lagra information i båda lägena på en gång är att öka den väntande data bearbetningen utöver vad som är möjligt i klassiskt och ytterligare Robs quantum-datorer i möjligheten att kopiera Quantum data på ett inkonsekvenser, se även [no-klonings satsen](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualisera qubits och omvandlingar med hjälp av Bloch-sfären

Qubits kan också bildas i $3 $ D med hjälp av [*sfär*](https://en.wikipedia.org/wiki/Bloch_sphere) representationen Bloch.  Bloch-sfären ger ett sätt att beskriva ett qubit Quantum-tillstånd (som är en tvådimensionell komplex Vector) som en tredimensionell Vector med Real värde.  Detta är viktigt eftersom vi gör det möjligt för oss att visualisera qubit tillstånd och därmed utveckla att det kan vara värdefullt att förstå qubit-tillstånd (där sadly Bloch sfär representationen bryts ned).  Bloch-sfären kan visualiseras på följande sätt:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch-sfär](~/media/concepts_bloch.png)

Pilarna i det här diagrammet visar i vilken riktning som den blinkande läges vektorn pekar och varje omvandling av pilen kan ses som en rotation av en av kardinal axlarna.
När du funderar på en Quantum-beräkning som en sekvens med rotationer är en kraftfull intuition, så det är svårt att använda den här intuition för att utforma och beskriva algoritmer. Q # minskar problemet genom att tillhandahålla ett språk för att beskriva sådana rotationer.

## <a name="single-qubit-operations"></a>Åtgärder med en qubit

Quantum Computers bearbetar data genom att använda en universell uppsättning Quantum-grindar som kan emulera all rotation av den Quantum-tillstånds vektorn.
Detta teoretiskt sett är via för begreppet traditionell (dvs. klassisk) data behandling där en grind anses vara universell om varje omvandling av indata-bitar kan utföras med hjälp av en endensitets krets.
I Quantum Computing är de giltiga omvandlingar som vi kan utföra på en qubit en enhetlig transformering och mätning.
Den *angränsande åtgärden* eller den komplexa konjugats transponeren är av avgörande betydelse för Quantum Computing eftersom det behövs för att invertera Quantum-omvandlingar.
Q # visar detta genom att tillhandahålla metoder för att automatiskt kompilera grind sekvenser till deras angränsande, vilket sparar programmerare från att behöva gå över till hand kod i många fall. Ett exempel på detta visas nedan:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Även om det här är ett enkelt exempel (som <xref:microsoft.quantum.intrinsic.h>  åtgärd är självrelaterat) kan du se hur det blir värdefullt för mer komplicerade qubit-åtgärder.
Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

Det finns bara fyra funktioner som mappar en bit till en bit på en klassisk dator. Det finns däremot ett obegränsat antal enhetliga omvandlingar för en enda qubit på en Quantum-dator. Därför kan ingen begränsad uppsättning primitiva Quantum-åtgärder, som kallas [*grindar*](https://en.wikipedia.org/wiki/Quantum_logic_gate), exakt replikera den oändliga uppsättningen av enhetliga omvandlingar som tillåts i Quantum Computing. Det innebär till skillnad från klassisk dator användning, men det är omöjligt för en Quantum-dator att implementera alla möjliga Quantum-program exakt med ett begränsat antal portar. Därför kan quantum-datorer inte vara universella i samma mening som klassiska datorer. Det innebär att när vi säger att en uppsättning portar är *universella* för Quantum Computing, betyder det egentligen något något svagt än vad vi menar med klassisk data behandling.
För Universality kräver vi att en Quantum-dator endast *uppskattar* varje enhetlig matris inom ett begränsat fel med hjälp av en grind serie med begränsad längd.
Med andra ord är en uppsättning portar en universell grind uppsättning om en enhetlig omvandling kan vara ungefär skriven som en produkt av portar från den här uppsättningen. Vi kräver att för alla före skrivna fel finns grindar $G _ {1 } , G_ {2 } , \ldots, G_N $ från den grind uppsättning som

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

Observera att eftersom konventionen för Matrix multiplikation är att multiplicera från höger till vänster om den första gaten i den här sekvensen $G _N $ , är den sista som tillämpas på den Quantum-tillstånds vektorn. Mer formellt, anta att en sådan grind uppsättning är universell om för varje fel tolerans $ \epsilon>0 finns $ $G _1, \ldots, G_N $ så att avståndet mellan $G _N \ldots G_1 $ och $U $ är högst $ \epsilon $ . Det bästa värdet för $N $ som krävs för att uppnå det här avståndet i $ \epsilon $ bör skala Poly-logarithmically med $1/\ Epsilon $ .

Vad kan en sådan universell grind se ut i praxis?  Den enklaste typen av universella grind för en qubit-grind består av bara två portar: Hadamard-grind $H $ och den så kallade $T $ -grind (kallas även $ \ PI/8 $ -grind):

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ PI/4 } \end{ bmatrix } .
$$

Men av praktiska skäl som rör en Quantum-fel korrigering kan det vara bekvämare att överväga en större grind, nämligen en som kan genereras med hjälp av $H $ och $T $ .
Vi kan klassificera Quantum-grindarna i två kategorier: Clifford-grindar och $T $ -grind.
Den här indelningen är användbar eftersom i många Quantum-fel korrigerings scheman så kallade Clifford-portar är enkla att implementera, det vill säga att de kräver mycket få resurser vad gäller åtgärder och qubits för att implementera feltoleranta fel, medan icke-Clifford-grindar är ganska kostsamma när fel tolerans krävs. Standard uppsättningen med en-qubit Clifford-grindar [som ingår som standard i Q #](xref:microsoft.quantum.libraries.standard.prelude)inkluderar

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2, \qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4h, $ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ i & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{ bmatrix } 1&0 \\\\ & -1 \end{ bmatrix } = T ^ 4.
$$

Här är de åtgärder som $X $ , $Y $ och $Z $ används särskilt ofta och kallas [*Pauli-operatörer*](https://en.wikipedia.org/wiki/Pauli_matrices) efter sin skapare Wolfgang-Pauli.
Tillsammans med en icke-Clifford-grind ($T $ -grind) kan dessa åtgärder sammanställas för att approximera en enhetlig omvandling på en enda qubit.

För ytterligare information om dessa åtgärder, Bloch-sfär representationer och Q #-implementeringar, se [inbyggda funktioner och funktioner](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Som ett exempel på hur enhetlig omvandling kan skapas från dessa primitiver, motsvarar de tre omvandlingarna som visas i Bloch-Kloten ovan motsvarande grind serien $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $.

Den tidigare utgör de mest populära primitiva portarna för att beskriva åtgärder på den logiska nivån i stacken (Tänk på den logiska nivån som nivån för Quantum-algoritmen), men det är ofta praktiskt att överväga mindre grundläggande åtgärder på algoritmnivå, till exempel åtgärder närmare en funktions beskrivnings nivå. Lyckligt vis har Q # också metoder som är tillgängliga för att implementera unitaries på högre nivå, vilket i sin tur gör att algoritmer på hög nivå kan implementeras utan att uttryckligen sammanföra allt till Clifford och $T $ -grindar.

Den enklaste sådan primitiv är den enda qubit. Tre qubit-rotationer anses vanligt vis vara: $R _x $ , $R _y $ och $R _z $ . Om du vill visualisera rotations $R _x (\theta) $, kan du till exempel säga att du vill peka ditt högra tumm utmed riktningen på $x $ -axeln i Bloch-sfären och rotera vektorn med handen genom en vinkel på $ \ theta/2 $ radianer. Den här förvirrande faktorn på $2 $ uppstår från det faktum att rätvinkliga vektorer är $180 ^ \circ $ isär när de ritas på Bloch-sfären, men som i själva verket är 90 ^ ^ \circ $ grader åtskilda. Motsvarande enhetliga matriser är:

\begin{align *} &R_z (\theta) = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ theta/2 } & 0 \\\\ 0 & e ^ {i \ theta/2 } \end{ bmatrix } , \\ \\ &R_x (\theta) = e ^ {-i\theta x/2 } = HR_z (\theta) H = \begin{ bmatrix } \cos (\ theta/2) &-i\sin (\ theta/2) \\ \\ -i\sin (\ theta/2) & \cos (\ theta/2) \end{ bmatrix } , \\ \\ &R_y (\theta) = e ^ {-i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{ bmatrix } \cos (\ theta/2) &-\sin (\ theta/2) \\ \\ \sin (\ theta/2) & \cos (\ theta/2) \end{ bmatrix } . \end{align*}

Precis som tre rotationer kan kombineras tillsammans för att utföra en godtycklig rotation i tre dimensioner, kan den ses från Bloch-sfären som kan skrivas som en sekvens av tre rotationer. För varje enhetlig matris $U $ det finns $ \alpha, \beta, \gamma, \delta, $ till exempel $U = e ^ {i \alpha } R_x (\beta) R_z (\gamma) R_x (\delta) $. Därför $R _z (\theta) $ och $H $ även en universell grind, även om det inte är en diskret uppsättning eftersom $ \theta $ kan ta något värde. Av den anledningen och på grund av program i Quantum-simulering är sådana kontinuerliga portar avgörande för Quantum-beräkning, särskilt på design nivån på Quantum-algoritmen. För att uppnå feltolerant maskin varu implementering kommer de i slut änden att sammanställas i diskreta grind serier som närmar sig dessa rotationer.
