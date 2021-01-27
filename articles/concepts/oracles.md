---
title: Quantum Oracle-Beskrivning: Lär dig hur du arbetar med och definierar Quantum Oracles, svarta Box-åtgärder som används som inmatade i en annan algoritm.
författare: cgranade-UID: Microsoft. Quantum. Concepts. Oracles MS. author: chgranad MS. Date: 07/11/2018 MS. topic: konceptuell No-Loc:
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
# <a name="quantum-oracles"></a>Quantum Oracle

En Oracle $ O $ är en "svart box"-åtgärd som används som inmatad till en annan algoritm.
Ofta definieras sådana åtgärder med hjälp av en klassisk funktion $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ som tar en $ n $ -bitars binär indata och producerar en $ m $ -bitars binär utdata.
Det gör du genom att tänka på ett visst binärt $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .
Vi kan märka qubit tillstånd som $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .

Vi kan först försöka definiera $ o $ så att $ o \ket { x } = \ket { f (x) } $ , men det har ett par problem.
För $ det första $ kan f ha olika storlekar på indata och utdata ( $ n \ne m $ ), som att tillämpa $ O $ skulle ändra antalet qubits i registret.
Andra, även om $ n = m $ , kanske funktionen inte är inverteras: om $ f (x) = f (y) $ för vissa $ x \ne y $ , så $ o \ket { x } = o y, \ket { } $ men $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .
Det innebär att vi inte kan skapa den angränsande åtgärden $ O ^ \dagger $ , och Oracle måste ha ett angränsande definierat för dem.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definiera en Oracle genom att påverka beräknings bas staterna
Vi kan hantera båda dessa problem genom att introducera ett andra register av $ m $ qubits för att hålla vårt svar.
Därefter definierar vi resultatet av Oracle i alla beräknings grund lägen: för alla $ x \in \\ { 0, 1 \\ } ^ n $ och $ y \in \\ { 0, 1 \\ } ^ m $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Nu $ = \dagger $ måste vi ha löst båda de tidigare problemen.

> [!TIP]
>Om du vill se att o $ = { \dagger } $ $ ^ 2 = \boldone $ sedan $ \oplus b \oplus b = a $ för alla $ a, b \in \: :: No-Loc ({)::: 0, 1 \: :: No-Loc (}): $ ::.
>Det innebär att $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Det är viktigt att definiera en Oracle på det här sättet för varje beräknings bas status $ \ket { x } \ket { y } $ definierar också hur $ O $ fungerar för alla andra tillstånd.
Detta följer omedelbart från det faktum att $ O $ , precis som alla Quantum-åtgärder, är linjärt i det tillstånd som det fungerar på.
Överväg Hadamard-åtgärden, till exempel, som definieras av $ h \ket { 0 } = \ket { + } $ och $ h \ket { 1 } = \ket { - } $ .
Om vi vill veta hur $ h $ agerar på $ \ket { + } $ kan vi använda den här $ H $ är linjär,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

Om du definierar vår Oracle $ O $ kan vi på samma sätt använda att alla tillstånd $ \ket { \psi } $ på $ n + m $ qubits kan skrivas som

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

där $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representerar koefficienterna för status $ \ket { \psi } $ . Därför

$$
\begin{align}
O \ket { \psi } & = o \sum _{ x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum_ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Fas Oracle
Alternativt kan vi koda $ f $ till en Oracle- $ O $ genom att använda en _fas_ baserat på inmatat på $ O $ . Vi kan till exempel definiera $ O $ så att $$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Om en fas Oracle agerar i ett register inlednings vis i ett beräknings underlags tillstånd $ \ket { x } $ , är den här fasen en global fas och går därför inte att observera.
Men en sådan Oracle kan vara en mycket kraftfull resurs om den tillämpas på en överposition eller som en kontrollerad åtgärd.
Anta till exempel en fas Oracle- $ O_f $ för en qubit funktion $ f $ .
Dra $$
\begin{align}
    O_f \ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

> [!NOTE]
>Observera att $ z ^ { -1 } = Z ^ { \dagger } = Z $ och därför $ z ^ { f (0)-f (1) } = z ^ { f (1)-f (0) } .$

I allmänhet kan båda vyerna i Oracle utökas för att representera klassiska funktioner som returnerar reella tal i stället för bara en enda bit.

Att välja det bästa sättet att implementera en Oracle är beroende av hur den här Oracle kommer att användas inom en specifik algoritm.
Till exempel är [Deutsch-Jozsa-algoritmen](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) beroende av den Oracle som implementerats på det första sättet, medan [algoritmen för Grover är](https://en.wikipedia.org/wiki/Grover's_algorithm) beroende av den Oracle som implementerats på det andra sättet.


För mer information, föreslår vi diskussionen i [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
