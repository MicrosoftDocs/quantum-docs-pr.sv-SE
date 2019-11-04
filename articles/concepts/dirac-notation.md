---
title: Dirac-notation | Microsoft Docs
description: Dirac-notation
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184771"
---
# <a name="dirac-notation"></a>Dirac-notation

Även om kolumn vektor notation är allmänt förekommande i linjär algebra, är det ofta besvärligt i Quantum Computing, särskilt när du hanterar flera qubits.  När vi till exempel definierar $ \psi $ som en Vector, är det inte uttryckligen uppenbart om $ \psi $ är en rad eller en kolumn vektor.  Om $ \phi $ och $ \psi $ är vektorer är det lika oklart om $ \phi \psi $ är jämnt definierat eftersom formerna för $ \phi $ och $ \psi $ kan vara oklara i kontexten.  Utöver tvetydigheten om figurerna i vektorer, uttrycker även enkla vektorer med den linjära Algebraic-notation som introducerades tidigare kan vara mycket besvärlig. Om vi till exempel vill beskriva ett $n $-qubit-tillstånd där varje qubit tar värdet $0 $, skulle vi formellt uttrycka status som 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

Självklart är det opraktiskt att utvärdera den här behållar produkten eftersom vektorn ligger i ett exponentiellt stort utrymme och så att den här notationen i själva verket är den bästa beskrivningen av det tillstånd som kan ges med hjälp av föregående notation.  

[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) löser dessa problem genom att presentera ett nytt språk som passar de exakta behoven för Quantum Mechanics.  Därför rekommenderar vi läsaren inte att se exemplen i det här avsnittet som en fast Skriv åtgärd för att beskriva Quantum-tillstånd, men för att uppmuntra läsaren att se dessa som förslag som kan användas för att uttrycka ett koncist förslag.

Det finns två typer av vektorer i Dirac-notation: *bra* Vector och *ket* Vector, så de heter eftersom när de placeras tillsammans bildar de ett *bromsat* eller en inre produkt.  Om $ \psi $ är en kolumn vektor kan vi skriva den i Dirac-notation som $ \ket{\psi} $, där $ \ket{\cdot} $ anger att det är en enhets kolumn vektor, d.v.s. en *ket* Vector.  På samma sätt uttrycks rad vektorn $ \psi ^ \dagger $ som $ \bra{\psi} $. Med andra ord, kommer $ \psi ^ \dagger $ erhållas genom att använda Entry komplexa conjugation till elementen i transponera $ \psi $. Bra-ket-notationen innebär direkt att $ \braket{\psi | \psi} $ är den inre produkten av Vector $ \psi $ med sig själv, vilket är genom definition $1 $.  

Allmänt sett, om $ \psi $ och $ \phi $ är Quantum State-vektorer, är deras inre produkt $ \braket{\phi | \psi} $, vilket innebär att sannolikheten för att mäta State $ \ket{\psi} $ ska vara $ \ket{\phi} $ är $ | \braket{\phi | \psi} | ^ 2 $.  

Följande konvention används för att beskriva de Quantum-tillstånd som kodar värdena för noll och ett (qubit beräknings bas tillstånd):

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}, \qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exempel: som representerar Hadamard-åtgärden med Dirac-notation

Följande notation används ofta för att beskriva de tillstånd som uppstår vid tillämpning av Hadamard-porten på $ \ket{0}$ och $ \ket{1}$ (som motsvarar enhets vektorerna i riktningarna $ + x $ och $-x $ på Bloch-sfären):

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}, \qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-} .
$$

Dessa tillstånd kan också utökas med Dirac-notation som summor av $ \ket{0}$ och $ \ket{1}$:

$ $ \ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}), \qquad \ket{-} = \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}).
$$

### <a name="computational-basis-vectors"></a>Beräknings bas vektorer
Detta visar varför dessa tillstånd ofta kallas för *beräknings grund*: varje Quantum-tillstånd kan alltid uttryckas som summor av beräknings bas vektorer och sådana summor är lätt att uttryckas med Dirac notation.  Omvänt är också sant i att tillstånden $ \ket{+} $ och $ \ket{-}$ också utgör grunden för Quantum-tillstånd.  Du kan se detta från det faktum att

$ $ \ket{0} = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}), \qquad \ket{1} = \frac{1}{\sqrt{2}} (\ket{+}-\ket{-}).
$$

Som ett exempel på Dirac-notation bör du överväga bromsen $ \braket{0 | 1} $, som är den inre produkten mellan $0 $ och $1 $.  Den kan skrivas som 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ end {bmatrix} = 0. $ $

Det betyder att $ \ket{0}$ och $ \ket{1}$ är rätvinkliga vektorer, vilket innebär att $ \braket{0 | 1} = \braket{1 | 0} = $0.  Även efter definition $ \braket{0 | 0} = \braket{1 | 1} = 1 $, vilket innebär att de två beräknings bas vektorerna också kan kallas *orthonormal*.
Dessa orthonormal-egenskaper är användbara i följande exempel. Om vi har ett tillstånd $ \ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$, eftersom $ \braket{1 | 0} = $0 sannolikheten för att mäta $1 $ är  

$ $ \big | \braket{1 | \psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>Betecknings produkt notation
Dirac notation innehåller också en produkt struktur med implicita beteckningar i den.  Detta är viktigt eftersom i Quantum Computing är den tillstånds vektor som beskrivs av två korrelerade Quantum-register beskrivare i de två tillstånds vektorerna.  En kortfattad beskrivning av produkt strukturen för beskrivare eller brist på detta är viktigt om du vill förklara en Quantum-beräkning.  Produkt strukturen för beskrivare innebär att vi kan skriva $ \psi \otimes \phi $ för två Quantum State-vektorer $ \phi $ och $ \psi $ som $ \ket{\psi} \ket{\phi} $, som ibland skrivs som $ \ket{\psi} \otimes \ket{\phi} $, trots konventions skrivning $ \otimes $ i mellan vektorerna är onödig.  Till exempel anges tillstånd med två qubits som initieras till noll för tillstånd av

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \ otimes \ket{0}= \ket{0} \ket{0}.
$$

På samma sätt representerar State $ \ket{p} $ för integer $p $ ett Quantum-tillstånd som kodar i binär representation av heltals $p $.  Om vi till exempel vill uttrycka talet $5 $ med en osignerad binär kodning kan vi även uttrycka det som

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.
$$

I den här notationen $ \ket{0}$ behöver inte referera till ett enda qubit-tillstånd utan i stället ett *qubit-register* som lagrar en binär kodning på $0 $.  Skillnaderna mellan dessa två format är vanligt vis tydliga från kontexten.  Denna konvention är användbar för att förenkla det första exemplet som kan skrivas på något av följande sätt:

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= | 0 \ cdots 0 \ rangle = \ket{0}^ {\otimes n} = \ket{0}.
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exempel: beskriva superposition med Dirac-notation
Ett annat exempel på hur du kan använda Dirac notation för att beskriva ett Quantum-tillstånd, Tänk på följande sätt för att skriva ett Quantum-tillstånd som är lika överplacerat över varje möjlig bit sträng med längden $n $

$ $ H ^ {\otimes n} \ket{0} = \frac{1}{2 ^ {n/2}} \sum_{j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}.
$$

Här kan du undra varför summan går från $0 $ till $2 ^ {n}-$1 för $n $ bitar.  Först Observera att det finns $2 ^ {n} $ olika konfigurationer som $n $ BITS kan ta.  Du kan se detta genom att notera att en bit kan ta $2 $-värden, men två bitar kan ta $4 $-värden och så vidare. I allmänhet innebär detta att det finns $2 ^ n $ olika möjliga bit strängar, men det största värdet som har kodats i någon av dem $1 \ cdots 1 = 2 ^ n-$1 och därmed är den övre gränsen för summan.
I det här exemplet använde vi inte $ \ket{+} ^ {\otimes n} = \ket{+} $ i analogt till $ \ket{0}^ {\otimes n} = \ket{0}$ eftersom den här Notations konventionen vanligt vis är reserverad för beräknings grunden med varje qubit initierad till noll.  Även om en sådan konvention skulle vara lämpliga i det här fallet, används den inte i den Quantum Computing-dokumentationen.

### <a name="expressing-linearity-with-dirac-notation"></a>Uttrycka linjärhet med Dirac-notation
En annan bra funktion i Dirac notation är att den är linjär.  Om vi vill skriva för alla fyra Quantum-delstats vektorer 

$ $ (\alpha \ket{\psi} + \beta\ket{\phi}) \otimes (\gamma \ket{\chi} + \delta \ket{\omega}) = \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega} + \beta\gamma\ket{\phi}\ket{\chi} + \beta\delta\ket{\phi}\ket{\omega}. $ $

Det innebär att du kan distribuera handnotationen för beskrivare i Dirac-notation så att du kan dra på att ta med sig produkter mellan delstats vektorer som ser ut precis som vanlig multiplikation.

Bra Vectors följer en liknande konvention till ket-vektorer.  Till exempel motsvarar Vector $ \bra{\psi}\bra{\phi} $ status Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi\otimes \phi) ^ \dagger $. Om ket Vector $ \ket{\psi} $ är $ \alpha \ket{0} + \beta \ket{1}$, är bra Vector-versionen $ \bra{\psi} = \ket{\psi} ^ \dagger = (\bra{0}\alpha ^ * + \bra{1}\beta ^ *) $.

Anta till exempel att vi vill beräkna sannolikheten för att mäta tillståndet $ \ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ med ett Quantum-program för att mäta tillstånd som ska vara antingen $ \ket{+} $ eller $ \ket{-}$. Sannolikheten att enheten skulle resultera i att statusen är $ \ket{-}$ 

$ $ | \braket{-| \psi} | ^ 2 = \left | \frac{1}{\sqrt{2}} (\bra{0}-\bra{1}) (\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right | ^ 2 = \left |-\frac{3}{5 \ sqrt{2}} + \frac{4}{5 \ sqrt{2}} \right | ^ 2 = \frac{1}{50}. $ $

Det faktum att det negativa tecknet visas i beräkningen av sannolikheten är en manifestning av Quantum interferens, som är en av de mekanismer som har Quantum Computing som ger fördelar jämfört med klassisk data behandling.

## <a name="ketbra-or-outer-product"></a>ketbra eller yttre produkt
Det slutliga objektet som är värt att diskutera i Dirac-notation är *ketbra* eller yttre produkten.  Den yttre produkten representeras i Dirac-notationar som $ \ket{\psi} \bra{\phi} $ och kallas ibland ketbras eftersom Bras och kets sker i motsatt ordning som bromsar.  Den yttre produkten definieras via matrisen multiplikation som $ \ket{\psi} \bra{\phi} = \psi \phi ^ \dagger $ för s i Quantum State $ \psi $ och $ \phi $.  Det enklaste, och utan tvekant vanliga exemplet i den här notationen, är

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ end {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ end {bmatrix}.
$$

Ketbras kallas ofta för projektorer eftersom de projicerar ett Quantum-tillstånd till ett fast värde.  Eftersom dessa åtgärder inte är enhetliga (och inte ens bevarar normen i en Vector) bör det inte vara så överraskning att en Quantum-dator inte kan deterministiskt tillämpa en projektor.  Projektorer gör dock ett snyggt jobb för att beskriva den åtgärd som mätningen har på ett Quantum-tillstånd.  Om vi till exempel mäter ett tillstånd $ \ket{\psi} $ till $0 $ kommer den resulterande omvandlingen att tillstånds upplevelsen som ett resultat av mätningen

  $ $ \ket{\psi} \rightarrow \frac{(\ket{0} \bra{0}) \ket{\psi}}{| \braket{0 | \psi} |} = \ket{0}, $ $

som ett förväntar dig att mäta statusen och hitta den som $ \ket{0}$.  För att upprepa kan sådana projektorer inte tillämpas på ett tillstånd i en Quantum Computer-deterministiskt.  De kan i stället användas slumpmässigt med resultatet $ \ket{0}$ som visas med viss fast sannolikhet.  Sannolikheten för att ett sådant mått lyckas kan skrivas som förväntat värde för Quantum-projektorn i läget

$ $ \bra{\psi} (\ket{0} \bra{0}) \ket{\psi} = | \braket{\psi | 0} | ^ 2, $ $

som illustrerar att projektorer bara ger ett nytt sätt att uttrycka Mät processen.

Om vi i stället bedömer att den första qubit i ett qubit-tillstånd är $1 $ kan vi också beskriva den här processen smidigt med projektorer och Dirac-notation:

$ $ P (\text{First qubit = 1}) = \bra{\psi}\left (\ket{1}\bra{1}\otimes \boldone ^ {\otimes n-1} \right) \ket{\psi}.
$$

Här kan identitets matrisen vara bekväm skriven i Dirac-notation som

$ $ \boldone = \ket{0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}.
$$

För det fall där det finns två-qubits kan projektorn expanderas som 

$ $ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+ \ket{1} \bra{1}) = \ket{10}\bra{10} + \ket{11}\bra{11}.
$$

Vi kan sedan se att detta stämmer överens med diskussionen om Mät sannolikheter för multiqubit-tillstånd med hjälp av Column-Vector notation:

$ $ P (\text{First qubit = 1}) = \psi ^ \dagger (e\_{10}e\_{10}^ \dagger + e\_{11}e\_{11}^ \dagger) \psi = | e\_{10}^ \dagger \psi | ^ 2 + | e\_{11}^ \ Dagger \psi | ^ 2, $ $

som matchar diskussions gruppen för multi-qubit.  Generaliseringen av det här resultatet till qubit-fallet är dock något mer okomplicerat att uttrycka med Dirac-notation än Column-Vector-notation och är helt likvärdig med den tidigare behandlingen.

## <a name="density-operators"></a>Densitets operatörer

En annan användbar operator att uttrycka med Dirac notation är en *Täthets operator*, som ibland även kallas för en *tillstånds operator*.
En densitets operator för en Quantum State-vektor tar formatet $ \rho = \ket{\psi} \bra{\psi} $.
Det här syftet med att representera statusen som en matris, i stället för en Vector, är ofta bekväm eftersom det ger ett bekvämt sätt att representera sannolikhets beräkningar, och det ger också en möjlighet att beskriva både statistisk osäkerhet och Quantum osäkerhet inom samma formalitet.
Allmänna Quantum State-operatörer i stället för vektorer är allmänt förekommande i vissa områden av Quantum Computing, men är inte nödvändiga för att förstå grunderna i fältet.
För den intresserade läsaren rekommenderar vi att du läser en av de referens böcker som finns i [för mer information](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Q # Gate-sekvenser som motsvarar Quantum-tillstånd
En slut punkt som kan höja om Quantum-notation och Q #-programmeringsspråk: vid början av det här dokumentet nämnde vi att steget Quantum är det grundläggande objektet av information i Quantum Computing.  Det kan sedan bli en överraskning som i Q # det inte finns någon form av ett Quantum-tillstånd.  I stället beskrivs alla tillstånd endast av de åtgärder som används för att förbereda dem.  Föregående exempel är en utmärkt illustration av detta.  I stället för att uttrycka en enhetlig överplacering över varje Quantum bit-sträng i ett register kan vi representera resultatet som $H ^ {\otimes n} \ket{0}$.  Den här exponentiellt kortare beskrivningen av tillstånden har inte bara fördelen att vi kan göra en klassisk orsak till den, men det är också en kortfattad beskrivning av de åtgärder som behövs för att spridas via program varu stacken för att implementera algoritmen.  Därför är Q # utformat för att generera grind sekvenser i stället för Quantum-tillstånd. men på en teoretisk nivå är båda perspektiven likvärdiga.

