---
title: Flera qubits | Microsoft Docs
description: Flera qubits
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3e0404cfd67f693ff6b7a8297566e59208fc7ec0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183785"
---
# <a name="multiple-qubits"></a>Flera qubits

Även om en qubit-grind har vissa funktioner som är intuitiva, till exempel möjligheten att vara i mer än ett tillstånd vid en viss tidpunkt, om allt vi hade i en Quantum-dator var en qubit-grind skulle vi ha en enhet med data ström som skulle vara dwarfed av till och med en kalkylator kan du själv göra en klassisk superdator.
Den verkliga kraften i Quantum Computing blir bara uppenbart när vi ökar antalet qubits.
Den här kraften uppstår delvis eftersom dimensionen för vektor utrymmet i Quantum State-vektorer växer exponentiellt med antalet qubits.
Det innebär att även om en enda qubit kan modelleras på ett enkelt sätt, skulle en simulering av en 50-qubit Quantum-beräkning utan tvekan push-överföra gränserna för befintliga superdatorer.
Att öka storleken på beräkningen genom att endast en ytterligare qubit *fördubblar* det minne som krävs för att lagra statusen och *fördubblar* beräknings tiden.
Den här snabba dubbleringen av beräknings kraften är varför en Quantum dator med ett relativt litet antal qubits kan överskrida de mest kraftfulla superdatorerna i idag, imorgon och senare för vissa beräknings uppgifter.

Varför har vi exponentiell tillväxt i Quantum State-vektorer?  Vårt mål i det här avsnittet är att granska de regler som används för att skapa qubit-tillstånd från en qubit och diskutera de grind åtgärder som vi behöver ta med i den här gaten för att bilda en Universal many-qubit Quantum-dator.
Dessa verktyg är absolut nödvändiga för att förstå de grind uppsättningar som ofta används i Q # Code och för att få intuition om varför Quantum-effekter som entanglement eller interferens återger Quantum Computing mer kraftfullare än klassisk data behandling.

## <a name="representing-two-qubits"></a>Som representerar två qubits
Den största skillnaden mellan ett-och två-qubit-tillstånd är att två-qubit-tillstånd är fyra dimensionell snarare än två mått.
Detta beror på att beräknings grunden för qubit-tillstånd bildas av behållen produkter i ett qubit tillstånd.  Till exempel har vi \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\@no__ t_9_ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0 @no__ t_40_ \\ 1 \end{bmatrix}.
\end{align}

Det är enkelt att se att mer än Quantum-läget för $n $ qubits representeras av en enhets vektor med dimension $2 ^ n $ med denna konstruktion.  Vektorn

$ $ \begin{bmatrix} \alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11} \end{bmatrix} $ $

representerar ett Quantum-tillstånd på två qubits om $ | \alpha_{00}| ^ 2 + | \alpha_{01}| ^ 2 + | \alpha_{10}| ^ 2 + | \alpha_{11}| ^ 2 = 1 $. Precis som med enkla qubits innehåller Quantum State-vektorn för flera qubits all information som behövs för att beskriva systemets beteende.

Om vi får två separata qubits, en i tillstånd $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ och en andra qubit i tillstånd $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, är motsvarande två qubit tillstånd

$ $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \ Beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix}, $ $

där åtgärden $ \otimes $ kallas för bevarans produkt (eller Kronecker-produkt) av vektorer. Observera att vi alltid kan använda behållar produkten av två qubit tillstånd för att bilda ett qubit tillstånd, men inte alla två-qubit Quantum-tillstånd kan skrivas som behållar produkt i två qubit-tillstånd.
Det finns till exempel inga tillstånd $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ och $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ så att deras beställnings produkt är tillståndet 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Ett sådant qubit tillstånd, som inte kan skrivas som en behållar produkt i ett qubit tillstånd, kallas "Entangled State". de två qubits sägs vara [*Entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).  Det går inte att tala om att Quantum-tillståndet inte kan betraktas som en behållar produkt av enskilda qubit-tillstånd, men den information som tillståndet omfattar är inte begränsad till någon av qubits individuellt.  Informationen lagras i stället inte lokalt i korrelationerna mellan de två tillstånden.  Den här informationen är en av de viktigaste särskiljande funktionerna i Quantum Computing och är viktiga för ett antal Quantum-protokoll, inklusive [Quantum Teleportion](https://github.com/Microsoft/Quantum/tree/master/Samples/src/Teleportation) och [Quantum fel korrigering](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Mäta två qubit-tillstånd ##
Att mäta två qubit-tillstånd liknar en qubit mått. Mäta status

$ $ \begin{bmatrix} \alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11} \end{bmatrix} $ $

ger $0 $ med sannolikhet $ | \alpha_{00}| ^ $2, $1 $ med sannolikhet $ | \alpha_{01}| ^ $2, $10 $ med sannolikhet $ | \alpha_{10}| ^ $2 och $11 $ med sannolikhet $ | \alpha_{11}| ^ $2. Variablerna $ \alpha_{00}, \alpha_{01}, \alpha_{10}, $ och $ \alpha_{11}$ kallades avsiktligt för att göra anslutningen tydlig. Om resultatet är $0 $ efter mätningen har Quantum-läget för qubit-systemet minimerats och är nu

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Det är också möjligt att mäta bara en qubit av ett qubit Quantum-tillstånd. I de fall där du endast mäter en av qubits är effekten av måttet olika, eftersom hela statusen inte är komprimerad till ett beräknings underlag, i stället komprimeras endast till ett under system.  I sådana fall kan du med andra ord bara mäta en qubit för att minimera ett av under systemen, men inte alla.  

För att se detta bör du mäta det första qubit av följande tillstånd, som bildas genom att använda Hadamard-transformeringen $H $ på två qubits som ursprungligen har angetts till status "0": $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{ bmatrix} 1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 @no__ t_10_ \\ 1 &-1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ end {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{Cases}\text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{Outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{ fall}.
$ $ Båda resultat har en sannolikhet på 50%.  Resultatet som 50% sannolikheten för båda kan Reformas från det faktum att den inledande Quantum-delläges vektorn är invariant under växlingen $0 $ med $1 $ på den första qubit.

Den matematiska regeln för att mäta den första eller andra qubit är enkel.  Om vi låter $e _k $ vara $k ^ {\rm to} $ beräknings bas vektor och låta $S $ vara en uppsättning $e _k $ så att qubit i fråga tar värdet $1 $ för värdet för $k $.  Om vi till exempel är intresse rad av att mäta det första qubit skulle $S $ bestå av $e _2 \ equiv $10 och $e _3 \ equiv $11.  På samma sätt skulle vi, om vi är intresserade av den andra qubit $S $, bestå av $e _1 \ equiv $1 och $e _3 \equiv $11.  Sannolikheten för att mäta de valda qubit till $1 $ är för State Vector $ \psi $

$ $ P (\text{Outcome} = 1) = \sum_{e_k \text{i uppsättningen} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

Eftersom varje qubit-mått bara kan ge $0 $ eller $1 $, är sannolikheten att mäta $0 $ bara $1-P (\text{Outcome} = 1) $.  Det är därför som vi bara uttryckligen ger en formel för sannolikheten för att mäta $1 $.

Den åtgärd som en sådan mätning har på tillstånd kan uttryckas matematiskt som

$ $ \psi \mapsto \frac{\sum_{e_k \text{i uppsättningen} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\text{Outcome} = 1)}}.
$$

Försiktig läsare kan bekymra sig om vad som händer när sannolikheten för mätningen är noll.  Även om det resulterande läget är tekniskt odefinierat i det här fallet behöver vi aldrig bekymra dig om sådana behov eftersom sannolikheten är noll!


Om vi tar $ \psi $ som en enhetlig delstats Vector som anges ovan och som är intresserade av att mäta de första qubit sedan 

$ $ P (\text{Measurement av First qubit} = 1) = (\psi ^ \dagger e_2) (e_2 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_2 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Observera att detta är bara summan av de två sannolikheter som skulle förväntas för att mäta resultaten $10 $ och $11 $ var alla qubits som skulle mätas.
I vårt exempel utvärderas detta till

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ end {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \ Starta {bmatrix} 0 & 0 & 0 & 1 \ end {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ slut {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

vilket perfekt matchar vad vår intuition anger för oss att sannolikheten ska vara.  På samma sätt kan tillstånd skrivas som

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $

återigen i enlighet med våra intuition.

## <a name="two-qubit-operations"></a>Två qubit-åtgärder
Precis som i ett qubit-fall är en enhetlig omvandling en giltig åtgärd på qubits. I allmänhet är en enhetlig omvandling på $n $ qubits en matris $U $ med storleken $2 ^ n \times 2 ^ n $ (så att den fungerar på vektorer med storleken $2 ^ n $), till exempel $U ^{-1} = U ^ \dagger $. CNOT (styrd-NOT) är till exempel en ofta använd qubit-grind och representeras av följande enhetliga matris:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \\0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

Vi kan också bilda två qubit-portar genom att använda qubit-portar på båda qubits. Om vi till exempel använder grindarna 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

och

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

till den första och andra qubits är detta detsamma som att tillämpa den qubit som anges av sin beskrivare produkt: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \ börja med {bmatrix} AE \ AF \ är \ BF \\\\ AG \ Ah \ BG \ BH \\\\ CE \ CF \ ta bort \\: CG \ CH \ \ DH \end{bmatrix}. $ $ därför kan vi bilda två-qubit-portar genom att använda behållar produkten av vissa kända portar med en qubit. Några exempel på två-qubit-portar är $H \otimes H $, $X \otimes \boldone $ och $X \otimes Z $.

Observera att även om det finns två qubit-portar som definierar en qubit-grind genom att ta sin betecknings produkt, är omvänt inte sant. Alla qubit-portar kan inte skrivas som behållar produkter av qubit-portar.  En sådan grind kallas en *Entangling* -grind. Ett exempel på en Entangling-grind är CNOT-porten.

Intuition bakom en kontrollerad, icke-grind kan generaliseras till valfria grindar.  En kontrollerad grind i allmänhet är en grind som fungerar som identitet (dvs. den har ingen åtgärd) om inte en angiven qubit är $1 $.  Vi betecknar en kontrollerad topp, som styrs i det här fallet på qubit med etiketten $x $, med en $ \Lambda\_x (U) $.  Som exempel $ \Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ och $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $ , där $e\_$0 och $e\_$1 är de beräknings bas vektorer för en enskild qubit som motsvarar värdena $0 $ och $1 $.  Överväg till exempel följande kontrollerad-$Z $-grind och kan sedan uttrycka detta som $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

Att skapa kontrollerade unitaries på ett effektivt sätt är en stor utmaning.  Det enklaste sättet att införa detta kräver att du skapar en databas med kontrollerade versioner av fundamentala grindar och ersätter varje fundamental grind i den ursprungliga enhetliga driften med dess styrda motsvarighet.  Detta är ofta ganska onödig och smarta Insight kan ofta användas för att bara ersätta några få portar med kontrollerade versioner för att uppnå samma påverkan.  Därför erbjuder vi i vårt ramverk möjligheten att utföra antingen naïve-metoden för att styra eller tillåta användaren att definiera en kontrollerad version av den enhetliga om en optimerad version är känd.

Portar kan också styras med klassisk information.  En klassisk styrd icke-grind är till exempel bara en vanlig icke-grind, men den tillämpas bara om en klassisk bit är $1 $ i stället för en Quantum-bit.  I det här fallet kan en klassisk kontrollerad grind betraktas som en If-instruktion i den Quantum-kod där grinden endast används i en gren av koden.


Precis som i ett qubit-fall är en qubit-grind universell om en produkt av någon av $4 de som är en produkt av grindar kan approximeras från denna uppsättning till godtycklig precision.
Ett exempel på en universell grind uppsättning är Hadamard-porten, T-porten och CNOT-porten. Genom att ta produkter av de här portarna kan vi approximera en enhetlig matris på två qubits.

## <a name="many-qubit-systems"></a>Många-qubit system
Vi följer exakt samma mönster som utforskas i två-qubit-fallet för att bygga många-qubit Quantum-tillstånd från mindre system.  Dessa tillstånd skapas genom att bilda flernivå produkter av mindre tillstånd.  Överväg till exempel att koda bit strängen $1011001 $ i en Quantum-dator.  Vi kan koda detta som

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{ bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Quantum Gates fungerar på exakt samma sätt.  Om vi till exempel vill tillämpa $X $-grind på den första qubit och sedan utföra en CNOT mellan den andra och tredje qubits kan vi uttrycka den här omvandlingen som

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\ otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\ otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

I många qubit-system finns det ofta ett behov av att allokera och ta bort qubits som fungerar som temporärt minne för Quantum-datorn.  En sådan qubit kallas för en Ancilla.  Som standard antar vi att qubit-tillstånd initieras till $e _0 $ vid allokering.  Vi förväntar oss ytterligare att det returneras igen till $e _0 $ före tilldelningen.  Detta antagande är viktigt eftersom om en Ancilla qubit blir Entangled med en annan qubit registrera sig när den blir avallokerad, skadas Ancilla.  Därför förutsätter vi alltid att sådana qubits återställs till sitt ursprungliga tillstånd innan de släpps.

Slutligen, även om nya grindar som krävs för att läggas till i vår grind uppsättning för att uppnå Universal Quantum computing för två qubit quantum-datorer, behöver inga nya grindar införas i multi-qubit-fallet.  Portarna $H $, $T $ och CNOT bildar en universell grind på många qubits, eftersom en allmän och enhetlig omvandling kan delas upp i en serie med två qubit-rotationer.  Vi kan sedan dra nytta av den teori som utvecklades för det qubit fallet och använda den igen när vi har många qubits.

Även om den linjära Algebraic-notation som vi har använt hittills kan användas för att beskriva qubit-tillstånd, blir det allt besvärligt att öka storleken på tillstånden.  Den resulterande kolumn-Vectorn för en length 7-bitars sträng, till exempel, är $128 $ Dimensional, som gör att du kan uttrycka den med hjälp av notationen som beskrivits tidigare mycket besvärlig.  Därför presenterar vi en vanlig notation i Quantum Computing som gör det möjligt för oss att kortfattat beskriva dessa avancerade vektorer.