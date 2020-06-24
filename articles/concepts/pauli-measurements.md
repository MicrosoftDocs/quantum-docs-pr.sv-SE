---
title: Pauli mått
description: Lär dig hur du arbetar med qubit Pauli mått åtgärder.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269481"
---
# <a name="pauli-measurements"></a>Pauli mått

I de föregående diskussionerna har vi fokuserat på beräknings bas mått.
I själva verket finns det andra vanliga mätningar som sker i den Quantum-bearbetningen som, från ett och samma perspektiv, är praktiska att uttrycka när det gäller beräknings bas mått.
När du arbetar med Q # är den vanligaste typen av mätningar som du kommer att köra i troligen *Pauli mätningar*, som generaliserar beräknings bas mått för att ta med mätningar i andra baser och paritet mellan olika qubits.
I sådana fall är det vanligt att diskutera en Pauli-operatör i allmänhet en operatör som $X, Y, Z $ eller $Z \otimes z, x \otimes x, x \otimes Y $ och så vidare.

> [!TIP]
> I Q # representeras qubit Pauli-operatörer vanligt vis av matriser av typen `Pauli[]` .
> Om du till exempel vill representera $X \otimes Z \otimes Y $ kan du använda matrisen `[PauliX, PauliZ, PauliY]` .

Att diskutera mått i Pauli-operatörer är särskilt vanligt i underfältet för en Quantum-fel korrigering.
I Q # följer vi en liknande konvention. Vi förklarar nu den här alternativa vyn över mått.

Innan du går in på Detaljer om hur du kan tänka på en Pauli-mätning, är det bra att tänka på vad som mäter en enskild qubit i en Quantum-dator till Quantum-tillstånd.
Föreställ dig att vi har $n ett $ qubitt Quantum-tillstånd, och sedan mäter en qubit omedelbart ut hälften av de möjligheter för $2 ^ n $ som tillstånden kan ha.
Med andra ord mäter måttet Quantum-tillstånd till ett av två halva blank steg.
Vi kan generalisera det sätt vi tycker att mäta för att återspegla den här intuition.

För att kortfattat identifiera dessa under utrymmen behöver vi ett språk för att beskriva dem.
Ett sätt att beskriva två under utrymmen är genom att ange dem via en matris som bara har två unika Eigenvalues, som tas av en konvention som är $ \pm 1 $ .
Ett enkelt exempel på hur du kan beskriva under utrymmen på det här sättet är $Z $ :

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .
\end{align}
$$

Genom att läsa de diagonala elementen i Pauli-$Z $ matrisen kan vi se att $Z $ har två eigenvectors, $ \ket{0 } $ och $ \ket{1 } $, med motsvarande Eigenvalues $ \pm 1 $ .
Om vi mäter qubit och hämtar `Zero` (som motsvarar State $ \ket{0 } $) vet vi att situationen för vår qubit är en $ + 1 $ eigenstate av $Z $ operatören.
På samma sätt `One` vet vi att vår qubit är en $-1 $ eigenstate av $Z $ .
Den här processen kallas för Pauli-mått som "mäta Pauli $Z $ " och är helt likvärdig med att utföra en beräknings bas mätning.

En \times $ matris på $2 2 som är en enhetlig transformering av $Z $ uppfyller även det här kriteriet.
Det vill säga att vi också kan använda en matris $A = U ^ \dagger Z U $ , där $U $ är en annan enhetlig matris, för att ge en matris som definierar de två resultatet av en mätning i $ \pm 1- $ eigenvectors.
Pauli-mätningarna hänvisar till den enhetliga motsvarigheten genom att identifiera $X, Y, Z- $ mått som likvärdiga mätningar som en kan göra för att få information från en qubit.
De här måtten anges nedan för bekvämlighet.


|Pauli-mått  |Enhetlig omvandling  |
|-------------------|------------------------|
| $Z$               | $ \boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dagger}$         |

Det innebär att "mått $Y $ " är detsamma som att använda $HS ^ \dagger $ och sedan mäta beräknings grunden, där [`S`](xref:microsoft.quantum.intrinsic.s) är en inbyggd Quantum-åtgärd som ibland kallas "fas grind" och kan simuleras av den enhetliga matrisen

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & i \end{ bmatrix } .
\end{align}
$$

Det motsvarar också att använda $HS ^ \dagger $ i den Quantum State-vektorn och sedan mäta $Z $ , så att följande åtgärd motsvarar `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Rätt tillstånd kan sedan hittas genom att transformera till beräknings grunden, som är ett belopp för att tillämpa $SH på den $ Quantum-delstats vektorn. i ovanstående kodfragment hanteras omvandlingen tillbaka till beräknings basen automatiskt genom användningen av `within … apply` blocket.

I Q # säger vi resultatet---det vill, den klassiska information som extraheras från att interagera med tillstånds---anges av ett `Result` värde $j \in \\ {\Texttt{Zero } , \texttt{One } \\ } $ som anger om resultatet är i $ (-1) ^ j $ eigenspace i Pauli-operatorn uppmätt.


## <a name="multiple-qubit-measurements"></a>Flera qubit-mått

Mätningar av multi-qubit Pauli-operatörer definieras på samma sätt som de visas på:

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ & -1&0&0 \\\\ 0&0 & -1&0 0&0&\\\\ 0&1 \end{bmatrix} .
$$

Det innebär att behållna produkter av två Pauli $Z- $ operatörer utgör en matris som består av två blank steg bestående av $ + 1 $ och $-1 $ Eigenvalues.
Precis som med ett qubit-fall utgör både ett halvt utrymme att hälften av det tillgängliga vektor utrymmet tillhör $ + 1 $ eigenspace och den återstående halvan till $-1- $ eigenspace.
I allmänhet är det enkelt att se från definitionen av den beskrivande produkten som bevarar-produkten av Pauli $Z- $ operatörer och identiteten lyder på detta.
Exempel:

$ $ \begin{align}
    Z-\otimes \boldone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .
\end{align}
$$

Precis som tidigare beskriver en enhetlig omvandling av sådana matriser även två hälften-blank steg med namnet $ \pm 1 $ Eigenvalues.
Till exempel, $X \otimes X = h \otimes h (z \otimes z) h \otimes h $ från den identitet som $Z = HXH $ .
På samma sätt som med ett-qubit-fall kan alla två-qubit-Pauli-mått skrivas som $U ^ \dagger (Z \otimes \id) U $ för $4 \times 4 $ enhetliga matriser $U $ . Vi räknar upp omvandlingarna i följande tabell.

> [!NOTE]
> I tabellen nedan använder vi $ \operatorname{SWAP } $ för att ange matrisen $ $ \begin{align}
>     \operatorname{SWAP } & = \left (\begin{Matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}
> $ $ som används för att simulera den inbyggda åtgärden [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli-mått     |Enhetlig omvandling  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS ^ \dagger \otimes \boldone$ |
| $ \boldone \otimes Z$ | $ \operatorname{SWAP}$ |
| $ \boldone \otimes X$ | $ (H \otimes \boldone) \operatorname{swap}$ |
| $ \boldone \otimes Y$ | $ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } (h \otimes h) $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $ |

Här [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) visas åtgärden av följande skäl.
Varje Pauli-mått som inte omfattar $ \boldone- $ matrisen är lika med upp till en enhetlig till $Z \otimes Z $ av ovanstående orsaker.
Eigenvalues för $Z \otimes Z $ är bara beroende av pariteten för qubits som utgör varje beräknings bas vektor och de kontrollerade-inte-åtgärderna kan beräkna denna paritet och lagra den i den första biten.
När den första biten mäts kan vi återställa identiteten för det resulterande halva utrymmet, vilket motsvarar att mäta Pauli-operatorn.

Ytterligare en anmärkning: det kan vara frestande att anta att mät $Z \otimes z $ är detsamma som att mäta $Z \otimes \mathbb{1 } $ och sedan $ \mathbb{1 } \otimes Z $ . Detta antagande skulle vara falskt.
Orsaken är att mät $Z \otimes Z- $ projekt är Quantum-status i antingen $ + 1- $ eller $-1- $ eigenstate för dessa operatörer.
Mät $Z \otimes \mathbb{1 } $ och sedan $ \Mathbb{1 } \otimes z- $ projekt i den första delen av $Z \otimes \mathbb{1 } $ och sedan till ett halvt utrymme på $ \mathbb{1 } \otimes Z $ . Eftersom det finns fyra beräknings bas vektorer minskar statusen till ett kvartals utrymme och minskar därför den till en enda beräknings bas vektor.

## <a name="correlations-between-qubits"></a>Korrelationer mellan qubits
Ett annat sätt att titta på Mät behållar produkter av Pauli-matriser som $X \otimes X $ eller $Z \otimes Z $ är att dessa mätningar gör det möjligt att titta på information som lagras i korrelationerna mellan de två qubits.
Genom att mäta $X \otimes \id $ kan du titta på information som lagras lokalt i den första qubit.
Även om båda typerna av mätningar är lika värdefulla i Quantum Computing, lyser den tidigare kraften i Quantum Computing.
Det visar att i Quantum Computing är ofta den information som du vill lära inte lagrad i en enskild qubit utan att i stället lagras lokalt i alla qubits samtidigt, och därför bara genom att titta på den via en gemensam mätning (t. ex. $Z \otimes Z $ ) blir den här informationen manifest.

I fel korrigering vill vi till exempel ofta lära sig vilket fel som har inträffat och lära mig ingenting om det tillstånd som vi försöker skydda.
[Kod exemplet bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) visar ett exempel på hur du kan göra det med hjälp av mätningar som $Z \otimes Z \otimes \id $ och $ \id \Otimes z \otimes z $ .
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Godtyckliga Pauli-operatörer som $X \otimes Y \Otimes Z \otimes \boldone $ kan också mätas.
Alla sådana behållna produkter av Pauli-operatörer har bara två Eigenvalues $ \pm 1 $ och båda eigenspaces utgör hälften av utrymmena i hela vektor utrymmet.
De sammanfaller därför med de krav som anges ovan.

I Q # returnerar sådana mätningar $j $ om mätningen ger ett resultat i eigenspace-tecknet $ (-1) ^ j $ .
Att ha Pauli mätningar som en inbyggd funktion i Q # är till hjälp eftersom man kan mäta sådana operatörer som kräver långa kedjor av kontrollerade, icke-portar och bas omvandlingar för att beskriva den diagonala $U $ grind som krävs för att uttrycka åtgärden som en beskrivare produkt i $Z $ och $ \id $ . Genom att kunna ange att du vill göra en av dessa fördefinierade mätningar behöver du inte oroa dig för att du ska kunna omvandla din grund till att en beräknings bas mätning ger nödvändig information.
Q # hanterar alla nödvändiga transformeringar åt dig automatiskt.
Mer information finns i [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) åtgärderna och.

## <a name="the-no-cloning-theorem"></a>No-Kloningsing-satsen

Quantum-informationen är kraftfull.
Det gör det möjligt för oss att göra fantastiska saker som faktor tal exponentiellt snabbare än de bästa kända klassiska algoritmerna, eller att effektivt simulera korrelerade Electron-system som klassiska kräver exponentiell kostnad för att simulera korrekt.
Det finns dock begränsningar för kraften i Quantum Computing.
En sådan begränsning anges av *satsen No-kloningsing*.

No-Kloningsing-satsen är aptly med namnet.
Den tillåter inte kloning av generiska Quantum-tillstånd av en Quantum-dator.
Satsen-beviset är remarkably är enkelt.
Det fullständiga beviset på No-kloning-satsen är lite för tekniskt för vår diskussion här, men beviset för att det inte finns några ytterligare hjälp qubits finns inom vår omfattning (hjälp qubits är qubits som används för arbets utrymme under en beräkning och är lätt att använda och hanteras i Q #, se [lånade qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

För en sådan Quantum-dator måste klonings åtgärden beskrivas av en enhetlig matris.
Vi tillåter inte mätningar, eftersom det skulle skada det Quantum-tillstånd som vi försöker klona.
För att simulera klonings åtgärden vill vi att den enhetliga matrisen som används för att ha den egenskap som $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}
$ $ för alla tillstånd $ \ket { \psi } $.
Egenskapen linjärt för mat ris multiplikation innebär sedan att för alla andra Quantum-tillstånd $ \ket { \phi } $,

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}
        \right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).
\end{align}
$$

Detta ger den grundläggande intuition bakom No-Kloningsing-satsen: alla enheter som kopierar ett okänt Quantum-tillstånd måste orsaka fel på minst några av de tillstånd som den kopierar.
Den nyckel som förutsätter att Klonaren fungerar linjärt i indata-läget kan brytas genom addition och mätning av hjälp-qubits, men sådana interaktioner läcker också information om systemet genom mätnings statistiken och förhindrar exakt kloning i sådana fall.
För [Mer information](xref:microsoft.quantum.more-information)om ett mer fullständigt korrektur av satsen No-kloningsing finns.

No-kloning-satsen är viktigt för att ge kvalitativ förståelse för Quantum Computing, eftersom om du skulle kunna klona Quantum-tillstånden på ett mycket bra ställe skulle du ges en Magical möjlighet att lära sig från Quantum-tillstånd.
I själva verket kan du bryta mot Heisenbergs vaunted osäkerhets princip.
Alternativt kan du använda en optimal klonare för att ta ett enda exempel från en komplex Quantum-distribution och lära dig allt du kan behöva lära dig mer om distributionen från bara ett exempel.
Detta skulle vara precis som du vänder på en och samma som när du berättar en vän om resultatet med att de svarar "Ah-fördelningen av dessa mynt måste vara Bernoulli med $p = 0.512643 \ ldots $ !"  En sådan instruktion skulle vara icke-sensical eftersom en bit av information (resultatet av huvudena) inte kan ge de många bitar av information som krävs för att koda distributionen utan avsevärd tidigare information.
På samma sätt kan vi inte helt klona ett Quantum-tillstånd på samma sätt som vi inte kan förbereda en ensemble av sådana mynt utan att känna till $p $ .

Informationen är inte kostnads fri i Quantum Computing.
Varje qubit uppmätta ger en enskild bit av information och No-klonings satsen visar att det inte finns några bakdörr som kan utnyttjas för att komma runt den grundläggande kompromissen mellan information som vunnits om systemet och den störning som har påbörjats.
