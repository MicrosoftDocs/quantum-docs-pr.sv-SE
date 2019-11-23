---
title: Pauli mått | Microsoft Docs
description: Pauli mått
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183717"
---
# <a name="pauli-measurements"></a>Pauli mått

I de föregående diskussionerna har vi fokuserat på beräknings bas mått.  Det finns i själva verket andra vanliga mätningar i Quantum Computing som, från ett skriftligt perspektiv, är praktiska att uttrycka när det gäller beräknings bas mått.  Den vanligaste uppsättningen av dessa mått är *Pauli mått*.  I sådana fall är det vanligt att diskutera en Pauli-operatör i allmänhet en operatör som $X, Y, Z $ eller $Z \otimes Z, X\otimes X, X\otimes Y $ och så vidare.  Att diskutera mått i Pauli-operatörer är särskilt vanligt i underfältet för en Quantum-fel korrigering. I Q # följer vi en liknande konvention. Vi förklarar nu den här alternativa vyn över mått.

Innan du går in på Detaljer om hur du kan tänka på en Pauli-mätning, är det bra att tänka på vad som mäter en enskild qubit i en Quantum-dator till Quantum-tillstånd.  Föreställ dig att vi har ett $n $-qubit Quantum-tillstånd; sedan kan du mäta en qubit omedelbart med en gräns på hälften av de möjligheter för $2 ^ n $ som det aktuella läget kan vara i.  Med andra ord mäter måttet Quantum-tillstånd till ett av två halva blank steg.  Vi kan generalisera det sätt vi tycker att mäta för att avspegla detta.

För att kortfattat identifiera dessa under utrymmen behöver vi ett språk för att beskriva dem.  Ett sätt att göra detta är att beskriva två under utrymmen genom att ange dem genom en matris som bara har två unika Eigenvalues, som tas av en konvention som ska vara $ \pm $1.  Det enklaste exemplet på detta är:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

Pauli-$Z $-matrisen har tydligt två eigenvectors $ \ket{0}$ och $ \ket{1}$ med Eigenvalues $ \pm $1.  Om vi mäter qubit och erhåller $ \ket{0}$ finns det i $ + $1-eigenspace (uppsättningen med alla vektorer som bildas av summor av eigenvectors med enbart positiva eller bara negativa Eigenvalues) för operatorn och om vi mäter $ \ket{1}$ finns i $-$1-eigenspace för $Z $.  Den här processen kallas för Pauli-mått som "mäta Pauli $Z $" och är helt likvärdig med att utföra beräknings bas mått.

Naturligtvis kan en matris på $2 \ Times $2 som är en enhetlig transformering av $Z $ också uppfylla det här kriteriet.  Detta är till exempel att vi kan överväga matris $A = U ^ \dagger Z U $, för alla enhetliga matriser $U $, för att ge en matris som definierar de två resultatet av en mätning i $ \pm $1-eigenvectors.  Notationen av Pauli-mätningar refererar till detta genom att identifiera $X, Y, Z $-mått som likvärdiga mått som en kan göra för att få information från en qubit.  De här måtten anges nedan för bekvämlighet.

$ $ \begin{array}{| c | c |} \text{Pauli mått} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{array} $ $

Det vill säga att "mått $Y $" är detsamma som att använda $HS ^ \dagger $ och sedan mäta beräknings grunden, där $S $ är den s.k. fas porten som anges av

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

Det motsvarar också att använda $HS ^ \dagger $ till vektorn med Quantum-tillstånd och sedan mäta $Z $.  Rätt tillstånd kan sedan hittas genom att transformera till beräknings grunden, vilka belopp som ska användas för att tillämpa $SH $ på Vectorn för Quantum-tillstånd.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Q #-resultat klassisk information hämtas från Quantum-tillstånd
I Q # säger vi resultatet, d.v.s. den klassiska information som extraheras från att samverka med staten, är $j $ som finns i uppsättningen $\{0, 1\}$ om resultatet är i fältet $ (-1) ^ j $ eigenspace i Pauli-operatorn.

Mätningar av multi-qubit Pauli-operatörer definieras på samma sätt som de visas på:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {bmatrix}.
$$

Det innebär att behållna produkter av två Pauli-$Z $-operatörer utgör en matris som består av två blank steg som består av $ + $1 och $-$1 Eigenvalues.  Precis som med ett qubit-fall utgör både ett halvt utrymme att hälften av det tillgängliga vektor utrymmet tillhör $ + $1-eigenspace och den återstående halvan till $-$1-eigenspace.  I allmänhet är det enkelt att se från definitionen av beskrivar produkten att alla beskrivare produkter av Pauli-$Z $-operatörer och identiteten lyder på detta.  Exempel:

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ end {bmatrix}.
$$

Precis som tidigare beskriver en enhetlig omvandling av sådana matriser även två halva blank steg med namnet $ \pm $1 Eigenvalues.  Exempel: $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ från den identitet som $Z = HXH $.  På samma sätt som med ett-qubit-fall kan alla qubits Pauli-mått skrivas som $U ^ \dagger (Z\otimes \id) U $ för $4 \ Times $4-matriser $U $.  Vi räknar upp omvandlingarna i följande tabell där vi inför den praktiska växlings porten som byter till qubits $0 $ och $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT}\_{01}$:

$ $ \begin{array}{| c | c |} \text{Pauli mått} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\otimes \boldone\\\\ \boldone \otimes & (\Operatorname{swap} \boldone) \Otimes\\\\ H\otimes \boldone Y & (HS ^ \operatorname{swap} \boldone) \ operatorname {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_{10}(H \ otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{array}\\\\

Här visas porten $ \operatorname{CNOT}\_{10}$ av följande skäl.  Varje Pauli-mått som inte omfattar $ \boldone $-matrisen är lika med upp till en enhetlig till $Z \otimes Z $ med ovanstående orsak.  Eigenvalues för $Z \otimes Z $ är bara beroende av pariteten för qubits som utgör varje beräknings bas vektor och de kontrollerade-inte-åtgärder som visas i den här listan för att beräkna den här pariteten och lagra den i den första biten.  När den första biten mäts kan vi återställa identiteten för det resulterande halva utrymmet som motsvarar att mäta Pauli-operatorn.

En ytterligare anteckning, men det kan vara frestande att anta att mät $Z \otimes Z $ är samma som att mäta $Z \otimes \id $ och sedan $ \id \otimes Z $. Detta antagande skulle vara falskt.  Anledningen är att mät $Z \otimes Z $ projekts Quantum-tillstånd i antingen $ + $1 eller $-$1 eigenstate för dessa operatörer.  Mät $Z \otimes \id $ och sedan $ \id \otimes Z $ projicerar den Quantum State Vector först i ett halvt utrymme på $Z \otimes \id $ och sedan till ett halvt utrymme på $ \id \otimes Z $.  Eftersom det finns fyra beräknings bas vektorer minskar statusen till ett kvartals utrymme och minskar därför den till en enda beräknings bas vektor.


## <a name="correlations-between-qubits"></a>Korrelationer mellan qubits
Ett annat sätt att titta på mät-och \otimes produkter från Paul, till exempel $X \otimes X $ eller $Z Z $ är att dessa mätningar gör det möjligt att titta på information som lagras i korrelationerna mellan de två qubits.  Genom att mäta $X \otimes \id $ kan du titta på information som lagras lokalt i de första qubit.  Även om båda typerna av mätningar är lika värdefulla i Quantum Computing, lyser den tidigare kraften i Quantum Computing. Det visar att den information som du vill lära i Quantum Computing ofta inte lagras i någon enskild qubit utan att i stället lagras lokalt i alla qubits samtidigt, och endast genom att titta på den via en gemensam mätning med $Z \otimes Z $, blir den här informationen uppenbarligen.

Pauli-operatörer som $X \otimes Y \otimes Z \otimes \boldone $ kan också mätas.  Alla sådana behållna produkter av Pauli-operatörer har bara två Eigenvalues $ \pm $1 och båda eigenspaces utgör hälften av utrymmena i hela vektor utrymmet.  De sammanfaller därför med de krav som anges ovan.

I Q # returnerar sådana mätningar $j $ om mätningen ger ett resultat i eigenspace-tecknet $ (-1) ^ j $.  Att ha det som en inbyggd funktion i Q # är användbart eftersom mätning av sådana operatörer kräver långa kedjor av kontrollerade, inte portar och bas omvandlingar för att beskriva den diagonala $U $-grind som krävs för att uttrycka åtgärden som en beskrivare produkt i $Z $ och $ \id $.  Genom att helt enkelt kunna ange att du vill göra en av dessa fördefinierade mätningar behöver du inte oroa dig för att du ska kunna omvandla din grund till att en beräknings bas mätning ger nödvändig information.  Q # hanterar alla nödvändiga transformeringar åt dig automatiskt. Se [Q # biblioteks referens för Pauli-mått](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>No-Kloningsing-satsen
Quantum-informationen är kraftfull.  Det gör det möjligt för oss att göra fantastiska saker som faktor tal exponentiellt snabbare än de bästa kända klassiska algoritmerna, eller att effektivt simulera korrelerade Electron-system som klassiska kräver exponentiell kostnad för att simulera korrekt.  Det finns dock begränsningar för kraften i Quantum Computing.  En sådan begränsning anges av *satsen No-kloningsing*.

No-Kloningsing-satsen är aptly med namnet.
Den tillåter inte kloning av generiska Quantum-tillstånd av en Quantum-dator.
Satsen-beviset är remarkably är enkelt.
Det fullständiga beviset på No-kloning-satsen är lite för tekniskt för vår diskussion här, och bevis på satsen i det fall där Quantum-datorn i fråga inte har några ytterligare Ancilla qubits är inom vår omfattning (Ancilla qubits är qubits används för arbets utrymme under en beräkning och är lätt att använda och hanteras i Q #, se <xref:microsoft.quantum.techniques.qubits>).
För en sådan Quantum-dator måste klonings åtgärden vara en enhetlig matris. Vi tillåter inte mätningar, eftersom det skulle skada det Quantum-tillstånd som vi försöker klona. Den enhetliga matrisen som vi vill ha måste ha den egenskap som $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ för alla tillstånd $ \ket{\psi} $.
Egenskapen linjärt för mat ris multiplikation anger sedan för alla andra Quantum-tillstånd $ \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Phi} \ ket{0}+ \frac{1}{\sqrt{2}} U\ket {\ PSI} \ ket{0}\\\\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ höger) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

Detta ger den grundläggande intuition bakom No-Kloningsing-satsen: alla enheter som kopierar ett okänt Quantum-tillstånd måste orsaka fel på minst några av de tillstånd som den kopierar.  Den nyckel som förutsätter att Klonaren fungerar linjärt i indata-läget kan brytas genom att Ancilla och mätning av Ancilla-qubits används, så att även sådana interaktioner läcker information om systemet genom mätnings statistiken och förhindrar exakt kloning i sådana fall.  För [Mer information](xref:microsoft.quantum.more-information)om ett mer fullständigt korrektur av satsen No-kloningsing finns.

No-kloning-satsen är viktigt för att ge kvalitativ förståelse för Quantum Computing, eftersom om du skulle kunna klona Quantum-tillstånden på ett mycket bra ställe skulle du ges en Magical möjlighet att lära sig från Quantum-tillstånd.  I själva verket kan du bryta mot Heisenbergs vaunted osäkerhets princip.  Alternativt kan du använda en optimal klonare för att ta ett enda exempel från en komplex Quantum-distribution och lära dig allt du kan behöva lära dig mer om distributionen från bara ett exempel.  Detta skulle vara likadant som du vänder på en och samma som när du berättar en vän om resultatet med att de svarar "Ah-fördelningen av dessa mynt måste vara Bernoulli med $p = 0.512643 \ ldots $!"  En sådan instruktion skulle vara icke-sensical eftersom en bit av information (resultatet av huvudena) inte kan ge de många bitar av information som krävs för att koda distributionen utan avsevärd tidigare information.  På samma sätt kan vi inte helt klona ett Quantum-tillstånd på samma sätt som vi inte kan förbereda en ensemble av sådana mynt utan att veta $p $.

Informationen är inte kostnads fri i Quantum Computing.  Varje qubit uppmätta ger en enskild bit av information och No-klonings satsen visar att det inte finns några bakdörr som kan utnyttjas för att komma runt den grundläggande kompromissen mellan information som vunnits om systemet och den störning som har påbörjats.

