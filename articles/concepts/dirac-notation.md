---
title: Dirac notation-Beskrivning: Lär dig hur du använder Dirac-notation för att representera Quantum-tillstånd och för att simulera Quantum-åtgärder.
författare: QuantumWriter UID: Microsoft. Quantum. Concepts. Dirac MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: artikeln No-Loc:
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

# <a name="dirac-notation"></a>Dirac-notation

Även om kolumn vektor notation är allmänt förekommande i linjär algebra, är det ofta besvärligt i Quantum Computing, särskilt när du hanterar flera qubits.  När vi till exempel definierar $ \psi $ som en Vector är det inte uttryckligen uppenbart om det $ \psi $ är en rad eller en kolumn vektor.  Om $ \phi $ och $ \psi $ är vektorer är det jämnt oklart om det $ \phi \psi $ är jämnt definierat eftersom formerna i $ \phi $ och $ \psi $ kan vara otydliga i kontexten.  Utöver tvetydigheten om figurerna i vektorer, uttrycker även enkla vektorer med den linjära Algebraic-notation som introducerades tidigare kan vara mycket besvärlig. Om vi till exempel vill beskriva ett $ n $ -qubit-tillstånd där varje qubit tar värdet $ 0 $ , skulle vi formellt uttrycka status som 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} . $$  

Självklart är det opraktiskt att utvärdera den här behållar produkten eftersom vektorn ligger i ett exponentiellt stort utrymme och så att den här notationen i själva verket är den bästa beskrivningen av det tillstånd som kan ges med hjälp av föregående notation.  

[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) löser dessa problem genom att presentera ett nytt språk som passar de exakta behoven för Quantum Mechanics.  Därför rekommenderar vi läsaren inte att se exemplen i det här avsnittet som en fast Skriv åtgärd för att beskriva Quantum-tillstånd, men för att uppmuntra läsaren att se dessa som förslag som kan användas för att uttrycka ett koncist förslag.

Det finns två typer av vektorer i Dirac-notation: *bra* Vector och *ket* Vector, så de heter eftersom när de placeras tillsammans bildar de ett *bromsat* eller en inre produkt.  Om $ \psi $ är en kolumn vektor kan vi skriva den i Dirac-notation som $ \ket { \psi } $ , där $ \ket { \cdot } $ anger att det är en vektor kolumn vektor, d.v.s. en *ket* Vector.  På samma sätt $ \psi ^ \dagger $ uttrycks rad vektorn som $ \bra { \psi } $ . Med andra ord $ \psi ^ \dagger $ erhålls du genom att använda en inmatning komplex conjugation till elementen i Transponeringen av $ \psi $ . Bra-ket-notationen innebär direkt att $ \braket { \psi | \psi } $ är den inre produkten av Vector $ \psi $ , som är med definition $ 1 $ .  

Mer allmänt, om $ \psi $ och $ \phi $ är Quantum State-vektorer är deras inre produkt, $ \braket { \phi | \psi } $ vilket innebär att sannolikheten för att mäta status $ \ket { \psi } $ $ \ket { \phi } $ är $ | \braket { \phi | \psi } | ^ 2 $ .  

Följande konvention används för att beskriva de Quantum-tillstånd som kodar värdena för noll och ett (qubit beräknings bas tillstånd):

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ,\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exempel: som representerar Hadamard-åtgärden med Dirac-notation

Följande notation används ofta för att beskriva de tillstånd som uppstår vid tillämpning av Hadamard-porten på $ \ket { 0 } $ och $ \ket { 1 } $ (som motsvarar enhets vektorerna i $ x $ $ -och-x- $ instruktionerna på Bloch-sfären):

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ \end{bmatrix} = H \ket { 0 } = \ket { + } ,\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ – 1 \end{bmatrix} = H \ket { 1 } = \ket { - } .
$$

Dessa tillstånd kan också utökas med Dirac-notation som summor på $ \ket { 0 } $ och $ \ket { 1 } $ :

$$
\ket{+}= \frac{ 1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } ), \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } ).
$$

### <a name="computational-basis-vectors"></a>Beräknings bas vektorer
Detta visar varför dessa tillstånd ofta kallas för *beräknings grund*: varje Quantum-tillstånd kan alltid uttryckas som summor av beräknings bas vektorer och sådana summor är lätt att uttryckas med Dirac notation.  Omvänt är också sant i att tillstånden $ \ket { + } $ och $ \ket { - } $ även utgör grunden för Quantum-tillstånd.  Du kan se detta från det faktum att

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ), \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  -  \ket { - } ).
$$

Som ett exempel på Dirac-notation bör du överväga bromsen $ \braket { 0 | 1 } $ , vilket är den inre produkten mellan $ 0 $ och $ 1 $ .  Den kan skrivas som 

$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} \\\\ 1 0 \end{bmatrix} = .$$

Det betyder att $ \ket { 0 } $ och $ \ket { 1 } $ är rätvinkliga vektorer, vilket innebär att $ \braket { 0 | 1 } = \braket { 1 0 | } = 0 $ .  Även genom definition $ \braket { 0 | 0 } = \braket { 1 | 1 } = $ , vilket innebär att de två beräknings bas vektorerna också kan kallas *orthonormal*.
Dessa orthonormal-egenskaper är användbara i följande exempel. Om vi har status $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0, } $ sedan $ \braket { 1 | 0 } = 0, $ är sannolikheten för att mäta $ 1 $  

$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } .$$ 

### <a name="tensor-product-notation"></a>Betecknings produkt notation
Dirac notation innehåller också en produkt struktur med implicita beteckningar i den.  Detta är viktigt eftersom i Quantum Computing är den tillstånds vektor som beskrivs av två korrelerade Quantum-register beskrivare i de två tillstånds vektorerna.  En kortfattad beskrivning av produkt strukturen för beskrivare eller brist på detta är viktigt om du vill förklara en Quantum-beräkning.  Produkt strukturen för beskrivare innebär att vi kan skriva $ \psi \otimes \phi $ för två Quantum-tillstånds vektorer $ \phi $ och $ \psi $ $ \ket { \psi } \ket { \phi } $ , ibland uttryckligen skrivna som $ \ket { \psi } \otimes \ket { \phi } $ , trots att konventions skrivningen $ \otimes $ mellan vektorerna är onödigt.  Till exempel anges tillstånd med två qubits som initieras till noll för tillstånd av

$$
\begin{bmatrix}1 0 0 1 0 0 0 0 \\\\ \\\\ \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } .
$$

På samma sätt representerar State $ \ket { p } $ för integer $ p $ ett Quantum-tillstånd som kodar i binär representation av heltalet $ p $ .  Om vi till exempel vill uttrycka siffran $ 5 $ med en osignerad binär kodning kan vi även uttrycka det som

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } .
$$

I det här Notations $ \ket { värdet 0 } $ behöver inte referera till ett qubit-tillstånd utan i stället för ett *qubit-register* som lagrar en binär kodning på $ 0 $ .  Skillnaderna mellan dessa två format är vanligt vis tydliga från kontexten.  Denna konvention är användbar för att förenkla det första exemplet som kan skrivas på något av följande sätt:

$$
\begin{bmatrix}1 \\\\ 0 1 0 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exempel: beskriva superposition med Dirac-notation
Ett annat exempel på hur du kan använda Dirac notation för att beskriva ett Quantum-tillstånd, Tänk på följande sätt för att skriva ett Quantum-tillstånd som är lika överplacerat över varje möjlig bit sträng med längden $ n$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } .
$$

Här kan du undra varför summan går från $ 0 $ till $ 2 ^ { n } -1 $ för $ n $ bitar.  Först Observera att det finns $ två ^ { n } $ olika konfigurationer som $ n $ bitar kan ta.  Du kan se detta genom att notera att en bit kan ta $ 2 $ värden, men två bitar kan ta $ 4 $ värden och så vidare. I allmänhet innebär detta att det finns $ två ^ n $ olika möjliga bit strängar, men det största värdet som är kodat i någon av dem $ 1 \cdots 1 = 2 ^ n-1 $ och därmed är den övre gränsen för summan.
I det här exemplet har vi i det här exemplet inte använt $ \ket { + } ^ { \otimes n } = \ket { + } $ i analogt till $ \ket { 0 } ^ { \otimes n } = \ket { 0 } $ eftersom den här Notations konventionen vanligt vis är reserverad för beräknings grunden med varje qubit initierad till noll.  Även om en sådan konvention skulle vara lämpliga i det här fallet, används den inte i den Quantum Computing-dokumentationen.

### <a name="expressing-linearity-with-dirac-notation"></a>Uttrycka linjärhet med Dirac-notation
En annan bra funktion i Dirac notation är att den är linjär.  Om vi vill skriva för alla fyra Quantum-delstats vektorer 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ) \otimes ( \gamma \ket { \chi }  +  \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } .$$

Det innebär att du kan distribuera handnotationen för beskrivare i Dirac-notation så att du kan dra på att ta med sig produkter mellan delstats vektorer som ser ut precis som vanlig multiplikation.

Bra Vectors följer en liknande konvention till ket-vektorer.  Vektorn $ \bra { \psi } \bra { \phi } $ motsvarar exempelvis tillstånds vektorn $ \psi ^ \dagger \otimes \phi ^ \dagger = ( \psi \otimes \phi ) ^ \dagger $ . Om ket Vector $ \ket { \psi } $ är $ \alpha \ket { 0 }  +  \beta \ket { 1, } $ är bra Vector-versionen av Vectorn $ \bra { \psi } = \ket { \psi } ^ \dagger = ( \bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ *) $ .

Anta till exempel att vi vill beräkna sannolikheten för att mäta status $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } $ med ett Quantum-program för att mäta tillstånd som antingen $ \ket { + } $ eller $ \ket { - } $ . Sannolikheten att enheten skulle resultera i att $ statusen är \ket { - } $ 

$$|\braket{- |\psi}| ^ 2 = \left | \frac { 1 } { \sqrt { 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } ) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } .$$

Det faktum att det negativa tecknet visas i beräkningen av sannolikheten är en manifestning av Quantum interferens, som är en av de mekanismer som har Quantum Computing som ger fördelar jämfört med klassisk data behandling.

## <a name="ketbra-or-outer-product"></a>ketbra eller yttre produkt
Det slutliga objektet som är värt att diskutera i Dirac-notation är *ketbra* eller yttre produkten.  Den yttre produkten representeras i Dirac-format $ \ket { \psi } \bra { \phi } $ och kallas ibland ketbras eftersom Bras och kets inträffar i motsatt ordning som bromsar.  Den yttre produkten definieras via matrisen multiplikation som $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ för vektorer med Quantum-tillstånd $ \psi $ och $ \phi $ .  Det enklaste, och utan tvekant vanliga exemplet i den här notationen, är

$$
\ket{0 0 1 0 1 0 1 1 0 0 1 0 1 0 } \bra { } = \begin{bmatrix} \\\\ \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & \end{bmatrix} \qquad \ket { } \bra { } = \begin{bmatrix} \\\\ \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & 1 \end{bmatrix} .
$$

Ketbras kallas ofta för projektorer eftersom de projicerar ett Quantum-tillstånd till ett fast värde.  Eftersom dessa åtgärder inte är enhetliga (och inte ens bevarar normen i en Vector) bör det inte vara så överraskning att en Quantum-dator inte kan deterministiskt tillämpa en projektor.  Projektorer gör dock ett snyggt jobb för att beskriva den åtgärd som mätningen har på ett Quantum-tillstånd.  Om vi till exempel mäter ett tillstånd som $ \ket { \psi } $ 0 blir $ $ den resulterande omvandlingen som tillstånds upplevelsen har till följd av mätningen

  $$\ket{\psi}\right \frac pil { ( \ket { 0 } \bra { 0 } ) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ,$$

som ett förväntar dig att mäta statusen och hitta den som $ \ket { 0 } $ .  För att upprepa kan sådana projektorer inte tillämpas på ett tillstånd i en Quantum Computer-deterministiskt.  De kan i stället användas slumpmässigt med resultatet $ \ket { 0 } $ som visas med fast sannolikhet.  Sannolikheten för att ett sådant mått lyckas kan skrivas som förväntat värde för Quantum-projektorn i läget

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2,$$

som illustrerar att projektorer bara ger ett nytt sätt att uttrycka Mät processen.

Om vi i stället bedömer att den första qubit i ett qubit-tillstånd är $ 1 $ , kan vi också beskriva den här processen smidigt med hjälp av projektorer och Dirac-notation:

$$
P ( \text { första qubit = 1 } ) = \bra { \psi } \left ( \ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } .
$$

Här kan identitets matrisen vara bekväm skriven i Dirac-notation som

$$
\boldone= \ket{ 0 } \bra { 0 1 1 0 } + \ket { } \bra { } = \begin{bmatrix} & \\\\ & 1 \end{bmatrix} .
$$

För det fall där det finns två-qubits kan projektorn expanderas som 

$$
\ket{1 1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes ( \ket { 0 } \bra { 0 } + \ket { 1 } \bra { } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } .
$$

Vi kan sedan se att detta stämmer överens med diskussionen om Mät sannolikheter för multiqubit-tillstånd med hjälp av Column-Vector notation:

$$
P ( \text { första qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger ) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2,$$

som matchar diskussions gruppen för multi-qubit.  Generaliseringen av det här resultatet till qubit-fallet är dock något mer okomplicerat att uttrycka med Dirac-notation än Column-Vector-notation och är helt likvärdig med den tidigare behandlingen.

## <a name="density-operators"></a>Densitets operatörer

En annan användbar operator att uttrycka med Dirac notation är en *Täthets operator*, som ibland även kallas för en *tillstånds operator*.
En densitets operator för en Quantum State-vektor tar formatet $ \rho = \ket { \psi } \bra { \psi } $ .
Det här syftet med att representera statusen som en matris, i stället för en Vector, är ofta praktisk eftersom det ger ett bekvämt sätt att representera sannolikhets beräkningar, och det ger också en möjlighet att beskriva både statistisk osäkerhet och Quantum osäkerhet inom samma formalitet.
Allmänna Quantum State-operatörer i stället för vektorer är allmänt förekommande i vissa områden av Quantum Computing, men är inte nödvändiga för att förstå grunderna i fältet.
För den intresserade läsaren rekommenderar vi att du läser en av de referens böcker som finns i [för mer information](xref:microsoft.quantum.more-information).

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# grindar som motsvarar Quantum-tillstånd
En slut punkt som kan höja om Quantum-notation och Q# programmeringsspråk: vid början av det här dokumentet nämnde vi att steget Quantum är det grundläggande objektet av information i Quantum Computing.  Det kan sedan bli en överraskning om Q# det inte finns någon begreppet Quantum-tillstånd.  I stället beskrivs alla tillstånd endast av de åtgärder som används för att förbereda dem.  Föregående exempel är en utmärkt illustration av detta.  I stället för att uttrycka en enhetlig överplacering över varje Quantum bit-sträng i ett register kan vi representera resultatet som $ H ^ { \otimes n } \ket { 0 } $ .  Den här exponentiellt kortare beskrivningen av tillstånden har inte bara fördelen att vi kan göra en klassisk orsak till den, men det är också en kortfattad beskrivning av de åtgärder som behövs för att spridas via program varu stacken för att implementera algoritmen.  Därför Q# är det utformat att generera grind sekvenser i stället för Quantum-tillstånd, men på en teoretisk nivå är båda perspektiven likvärdiga.
