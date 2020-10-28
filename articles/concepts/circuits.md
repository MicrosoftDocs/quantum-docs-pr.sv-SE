---
rubrik: Quantum-kretsar Beskrivning: Lär dig att visuellt återge enkla och komplexa Quantum-åtgärder med Quantum-krets diagram.
författare: QuantumWriter-UID: Microsoft. Quantum. Concepts. kretsar MS. author: v-benbra MS. Date: 12/11/2017 MS. topic: artikel nr-Loc:
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

# <a name="quantum-circuits"></a>Quantum-kretsar
Överväg att ta en stund till den enhetliga omvandlingen $ \text { CNOT } _ { 01 } (H \otimes 1) $ .
Den här grind serien är av grundläggande betydelse för Quantum Computing eftersom den skapar ett maximally Entangled-qubit tillstånd:

$$\mathrm{CNOT } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$

Åtgärder med den här eller större komplexiteten är allmänt förekommande i Quantum-algoritmer och Quantum Error-korrigering, så det bör vara en bra avläsnings metod för att det ska finnas en enkel metod för visualiseringen som kallas ett *Quantum-krets diagram* .
Krets diagrammet för att förbereda denna maximally Entangled-Quantum-tillstånd är:

<!--- ![](.\media\1.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Krets diagram för ett maximally-Entangled med två qubit-tillstånd](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Diagram konventioner för Quantum-kretsar
Det här visuella språket för Quantum Operations kan vara mer enkelt digestible än att skriva ned motsvarande matris när du förstår konventionerna för att uttrycka en Quantum-krets.
Vi går igenom dessa konventioner nedan.

I ett krets diagram illustrerar varje heldragen linje en qubit eller oftare i ett qubit-register.
Per konvention är den översta raden qubit registrerad $ 0 $ och resten märks sekventiellt. Exempel kretsen ovan illustreras på två qubits (eller motsvarande två register som består av en qubit).
Portar som agerar på en eller flera qubit-register betecknas som en box.
Till exempel symbolen

<!--- ![](.\media\2.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Symbol för en Hadamard-åtgärd som agerar på ett enda qubit-register](~/media/2.svg)

är en [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) -åtgärd som agerar på ett enda qubit-register.

Quantum Gates sorteras i kronologisk ordning med den översta porten som den grind som först appliceras på qubits.
Om du till exempel har en bild av kablarna som behålls i Quantum-läget, tar kablarna med Quantum-tillstånd genom varje port i diagrammet från vänster till höger.
Det vill säga 

<!--- ![](.\media\3.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Diagram över Quantum-grindar som används från vänster till höger](~/media/3.svg)

är den enhetliga matrisen $ CBA $ .
Matrisen multiplikation följer den motsatta konventionen: den högra matrisen används först. I Quantum-krets diagram används dock den översta porten först.
Den här skillnaden kan ibland leda till förvirring, så det är viktigt att notera denna betydande skillnad mellan de linjära Algebraic-och Quantum-krets diagrammen.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Indata och utdata från Quantum-kretsar
Alla tidigare exempel har haft exakt samma antal tråds (qubits) inmatade i en Quantum-grind som antalet ledningar från Quantum-grinden.
Det kan först förefalla rimligt att Quantum-kretsar kan ha mer eller färre utdata än vad som är allmänt.
Detta är omöjligt, eftersom alla Quantum-åtgärder, spara mått, är enhetliga och därmed kan ångras.
Om de inte har samma antal utdata som indata kan de inte vara reversibela och därför inte vara enhetliga, vilket är en motstridighet.
En ruta som ritas i ett krets diagram måste därför ha exakt samma antal kablar som du anger när den avslutas.

Multi-qubit krets diagram följer liknande konventioner för en qubit.
Som ett exempel på ett klargörande exempel kan vi definiera en två-qubit-åtgärd $ B $ som ska vara $ (H S \otimes X) $ och uttrycka kretsen på samma sätt som

<!--- ![](.\media\4.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Krets diagram över en qubit, enhetlig åtgärd](~/media/4.svg)

Vi kan också visa $ B $ som har en åtgärd på ett enda qubit-register i stället för 2 1-qubit-registreringar beroende på i vilken kontext kretsen används. Den mest användbara egenskapen för sådana abstrakta krets diagram är att de gör att komplicerade Quantum-algoritmer kan beskrivas på en hög nivå utan att behöva kompilera dem till fundamentala grindar.
Det innebär att du kan få en intuition om data flödet för en stor Quantum-algoritm utan att behöva förstå all information om hur var och en av under rutinerna i algoritmen fungerar.

## <a name="controlled-gates"></a>Kontrollerade grindar
Den andra konstruktion som är inbyggd i qubit-diagram med flera är kontroll.
Åtgärden för en Quantum och lätt kontrollerad grind, med antecknad $ \Lambda (G) $ , där ett enskilt qubit värde styr tillämpningen av $ G $ , kan tolkas genom att titta i följande exempel på en produkt tillstånds ingång $ \Lambda (G) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ . Det vill säga att den kontrollerade porten tillämpar $ G $ på registret som innehåller $ \psi $ om och bara om kontrollen qubit tar värdet $ 1 $ .
I allmänhet beskriver vi sådana kontrollerade åtgärder i krets diagram som

<!--- ![](.\media\5.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Krets diagram över en enkel kontrollerad grind](~/media/5.svg)

Här anger den svarta cirkeln den Quantum-bit som porten styrs av och en lodrät kabel anger den färg som tillämpas när kontrollen qubit tar värdet $ 1 $ .
För de specialfall där $ G = X $ och $ g = Z $ introducerar vi följande notation för att beskriva den kontrollerade versionen av grindarna (Observera att den kontrollerade X-porten är [ $ CNOT- $ grind](xref:Microsoft.Quantum.Intrinsic.CNOT)):

<!--- ![](.\media\6.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Krets diagram för särskilda fall av kontrollerade grindar](~/media/6.svg)

Q# innehåller metoder för att automatiskt generera en kontrollerad version av en åtgärd, vilket sparar programmerare från att behöva gå vidare med dessa åtgärder. Ett exempel på detta visas nedan:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Mått operator
Den återstående åtgärden att visualisera i krets diagram är mått.
Mätningen tar ett qubit register, mäter det och matar ut resultatet som klassisk information.
En mätnings åtgärd anges av en mätar symbol och fungerar alltid som indata för ett qubit-register (betecknas med en heldragen linje) och utvärderar klassisk information (betecknas med en dubbel linje).
Mer specifikt ser en sådan under krets ut så här:

<!--- ![](.\media\7.svg) ---->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Symbol som representerar en mått åtgärd](~/media/7.svg)

Q# implementerar en [mått operator](xref:Microsoft.Quantum.Intrinsic.Measure) för det här ändamålet.
Mer information finns i [avsnittet om mått](xref:microsoft.quantum.libraries.standard.prelude#measurements) .

På samma sätt är under kretsen

<!--- ![](.\media\8.svg) --->
<!--Kan inte hitta något sätt att enkelt centrera detta... troligen ett tillägg som krävs:-->
![Krets diagram som representerar en kontrollerad åtgärd](~/media/8.svg)

ger en klassisk kontrollerad grind där $ G $ tillämpas på den klassiska kontroll biten som värde $ 1 $ .

## <a name="teleportation-circuit-diagram"></a>Diagram över Teleportion krets
Quantum Teleportion är kanske den bästa Quantum-algoritmen för att illustrera dessa komponenter.
Du kan lära dig praktisk med motsvarande [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum-teleportning i den här metoden för att flytta data i en Quantum-dator (eller till och med mellan avlägsen quantum datorer i ett Quantum-nätverk) genom att använda entanglement och mätning.
Det kan vara intressant att flytta ett Quantum-tillstånd, säga värdet i en specifik qubit, från en qubit till en annan, utan att ens veta vad qubit värde är!
Detta är nödvändigt för att protokollet ska fungera enligt lagstiftningen i Quantum Mechanics.
Den andra kretsen för Quantum Teleportion anges nedan. Vi tillhandahåller också en kommenterad version av kretsen för att illustrera hur du kan läsa Quantum-kretsen.

<!--- ![](.\media\tp2.svg) { Bredd = 50%} --->
![Krets för Quantum Teleportion](~/media/tp2.svg)
