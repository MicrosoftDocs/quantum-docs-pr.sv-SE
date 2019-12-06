---
title: 'Q # standard bibliotek – program | Microsoft Docs'
description: Q#-standardbibliotek
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ef22460a5bca63ebaf32c0ba21984e103ec8ebdd
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864397"
---
# <a name="applications"></a>Appar #

## <a name="hamiltonian-simulation"></a>Hamiltonsk simulering ##

Simuleringen av Quantum Systems är ett av de mest spännande programmen i Quantum-beräkningen.
På en klassisk dator skalas svårigheten att simulera Quantum Mechanics i allmänhet med dimensions $N $ för sin tillstånds vektor representation.
I takt med att den här representationen ökar exponentiellt med antalet $n $ qubits $N = 2 ^ n $, en benämning som är känd även känd som [Curse](xref:microsoft.quantum.concepts.multiple-qubits), är Quantum-simuleringen i klassisk maskin vara indragbar.

Situationen kan dock vara mycket annorlunda på Quantum-maskinvara. Den vanligaste variationen av Quantum-simulering kallas för tids oberoende Hamiltonian simulerings problem. Det finns en beskrivning av systemets Hamiltonian $H $, som är en Hermitian-matris och vissa inledande Quantum-tillstånd $ \ket{\psi (0)} $ som är kodade i vissa fall på $n $ qubits på en Quantum-dator. I takt med att de stängda systemen utvecklas under Schrödinger ekvation $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ målet är att implementera den enhetliga tids utvecklings operatören $U (t) = e ^ {-iHt} $ vid vissa bestämda tidpunkter $t $ , där $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ matchar Schrödinger-ekvationen.
Analogously, den tids beroende Hamiltonian simulerings problemet matchar samma formel, men med $H (t) $ nu en funktion av tiden.

Hamiltonian-simulering är en viktig komponent i många andra problem med Quantum-simulering och lösningar på Hamiltonian simulerings problem är algoritmer som beskriver en sekvens med primitiva Quantum-grindar för att syntetisera en ungefärlig \tilde{U} $ med fel $\\| \tilde{U}-U (t)\\| \le \epsilon $ i [Spectral-normen](xref:microsoft.quantum.concepts.matrix-advanced). De här algoritmernas komplexitet är mycket starkt beroende av hur en beskrivning av Hamiltonian av intresse görs tillgänglig för en Quantum-dator. I värsta fall, om $H $ som agerar på $n $ qubits skulle tillhandahållas som en lista över $2 ^ n \times 2 ^ n $ Numbers, ett för varje mat ris element skulle det redan kräva exponentiell tid att läsa data. I det bästa fallet kan det vara bra att ha till gång till en svart box som $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ löser problemet enkelt. Ingen av dessa ingångs modeller är särskilt intressanta – den tidigare versionen är inte bättre än klassiska metoder och den senare som den svarta rutan döljer den primitiva gaten för dess implementering, vilket kan vara exponentiellt i antalet qubits.

### <a name="descriptions-of-hamiltonians"></a>Beskrivningar av Hamiltonians ###

Det krävs ytterligare antaganden om formatet på indatamängden. En fin balans måste ligga mellan ingångs modeller som är tillräckligt beskrivande för att omfatta intressanta Hamiltonians, t. ex. för realistiska fysiska system eller intressanta beräknings problem och ingående modeller som är tillräckligt begränsade för att effektivt kunna implementeras på en Quantum-dator. En mängd olika icke-triviala ingångs modeller finns i dokumentationen, och de sträcker sig från Quantum till klassisk. 

Som exempel på Quantum-ingångs modeller antar den [exempelbaserade Hamiltonian-simuleringen](http://www.nature.com/articles/s41534-017-0013-7) svart-Box till Quantum-åtgärder som producerar kopior av en densitets mat ris $ \rho $, som är Hamiltonian $H $. I den [enhetliga åtkomst modellen](https://arxiv.org/abs/1202.5822) förutsätter att Hamiltonian i stället dedelas i summan av unitaries $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j, \end{align} $ $ där $a\_j > 0 $ är koefficienter, och $ \hat{U}\_j $ är unitaries. Det förutsätts att en har svart-Box till gång till den enhetliga Oracle-$V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ som väljer önskad $ \hat{U}\_j $, och Oracle-$A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ sum ^ {d-1}\_{k = 0} \alpha\_j} \ket{j} $ som skapar en kodning av Quantum-tillstånd. I händelse av en [optimerad Hamiltonian-simulering](https://arxiv.org/abs/quant-ph/0301023)förutsätter det att Hamiltonian är en sparse-matris med endast $d = \mathcal{O} (\Text{polylog} (N)) $ element som inte är noll i varje rad. Dessutom förutsätter en förekomst av effektiva Quantum-kretsar som utvärderar platsen för dessa icke-noll-element, samt deras värden. Komplexiteten för [algoritmerna för Hamiltonian simulering](xref:microsoft.quantum.more-information) utvärderas som antalet frågor till dessa svarta rutor, och den primitiva grinden av porten är sedan mycket stor på svårigheten att implementera dessa svarta rutor.

> [!NOTE]
> Big-O-notationen används ofta för att beskriva komplexitets skalningen för algoritmer. Med två verkliga Functions $f, g $, uttrycket $g (x) = \mathcal{O} (f (x)) $ betyder det att det finns en absolut positiv konstant $x\_0, c > 0 $ så $g (x) \le c f (x) $ för alla $x \ge x\_$0. 

I de flesta praktiska program som ska implementeras på en Quantum-dator måste dessa svarta rutor vara effektiva att implementera, det vill säga med $ \mathcal{O} (\text{polylog} (N)) $ primitiva Quantum-grindar. Mer starkt simulable Hamiltonians måste ha en viss tillräckligt optimerad klassisk beskrivning. I en sådan formulering förutsätts det att Hamiltonian i en summa av Hermitian-delarna $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $, det förutsätts dessutom att varje del, en Hamiltonian $H\_j $, är lätt att simulera. Det innebär att den enhetliga $e ^ {-iH\_j t} $ när som helst $t $ kan implementeras exakt med $ \mathcal{O} (1) $ primitiva Quantum-grindar. Detta är till exempel sant i det särskilda fallet där varje $H\_j $ är lokala Pauli-operatörer, vilket innebär att de är av \mathcal{O} produkter av $ (1) $ Pauli-operatörer som agerar på rums qubits. Den här modellen är särskilt tillämplig på fysiska system med gräns och lokal interaktion, eftersom antalet villkor är $d = \mathcal{O} (\text{polylog} (N)) $, och det kan tydligt skrivas ned, vilket beskrivs i polynom tid.

> [!TIP]
> Hamiltonians som ingår i en summa av delar kan beskrivas med hjälp av det dynamiska Generator representations biblioteket. Mer information finns i avsnittet representation av dynamiskt Generator i [data strukturer](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Simulerings algoritmer ###

En algoritm för Quantum simulering konverterar en specifik Beskrivning av en Hamiltonian till en sekvens med primitiva Quantum-grindar som, som helhet, närmar sig tids utvecklingen av Hamiltonian.

I det särskilda fallet där Hamiltonian delas upp i en summa av Hermitian delar, är Trotter-Suzuki-dekompositionen en särskilt enkel och intuitiv algoritm för att simulera Hamiltonians som sammanställer till en summa av Hermitian-komponenter. Till exempel är en första ordning integrerare i den här familjen ungefär $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $ med en produkt av $r d $-villkor. 

> [!TIP]
> Program av algoritmen Trotter-Suzuki simulering beskrivs i exemplen.
> För Ising-modellen som bara använder de inbyggda åtgärder som tillhandahålls av varje måldator, se [ **SimpleIsing** -exemplet](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Ising-modellen med hjälp av Trotter-Suzuki biblioteks kontroll struktur finns i [ **IsingTrotter** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> För molekyliga väte med Trotter-Suzuki biblioteks kontroll struktur kan du se [exempel på **H2-simulering** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

I många fall vill vi implementera simulerings algoritmen, men den är inte intresse rad av implementeringens information. Till exempel, den andra ordnings integreraren uppskattar $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/2R} e ^ {-iH\_1 t/2R} \cdots e ^ {-iH\_{d-1} t/2R} e ^ {-iH\_{d-1} t/2R} \cdots e ^ {-iH\_1 t/2R} e ^ {-iH\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ med en produkt av $2rd $-villkor. Större beställningar innebär ännu fler villkor och optimerade varianter kan kräva hög icke-trivial ordningsföljd på exponenterna. Andra avancerade algoritmer kan också innebära användning av Ancilla-qubits i mellanliggande steg. Därför har vi paket simulerings algoritmer i filen Canon som användardefinierad typ

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

Den första parametern `Double` är tidpunkten för simulering, den andra parametern `EvolutionGenerator`, som omfattas av representations avsnittet för dynamisk Generator i [data strukturer](xref:microsoft.quantum.libraries.data-structures), är en klassisk Beskrivning av en tidsoberoende Hamiltonian paketerad med anvisningar om hur varje term i Hamiltonian kan simuleras av en Quantum-krets. Typerna av detta formulär uppskattar den enhetliga åtgärden $e ^ {-iHt} $ på den tredje parametern `Qubit[]`, vilket är det register som lagrar det simulerade systemets Quantum-tillstånd. På samma sätt för tids beroende fallet definierar vi en användardefinierad typ med en `EvolutionSchedule` typ i stället, som är en klassisk Beskrivning av en tids beroende Hamiltonian.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Som exempel kan Trotter-Suzuki diskompositionen anropas med hjälp av följande Canon functions, med parametrar `trotterStepSize` ändra varaktigheten för simuleringen i varje exponentiell och `trotterOrder` för den önskade integratorns ordning.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : SimulationAlgorithm {
    ...
}
function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Program för simulerings biblioteket beskrivs i exemplen. För fas uppskattning i Ising-modellen med hjälp av `SimulationAlgorithm`, se [ **IsingPhaseEstimation** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> För förberedelse av adiabatic-tillstånd i Ising-modellen med hjälp av `TimeDependentSimulationAlgorithm`, se exemplet på [ **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic för att förbereda & fas uppskattning ###

Ett vanligt program för Hamiltonian-simulering är adiabatic-tillstånds förberedelse. Här följer två Hamiltonians-$H\_{\text{start}} $ och $H\_{\text{End}} $ och ett Quantum-tillstånd $ \ket{\psi (0)} $ som är ett mark läge för start Hamiltonian $H\_{\text{start}} $. Vanligt vis väljs $H\_{\text{start}} $ så att $ \ket{\psi (0)} $ är enkelt att förbereda från beräknings bas tillstånd $ \ket{0\cdots 0} $. Genom interpolating mellan dessa Hamiltonians i tids beroende simulerings problem tillräckligt långsamt, är det möjligt att uppnå hög sannolikhet i det slutliga Hamiltonian $H\_{\text{End}} $. Även om det går att förbereda en utmärkt uppskattning av Hamiltonian-länder kan du gå vidare på det här sättet genom att anropa på tids beroende Hamiltonian simulerings algoritmer som en subrutin, andra konceptuella metoder, till exempel variationen Quantum eigensolver är möjliga.

Ännu en annan program allmänt förekommande i Quantum kemi uppskattar den markbaserade energin för Hamiltonians som representerar de mellanliggande stegen för kemisk reaktion. Ett sådant schema kan t. ex. förlita sig på adiabatic State-förberedelse för att skapa ett jord-tillstånd och sedan införliva den tidsbegränsade Hamiltonian-simuleringen som en del rutin i beräknings beräknings karakteriseringen för att extrahera denna energi med ett begränsat fel och sannolikheten lyckades. 

Algoritmer för att beräkna simuleringar som användardefinierade typer `SimulationAlgorithm` och `TimeDependentSimulationAlgorithm` göra det möjligt för oss att enkelt införliva sina funktioner i mer avancerade Quantum-algoritmer. Detta motiverar oss att göra samma sak för de här ofta använda underrutinerna.

Vi definierar därför den praktiska funktionen

```qsharp
function InterpolatedEvolution(
        interpolationTime: Double, 
        evolutionGeneratorStart: EvolutionGenerator,
        evolutionGeneratorEnd: EvolutionGenerator,
        timeDependentSimulationAlgorithm: TimeDependentSimulationAlgorithm)
        : (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Detta returnerar en enhetlig åtgärd som implementerar alla steg i adiabatic-tillstånds förberedelse. Den första parametern `interpolatedTime` definierar den tid över vilken vi linjärt interpolerar mellan start-Hamiltonian som beskrivs av den andra parametern `evolutionGeneratorStart` och slut Hamiltonian som beskrivs av den tredje parametern `evolutionGeneratorEnd`. Den fjärde parametern `timeDependentSimulationAlgorithm` är där du kan välja simulerings algoritm. Observera att om `interpolatedTime` är tillräckligt lång, är ett initialt jord tillstånd kvar i Hamiltonian under hela tiden för tids beroende simulering och därmed avslutas i slutet av slut Hamiltonian.

Vi definierar också en användbar åtgärd som automatiskt utför alla steg i ett typiskt Quantum kemi-experiment. Till exempel har vi följande, som returnerar en energi uppskattning av den status som produceras av adiabatic-tillstånds förberedelse:

```qsharp
operation AdiabaticStateEnergyEstimate( 
    nQubits : Int, 
    statePrepUnitary: (Qubit[] => Unit),
    adiabaticUnitary: (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
    : Double {
...
}
```

`nQubits` är antalet qubits som används för att koda det inledande Quantum-läget. `statePrepUnitary` förbereder start tillstånd från beräknings basen $ \ket{0\cdots 0} $. `adiabaticUnitary` är en enhetlig åtgärd som implementerar adiabatic-tillstånds förberedelse, till exempel producerad av funktionen `InterpolatedEvolution`. `qpeUnitary` är den enhetliga åtgärd som används för att utföra fas uppskattningar i det resulterande steget. `phaseEstAlgorithm` är vårt val av algoritm för fas uppskattning.

> [!TIP]
> Program för förberedelse av adiabatic-tillstånd beskrivs i exemplen. För Ising-modellen med en manuell implementering av adiabatic-tillstånds förberedelse jämfört med `AdiabaticEvolution` funktionen, se exemplet på [ **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> För fas uppskattning och förberedelse av adiabatic-tillstånd i Ising-modellen, se [exemplet på **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> [Simuleringen av molekylen väte](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) är ett intressant och kort exempel. Modell-och experiment resultaten som rapporteras i [O'Malley et. Al.](https://arxiv.org/abs/1512.06860) kräver bara Pauli-matriser och använder formatet $ \hat H = g\_{0}\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Detta är en effektiv Hamiltonian som bara behöver bara två qubits, där konstanterna $g $ beräknas från avståndet $R $ mellan de två väte-atomerna. Med hjälp av Canon functions, konverteras Johan till unitaries och sedan utvecklats över korta tids perioder med hjälp av Trotter-Suzuki-dekompositionen. Det går att skapa en utmärkt uppskattning av $H _2 $ mark State utan att använda adiabatic och så att energi tillståndets energi kan hittas direkt genom att använda fas uppskattning från Canon.

## <a name="shors-algorithm"></a>Shors algoritm ##
Shor-algoritmen är inte en av de viktigaste fördelarna med Quantum Computing eftersom den visade att Quantum Computers kan användas för att lösa viktiga, för närvarande inaktiverade problem.
Shor-algoritmen är ett snabbt sätt att väga stora tal med en Quantum-dator, ett problem som kallas för *factoring*.
Säkerheten för många befintliga cryptosystems baseras på antagandet att det inte finns någon snabb algoritm för factoring.
Därför har Shor-algoritmen haft en Profound inverkan på hur vi tycker om säkerhet i en post-Quantum World.

Shor-algoritmen kan betraktas som en hybrid algoritm.
Quantum-datorn används för att utföra en beräknings hårt aktivitet som kallas för att söka efter perioder.
Resultaten från periods ökningen bearbetas sedan som en uppskattning av faktorerna.
Vi går igenom de här två stegen nedan.

### <a name="period-finding"></a>Period sökning ###

Vi har sett hur Quantum Fourier-transformeringen och fas uppskattningen fungerar (se [Quantum-algoritmer](xref:microsoft.quantum.libraries.standard.algorithms)). vi kan använda dessa verktyg för att lösa ett klassiskt hårt beräknings problem som kallas för *period sökning*.  I nästa avsnitt kommer vi att se hur perioden kan användas för att debiteras.

Med två heltal $a $ och $N $, där $a < N $, målet för perioden som söker, även kallat order sökning, är att hitta _order_ $r $ $a $ modulo $N $, där $r $ har definierats som minst positivt heltal som $a ^ r \equiv 1 \text{mod} N $.  

För att hitta beställningen med en Quantum-dator kan vi använda fasen för fas uppskattning som tillämpas på följande enhetliga operatör $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \text{mod} N}. $ $ eigenvectors för $U _a $ är för heltal $s $ och $0 \ LEQ s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i sk} {r}} \ket{a ^ k\text {rest} N}, $ $ är _eigenstates_ av $U _A $.
Eigenvalues för $U _a $ är $ $ U\_en \ket{x\_s} = e ^ {2 \ Pi i s/r} \ket{x\_s}. $$

Fas uppskattningen utökar därmed Eigenvalues $e ^ {2 \ Pi i s/r} $ från vilken $r $ kan läsas effektivt med hjälp av [fortsatt bråk](https://en.wikipedia.org/wiki/Continued_fraction) från $s/r $.

Krets diagrammet för Quantum period är:

![](./../../media/QPE.svg)

Här $2n $ qubits initieras till $ \ket{0}$ och $n $ qubits initieras till $ \ket{1}$.
Det kan hända att läsaren återigen undrar varför den Quantum-registreraren för att hålla eigenstates initieras till $ \ket{1}$.
Eftersom en inte känner till order $r $ i förväg, kan vi faktiskt inte förbereda $ \ket{x_s} $-tillstånd direkt.
Som tur är, det visar sig att $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
Vi behöver faktiskt inte förbereda $ \ket{x} $!
Vi kan bara förbereda ett Quantum-register över $n $ qubits i stat $ \ket{1}$. 

Kretsen innehåller QFT och flera kontrollerade portar.
QFT-porten har beskrivits [tidigare](xref:microsoft.quantum.libraries.standard.algorithms).
Det styrda-$U _a $ Gate Maps $ \ket{x} $ till $ \ket{(AX) \text{mod} N} $ om kontrollen qubit är $ \ket{1}$ och mappar $ \ket{x} $ till $ \ket{x} $ annars.

För att uppnå $ (a ^ NX) \text{mod} N $ kan vi helt enkelt tillämpa styrd-$U _ {a ^ N} $, där vi beräknar $a ^ N \text{mod} N $ som är klassiska för att ansluta till Quantum-kretsen.  
Kretsarna för att uppnå sådana modulära beräkningar har beskrivits i den [Quantum-aritmetiska dokumentationen](./algorithms.md#arithmetic), i synnerhet vi kräver en modulär exponent krets för att implementera de kontrollerade $U\_{a ^ i} $-åtgärder.

Även om kretsen ovan motsvarar Quantum- [fas-uppskattningen](xref:microsoft.quantum.characterization.quantumphaseestimation) och explicit aktiverar order upptäckt, kan vi minska antalet qubits som krävs. Vi kan antingen följa Beauregard-metoden för order sökning enligt beskrivningen [på sidan 8 i arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)eller använda en av de fas uppskattnings rutiner som är tillgängliga i Microsoft. Quantum. Canon. Till exempel använder [robust fas uppskattning](xref:microsoft.quantum.characterization.robustphaseestimation) också en extra qubit.
 
### <a name="factoring"></a>Hänsyn ###
Syftet med att använda factoring är att fastställa de två viktigaste faktorerna i heltal $N $, där $N $ är ett $n $-bitars nummer.  
Factoring består av stegen som beskrivs nedan. Stegen delas upp i tre delar: en klassisk för bearbetnings rutin (1-4). en Quantum Computing-rutin för att hitta ordningen på $a \text{mod} N $ (5); och en klassisk postprocessing-rutin för att härleda de viktigaste faktorerna från ordern (6-9).

Den klassiska för bearbetnings rutinen består av följande steg:
1. Om $N $ är ens returnerar du den primära faktorn $2 $.
2. Om $N = p ^ q $ för $p \geq1 $, $q \geq2 $, returnerar du den primära faktorn $p $.  Det här steget utförs i klassiskt läge.
3. Välj ett slumptal $a $ så att $1 < en < N-$1.
4. Om $ \text{GCD} (a, N) > 1 $ returnerar du den primära faktorn $ \text{GCD} (a, N) $. Det här steget beräknas med Euclid-algoritmen.
Om ingen primär faktor har returnerats går vi vidare till Quantum-rutinen:
5. Anropa den Quantum perioden hitta algoritmen för att beräkna ordningen $r $ för $a \text{mod} N $. Använd $r $ i den klassiska postprocessing-rutinen för att fastställa de viktigaste faktorerna:
6. Om $r $ är ojämn går du tillbaka till förbearbetnings steget (3).
7. Om $r $ är jämnt och $a ^ {r/2} =-1 \ text {mod} N $ går du tillbaka till för bearbetnings steg (3).
8. Om $ \text{GCD} (a ^ {r/2} + 1, N) $ är en icke-trivial faktor för $N $ Returnerar du $ \text{GCD} (a ^ {r/2} + 1, N) $.
9. Om $ \text{GCD} (a ^ {r/2}-1, N) $ är en icke-trivial faktor på $N $ Returnerar du $ \text{GCD} (a ^ {r/2}-1, N) $.


Factoring-algoritmen är Probabilistic: den kan visas med sannolikheten minst en halv som $r $ kommer att vara jämn och $a ^ {r/2} \neq-1 \text{mod} N $, vilket skapar en primär faktor.  (Mer information finns i [Shor original Paper](https://doi.org/10.1109/SFCS.1994.365700) eller något av de *grundläggande Quantum Computing* -texterna i [för mer information](xref:microsoft.quantum.more-information)).
Om en primär faktor inte returneras upprepar vi bara algoritmen från steg (1).  När $n $ försöker är sannolikheten att varje försök har misslyckats högst $2 ^ {-n} $.
Därför är det ett litet antal gånger som lyckats när algoritmen har upprepats.
