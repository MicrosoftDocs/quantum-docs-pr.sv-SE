---
title: Beskrivning av Pauli mått: Lär dig hur du arbetar med en och flera qubit Pauli mått åtgärder.
författare: bradben UID: Microsoft. Quantum. Concepts. Pauli MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: artikeln No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="pauli-measurements"></a>Pauli mått

I de föregående diskussionerna har vi fokuserat på beräknings bas mått.
I själva verket finns det andra vanliga mätningar som sker i den Quantum-bearbetningen som, från ett och samma perspektiv, är praktiska att uttrycka när det gäller beräknings bas mått.
När du arbetar med Q# , är den vanligaste typen av mätningar som du kommer att köra i troligen *Pauli mätningar*, som generaliserar beräknings bas mått för att ta med mätningar i andra baser och paritet mellan olika qubits.
I sådana fall är det vanligt att diskutera en Pauli-operatör i allmänhet en operator som $ X, Y, z $ eller $ z \otimes z, x \otimes x, x \otimes Y $ och så vidare.

> [!TIP]
> I Q# , representeras qubit Pauli-operatörer vanligt vis av matriser av typen `Pauli[]` .
> Om du till exempel vill representera $ X \otimes Z \otimes Y $ kan du använda matrisen `[PauliX, PauliZ, PauliY]` .

Att diskutera mått i Pauli-operatörer är särskilt vanligt i underfältet för en Quantum-fel korrigering.
I Q# följer vi en liknande konvention. vi förklarar nu den här alternativa vyn av mått.

Innan du går in på Detaljer om hur du kan tänka på en Pauli-mätning, är det bra att tänka på vad som mäter en enskild qubit i en Quantum-dator till Quantum-tillstånd.
Tänk dig att vi har ett $ n $ -qubit Quantum-tillstånd, och sedan mäter du en qubit omedelbart ut hälften av de $ 2 ^ n- $ möjligheter som tillstånden kan ha.
Med andra ord mäter måttet Quantum-tillstånd till ett av två halva blank steg.
Vi kan generalisera det sätt vi tycker att mäta för att återspegla den här intuition.

För att kortfattat identifiera dessa under utrymmen behöver vi ett språk för att beskriva dem.
Ett sätt att beskriva två under utrymmen är genom att ange dem via en matris som bara har två unika Eigenvalues, som tas av en konvention som ska vara $ \pm 1 $ .
Ett enkelt exempel på hur du kan beskriva under utrymmen på det här sättet är att tänka på $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ & -1 \end{bmatrix} .
\end{align}
$$

Genom att läsa de diagonala elementen i Pauli- $ Z- $ matrisen kan vi se att $ Z $ har två eigenvectors, $ \ket { 0 } $ och $ \ket { 1 } $ , med motsvarande Eigenvalues $ \pm 1 $ .
Om vi mäter qubit och hämtar `Zero` (som motsvarar tillstånd $ \ket { 0 } $ ) vet vi att situationen för vår qubit är a $ + 1 $ eigenstate av $ Z- $ operatorn.
På samma sätt `One` vet vi att vår qubit-stat är en $ -1 $ eigenstate av $ Z $ . Den här processen kallas för Pauli-mått som "mäta Pauli $ Z $ " och är helt likvärdig med att utföra en beräknings bas mätning.

$2 \times 2- $ matriser som är en enhetlig omvandling av $ Z $ uppfyller också det här kriteriet.
Det innebär att vi också kan använda en matris $ a = u ^ \dagger Z u $ , där $ u $ är en annan enhetlig matris, för att ge en matris som definierar de två resultatet av en mätning i dess $ \pm 1- $ eigenvectors.
Pauli-mätningarna hänvisar till den enhetliga motsvarigheten genom $ att identifiera X, Y, Z- $ mått som likvärdiga mätningar som en kan göra för att få information från en qubit.
De här måtten anges nedan för bekvämlighet.


|Pauli mått-  | transformering  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $HS ^               {\dagger}$         |

Med det här språket är "mått $ Y $ " detsamma som att tillämpa $ HS ^ \dagger $ och sedan mäta beräknings grunden, där [`S`](xref:microsoft.quantum.intrinsic.s) är en inbyggd Quantum-åtgärd som ibland kallas "fas grind" och kan simuleras av den enhetliga matrisen

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

Det är också detsamma som att tillämpa $ HS ^ \dagger $ på Vectorn för Quantum-tillstånd och sedan mäta $ Z $ , så att följande åtgärd motsvarar `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Rätt tillstånd kan sedan hittas genom att omvandla tillbaka till beräknings grunden, vilka belopp som ska tillämpas på den $ Quantum- $ delstats vektorn. i ovanstående kodfragment hanteras omvandlingen tillbaka till beräknings basen automatiskt av användningen av `within … apply` blocket.

I Q# säger vi resultatet---det vill, den klassiska information som extraheras från att samverka med tillstånds---anges av ett `Result` värde $ j \in \\ { \texttt { noll } , \texttt { ett } \\ } $ som anger om resultatet är i $ (-1) ^ j $ eigenspace i Pauli-operatorn uppmätt.


## <a name="multiple-qubit-measurements"></a>Flera qubit-mått

Mätningar av multi-qubit Pauli-operatörer definieras på samma sätt som de visas på:

$$
Z z 1 0 0-1 0-1 0 – 1 0 0 0 0 \otimes = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & 1 \end{bmatrix} .
$$

Det innebär att behållna produkter av två Pauli- $ ö- $ operatörer utgör en matris som består av två blank steg bestående av $ + 1 $ och $ -1 $ Eigenvalues.
Precis som med ett qubit-fall utgör både ett halvt utrymme att hälften av det tillgängliga vektor utrymmet tillhör $ + 1 $ eigenspace och den återstående halvan till $ -1- $ eigenspace.
I allmänhet är det enkelt att se från definitionen av den beskrivande produkten som alla beskrivare produkter av Pauli- $ ö- $ operatörer och identiteten följer.
Exempel:

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 &  0 &  0 &  0 \\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 & & -1 \end{bmatrix} .
\end{align}
$$

Precis som tidigare beskriver en enhetlig omvandling av sådana matriser även två hälften-blank steg som är märkta med $ \pm 1 $ Eigenvalues.
Till exempel $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  från den identitet som Z- $ = HXH $ .
På samma sätt som med ett-qubit-fall kan alla qubits Pauli-mått skrivas som $ u ^ \dagger (Z \otimes \id ) u $ för $ 4 4 höga \times $ matriser $ U $ . Vi räknar upp omvandlingarna i följande tabell.

> [!NOTE]
>I tabellen nedan använder vi $ \operatorname { swap } $ för att ange matrisen >$$
> \begin{align}
>     \operatorname{Växla } &=
>     \left( \begin { matris}
>         1 & 0 & 0 & 0 \\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { matris } \right ) >     \end{align}
> $$
> används för att simulera den inbyggda åtgärden [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli mått-     | transformering  |
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes Z- $ | $ \operatorname { växling } $|
|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { växling } $|
|$\boldone \otimes Y $ | $ - \dagger \otimes \boldone \operatorname { växling } (HS ^ $ )|
|$Z \otimes Z- $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { } \_ { -CNOT 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes Y $ | $ \operatorname { } \_ { -CNOT 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

Här [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) visas åtgärden av följande skäl.
Varje Pauli-mått som inte omfattar $ \boldone $ matrisen motsvarar en enhetlig till $ z \otimes z $ av ovanstående orsaker.
Eigenvalues av $ z \otimes z $ är bara beroende av pariteten för qubits som utgör varje beräknings bas vektor och de kontrollerade-inte-åtgärderna kan beräkna denna paritet och lagra den i den första biten.
När den första biten mäts kan vi återställa identiteten för det resulterande halva utrymmet, vilket motsvarar att mäta Pauli-operatorn.

Ytterligare en anmärkning: det kan vara frestande att anta att måttet $ z \otimes z $ är detsamma som att mäta $ z \otimes \mathbb { 1 } $ och sedan $ \mathbb { 1 } \otimes Z $ . Detta antagande skulle vara falskt.
Orsaken är att $ z z- \otimes $ projekt har ett Quantum-tillstånd i antingen $ eigenstate + 1 $ eller $ -1 $ för dessa operatörer.
Mätning $ \otimes \mathbb { av z 1 } $ och sedan $ \mathbb { 1 } \otimes z- $ projekt är den Quantum-tillstånds vektorn först i ett halvt utrymme på $ z \otimes \mathbb { 1 } $ och sedan till ett halvt utrymme på $ \mathbb { 1 } \otimes Z $ . Eftersom det finns fyra beräknings bas vektorer minskar statusen till ett kvartals utrymme och minskar därför den till en enda beräknings bas vektor.

## <a name="correlations-between-qubits"></a>Korrelationer mellan qubits
Ett annat sätt att titta på mätnings behållar produkter av Pauli-matriser som $ X \otimes x $ eller $ z \otimes z $ är att dessa mätningar gör att du kan titta på information som lagras i korrelationerna mellan de två qubits.
Med måttet $ X \otimes \id $ kan du titta på information som lagras lokalt i den första qubit.
Även om båda typerna av mätningar är lika värdefulla i Quantum Computing, lyser den tidigare kraften i Quantum Computing.
Det visar att i Quantum Computing är ofta den information som du vill lära inte lagrad i en enskild qubit utan att i stället lagras lokalt i alla qubits samtidigt, och därför bara genom att titta på den via en gemensam mätning (t. ex. $ z \otimes z $ ) blir den här informationen manifest.

I fel korrigering vill vi till exempel ofta lära sig vilket fel som har inträffat och lära mig ingenting om det tillstånd som vi försöker skydda.
[Kod exemplet bit-flip](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) visar ett exempel på hur du kan göra det med hjälp av mätningar som $ z \otimes z \otimes \id $ och $ \id \otimes z \otimes z $ . < ! --Att göra: ändra detta till en länk till exempel webbläsaren så snart kod exemplet för bit-Flip är på skiva. -->

Godtyckliga Pauli-operatorer som $ X \otimes Y \otimes Z \otimes \boldone $ kan också mätas.
Alla sådana Beslags produkter av Pauli-operatörer har bara två Eigenvalues- $ \pm 1 $ och båda eigenspaces utgörs av halva utrymmet i hela vektor utrymmet.
De sammanfaller därför med de krav som anges ovan.

I Q# kan sådana mätningar returnera $ j $ om mätningen ger ett resultat i eigenspace $ (-1) ^ j $ .
Att ha Pauli mätningar som en inbyggd funktion i Q# är till hjälp eftersom du kan mäta sådana operatörer som kräver långa kedjor av kontrollerade, icke-portar och bas omvandlingar för att beskriva hur mycket $ U-grind som $ krävs för att uttrycka åtgärden som en beskrivare produkt i $ Z $ och $ \id $ .
Genom att kunna ange att du vill göra en av dessa fördefinierade mätningar behöver du inte oroa dig för att du ska kunna omvandla din grund till att en beräknings bas mätning ger nödvändig information.
Q# hanterar alla transformeringar som behövs automatiskt.
Mer information finns i [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) åtgärderna och.

## <a name="the-no-cloning-theorem"></a>No-Kloningsing-satsen

Quantum-informationen är kraftfull.
Det gör det möjligt för oss att göra fantastiska saker som faktor tal exponentiellt snabbare än de bästa kända klassiska algoritmerna, eller att effektivt simulera korrelerade Electron-system som klassiska kräver exponentiell kostnad för att simulera korrekt.
Det finns dock begränsningar för kraften i Quantum Computing.
En sådan begränsning anges av *satsen No-kloningsing*.

No-Kloningsing-satsen är aptly med namnet.
Den tillåter inte kloning av generiska Quantum-tillstånd av en Quantum-dator.
Satsen-beviset är remarkably är enkelt.
Det fullständiga beviset på No-kloning-satsen är lite för tekniskt för vår diskussion här, men beviset för att det inte finns några ytterligare hjälp qubits inom vår omfattning (hjälp qubits är qubits som används för arbets utrymme under en beräkning och är lätt att använda och hanteras i Q# , se [lånade qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

För en sådan Quantum-dator måste klonings åtgärden beskrivas av en enhetlig matris.
Vi tillåter inte mätningar, eftersom det skulle skada det Quantum-tillstånd som vi försöker klona.
För att simulera klonings åtgärden vill vi att den enhetliga matrisen som används för att ha den egenskap som $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
för alla tillstånd $ \ket { \psi } $ .
Egenskapen linearitet för mat ris multiplikation anger sedan att för andra Quantum $ \ket { \phi } $ -tillstånd.

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Detta ger den grundläggande intuition bakom No-Kloningsing-satsen: alla enheter som kopierar ett okänt Quantum-tillstånd måste orsaka fel på minst några av de tillstånd som den kopierar.
Den nyckel som förutsätter att Klonaren fungerar linjärt i indata-läget kan brytas genom addition och mätning av hjälp-qubits, men sådana interaktioner läcker också information om systemet genom mätnings statistiken och förhindrar exakt kloning i sådana fall.
För [Mer information](xref:microsoft.quantum.more-information)om ett mer fullständigt korrektur av satsen No-kloningsing finns.

No-kloning-satsen är viktigt för att ge kvalitativ förståelse för Quantum Computing, eftersom om du skulle kunna klona Quantum-tillstånden på ett mycket bra ställe skulle du ges en Magical möjlighet att lära sig från Quantum-tillstånd.
I själva verket kan du bryta mot Heisenbergs vaunted osäkerhets princip.
Alternativt kan du använda en optimal klonare för att ta ett enda exempel från en komplex Quantum-distribution och lära dig allt du kan behöva lära dig mer om distributionen från bara ett exempel.
Detta skulle vara precis som du vänder på en och samma som när du säger upp en vän om resultatet med att de svarar "Ah-fördelningen av dessa mynt måste vara Bernoulli med $ p = 0.512643 \ ldots $ !"  En sådan instruktion skulle vara icke-sensical eftersom en bit av information (resultatet av huvudena) inte kan ge de många bitar av information som krävs för att koda distributionen utan avsevärd tidigare information.
På samma sätt kan vi inte helt klona ett Quantum-tillstånd på samma sätt som vi inte kan förbereda en ensemble av sådana mynt utan att veta $ p $ .

Informationen är inte kostnads fri i Quantum Computing.
Varje qubit uppmätta ger en enskild bit av information och No-klonings satsen visar att det inte finns några bakdörr som kan utnyttjas för att komma runt den grundläggande kompromissen mellan information som vunnits om systemet och den störning som har påbörjats.
