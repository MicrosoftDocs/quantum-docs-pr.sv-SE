---
title: Data strukturer i Q# standard biblioteken
description: Lär dig mer om data strukturer, Oracle och dynamiska generatorer i Microsofts Q# standard bibliotek.
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 222fa7d0d33d4ac6c15e9ee9e6e97f380867a145
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868532"
---
# <a name="data-structures-and-modeling"></a>Data strukturer och modeller #

## <a name="classical-data-structures"></a>Klassiska data strukturer ##

Tillsammans med användardefinierade typer för att representera Quantum-koncept, innehåller Canon även åtgärder, funktioner och typer för att arbeta med klassiska data som används i kontrollen över Quantum Systems.
Funktionen tar till exempel <xref:microsoft.quantum.arrays.reversed> en matris som inmatad och returnerar samma matris i omvänd ordning.
Detta kan sedan användas på en matris av typen `Qubit[]` för att undvika att behöva tillämpa onödiga $ \operatorname{swap} $-grindar vid konvertering mellan Quantum-representationer av heltal.
På samma sätt såg vi i föregående avsnitt att typer av formulär `(Int, Int -> T)` kan vara användbara för att representera slumpmässiga åtkomst samlingar, så <xref:microsoft.quantum.arrays.lookupfunction> funktionen ger ett bekvämt sätt att konstruera sådana typer från mat ris typer.

### <a name="pairs"></a>Stod ###

Canon stöder funktionell notation för par som kompletterar åtkomst till tupler genom att avkonstrueras:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Matriser ###

Canon innehåller flera funktioner för att ändra matriser.
Dessa funktioner är Type-parameterd och kan därför användas med matriser av valfri Q# typ.
Funktionen returnerar till exempel <xref:microsoft.quantum.arrays.reversed> en ny matris vars element är i omvänd ordning från dess Indatatyp.
Detta kan användas för att ändra hur ett Quantum-register representeras vid anrop av åtgärder:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

På samma sätt <xref:microsoft.quantum.arrays.subarray> kan funktionen användas för att ändra ordning på eller ta med del mängder av elementen i en matris:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

I kombination med Flow-kontroll fungerar mat ris funktioner som exempelvis <xref:microsoft.quantum.arrays.zip> kan ge ett kraftfullt sätt att uttrycka Quantum-program:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracle ##

I steg-för- [steg-uppskattning](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) och litteratur för [amplitud förstärkning](https://en.wikipedia.org/wiki/Amplitude_amplification) används begreppet Oracle ofta.
Här är termen Oracle en blackbox Quantum-underrutin som agerar på en uppsättning qubits och returnerar svaret som en fas.
Den här subrutinen kan ofta ses som en inläsning av en Quantum-algoritm som godkänner Oracle, förutom andra parametrar, och som använder en serie Quantum-åtgärder och som behandlar ett anrop till den här Quantum-underrutinen som om det vore en grundläggande grind.
För att du ska kunna implementera den större algoritmen måste en konkret nedbrytning av Oracle till fundamental Gates tillhandahållas, men sådan dekomposition behövs inte för att förstå algoritmen som anropar Oracle.
I Q# representeras den här abstraktionen med hjälp av den här typen av värden i första klass, så att åtgärder kan skickas till implementeringar av Quantum-algoritmer i ett svart-box.
Dessutom används användardefinierade typer för att märka olika Oracle-representationer på ett typ säkert sätt, vilket gör det svårt att oavsiktligt dela olika typer av svarta Box-åtgärder.

Sådana Oracle visas i ett antal olika kontexter, inklusive berömda-exempel, till exempel [Grover search](https://en.wikipedia.org/wiki/Grover%27s_algorithm) -och Quantum simulering-algoritmer.
Här fokuserar vi på de Oracle som behövs för bara två program: amplitud förstärkning och fas uppskattning.
Vi ska först diskutera amplituds förstärknings Oracle innan du fortsätter till fas uppskattningen.

### <a name="amplitude-amplification-oracles"></a>Oracle-förstärkning för amplitud ###

Algoritmen för amplitud förstärkning syftar till att utföra en rotation mellan ett ursprungligt tillstånd och ett slutligt tillstånd genom att använda en sekvens av reflexer av staten.
För att algoritmen ska fungera krävs en specifikation av båda dessa tillstånd.
Dessa specifikationer ges av två Oracle-enheter.
Dessa Oracle fungerar genom att dela upp indata i två blank steg, ett "mål"-och under utrymme.
Oracle-enheterna identifierar sådana under utrymmen, liknande hur Pauli-operatörer identifierar två mellanslag genom att tillämpa en $ \pm $1-fas på dessa utrymmen.
Den största skillnaden är att dessa utrymmen inte behöver vara hälften-blank steg i det här programmet.
Observera också att dessa två del utrymmen vanligt vis inte är ömsesidigt uteslutande: det kommer att vara vektorer som är medlemmar i båda områdena.
Om detta inte var sant skulle amplitud-förstärkningen ha ingen påverkan, så vi behöver det inledande under utrymmet för att få icke-noll överlappande mål under utrymmet.

Vi anger den första Oracle som vi behöver för amplitud-förstärkningen $P \_ $0, som definieras för att ha följande åtgärd.  För alla delstater $ \ket{x} $ i "första" under utrymmet $P \_ 0 \ket{x} =-\ket{x} $ och för alla tillstånd $ \ket{y} $ som inte ingår i det här under utrymmet har vi $P \_ 0 \ket{y} = \ket{y} $.
Oracle som markerar mål under utrymmet, $P _1 $, tar exakt samma formulär.
För alla tillstånd $ \ket{x} $ i mål under utrymmet (dvs. för alla tillstånd som du vill att algoritmen ska mata ut), $P _1 \ ket {x} =-\ket{x} $.
På samma sätt gäller för alla tillstånd $ \ket{y} $ som inte finns i mål under utrymmet $P _1 \ ket {y} = \ket{y} $.
Dessa två reflektioner kombineras sedan för att bilda en operatör som agerar i ett enda steg av amplitud-förstärkning, $Q =-P_0 P_1 $, där det totala minus tecknet bara är viktigt att tänka på i kontrollerade program.
Amplitud-förstärkningen fortsätter sedan genom att göra ett ursprungligt tillstånd, $ \ket{\psi} $ som är i det första under utrymmet och sedan utföra $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
Att utföra en sådan upprepning garanterar att om en börjar med ett ursprungligt tillstånd som har överlappande $ \sin ^ 2 (\theta) $ med det markerade utrymmet $m kommer den överlappande att bli $ \sin ^ 2 ([2 m + 1] \theta) $.
Vi vill därför vanligt vis välja $m $ som en kostnads fri parameter som $ [2 m + 1] \theta = \ Pi/2 $; sådana fasta val är dock inte lika viktiga för vissa former av amplitud förstärkning, till exempel amplitud förstärkning av fast punkt.
Med den här processen kan vi förbereda ett tillstånd i det markerade del utrymmet med hjälp av kvadratiskt färre frågor till märknings funktionen och tillstånds förberedelse funktionen än vad som skulle vara möjligt på en absolut klassisk enhet.
Det är därför som amplitud förstärkning är ett betydande Bygg block för många program av Quantum Computing.

För att förstå hur du använder algoritmen, är det praktiskt att tillhandahålla ett exempel som ger en konstruktion av Oracle.  Överväg att utföra Grover-algoritmen för Databass ökningar i den här inställningen.
I Groverens sökning är målet att transformera tillståndet $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ till ett av (potentiellt) många markerade tillstånd.
För att ytterligare förenkla ska vi bara titta på det fall där det enda markerade läget är $ \ket {0} $.
Sedan har vi designat två Oracle: One som bara markerar det ursprungliga läget $ \ket{+} ^ {\otimes n} $ med ett minus tecken och en annan som markerar det markerade läget $ \ket {0} $ med ett minus tecken.
Den sistnämnda porten kan implementeras med hjälp av följande process-åtgärder med hjälp av åtgärder för kontroll flöde i filen Canon:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Den här Oracle är sedan ett specialfall av <xref:microsoft.quantum.canon.rall1> åtgärden, som gör det möjligt att rotera med en godtycklig fas i stället för reflektions väskan $ \phi = \pi $.
I det här fallet `RAll1` liknar <xref:microsoft.quantum.intrinsic.r1> åtgärden inledning, i så här roterar vi om $ \ket{11\cdots1} $ i stället för qubit-tillstånd $ \ket {1} $.

Oracle som markerar det inledande under utrymmet kan skapas på samma sätt.
I pseudocode:

1. Använd $H $ Gates för varje qubit.
2. Använd $X $ Gates för varje qubit.
3. Använd en $n-$1-kontrollerad $Z $-grind till $n ^ {\text{th}} $ qubit.
4. Använd $X $ Gates för varje qubit.
5. Använd $H $ Gates för varje qubit.

Den här gången demonstrerar vi också användning <xref:microsoft.quantum.canon.applywith> tillsammans med <xref:microsoft.quantum.canon.rall1> åtgärden som diskuteras ovan:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Vi kan sedan kombinera dessa två Oracle-grupper för att rotera mellan de två tillstånden och deterministiskt Transform $ \ket{+} ^ {\otimes n} $ till $ \ket {0} $ med ett antal lager av Hadamard-portar som är proportionella till $ \sqrt{2 ^ n} $ (ie $m \propto \sqrt{2 ^ n} $) jämfört med de ungefär $2 ^ n $-lager som skulle behövas för att icke-deterministiskt ska förbereda $ \ket {0} $-tillstånd genom att förbereda och mäta det ursprungliga läget tills resultatet $0 $ observeras.

### <a name="phase-estimation-oracles"></a>Fas uppskattning i Oracle ###

För fas uppskattning är Oracle-formerna något mer naturliga.
Syftet med fas uppskattning är att utforma en subrutin som kan sampla från Eigenvalues i en enhetlig matris.
Den här metoden är inte användbar i Quantum-simuleringen eftersom det för många fysiska problem i kemi-och material vetenskap i dessa Eigenvalues ger Energies av Quantum-system, vilket ger oss värdefull information om fas diagram för material och reaktions dynamik för molekyler.
Varje smak av fas uppskattning behöver en enhetlighet.
Den här enhetliga beskrivningen beskrivs av en av två typer av Oracle.

> [!TIP]
> Båda typerna av Oracle som beskrivs nedan beskrivs i exemplen.
> Om du vill veta mer om kontinuerliga frågor och Oracle kan du se [ **PhaseEstimation** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation).
> Om du vill veta mer om diskreta frågor och Oracle kan du se [ **IsingPhaseEstimation** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

Den första typen av Oracle, som vi anropar en diskret fråga i Oracle och representerar den användardefinierade typen <xref:microsoft.quantum.oracles.discreteoracle> , inbegriper helt enkelt en enhetlig matris.
Om $U $ är den höga vars Eigenvalues vi vill uppskatta, är Oracle för $U $ helt enkelt ett enda sätt att använda en subrutin som implementerar $U $.
Det kan till exempel ta $U $ att vara den Oracle $Q $ som definieras ovan för amplituds uppskattning.
Eigenvalues för den här matrisen kan användas för att uppskatta överlappningen mellan de initiala och mål tillstånden, $ \sin ^ 2 (\theta) $, med en kvadratiskt färre sampel än en som annars skulle behövas.
Detta är programmet för fas uppskattning med hjälp av Grover Oracle $Q $ som inmatade moniker för amplitud-uppskattning.
Ett annat vanligt program, som ofta används i Quantum metrologi, innebär en liten rotations vinkel.
Med andra ord vill vi uppskatta $ \theta $ för en okänd rotations grind av formuläret $R _z (\theta) $.
I sådana fall är underrutinen som vi skulle interagera med för att lära sig detta fasta värde på $ \theta $ för porten $ $ \begin{align} U & = R_z (\theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ theta/2} \end{bmatrix}.
\end{align} $ $

Den andra typen av Oracle som används i fas uppskattning är den kontinuerliga frågan Oracle, som representeras av <xref:microsoft.quantum.oracles.continuousoracle> typen.
En kontinuerlig fråga för beräkning av Oracle för fas tar formuläret $U (t) $ där $t $ är ett klassiskt känt reellt tal.
Om vi låter $U $ vara en fast enhetlig, tar den kontinuerliga frågan Oracle formen $U (t) = U ^ t $.
Detta gör att vi kan fråga matriser som $ \sqrt{U} $, som inte kunde implementeras direkt i den diskreta fråge modellen.

Den här typen av Oracle är värdefull när du inte har en viss enhetlighet, utan i stället vill lära dig egenskaperna för generatorn för den enhetliga.
I en dynamisk Quantum-simulering är målet till exempel att utforma Quantum-kretsar som närmar sig $U (t) = e ^ {-i H t} $ för en Hermitian-matris $H $ och utvecklings tid $t $.
Eigenvalues för $U (t) $ är direkt relaterat till Eigenvalues för $H $.
För att se detta bör du överväga en eigenvector av $H $: $H \ket{E} = E\ket {E} $ och det är enkelt att se från Power-seriens definition av matrisen exponent som $U (t) \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $.
Därför uppskattar eigenphase i $U (t) $ eigenvalue $E $ förutsatt att eigenvector $ \ket{E} $ är inmatat i algoritmen för fas uppskattning.
I det här fallet kan värdet $t $ väljas på användarens eget gottfinnande eftersom det finns tillräckligt mycket små värdet $t $ eigenvalue $E $ kan inverteras unikt genom $E =-\ Fi/t $.
Eftersom Quantum simulerings metoder ger möjlighet att utföra en fraktions utveckling ger detta en ytterligare frihet vid frågor till den enhetliga frågan, särskilt när den diskreta fråge modellen bara tillåter att unitaries av formuläret $U ^ j $ till att gälla heltal $j $ den kontinuerliga frågan Oracle gör det möjligt för oss att approximera unitaries i formuläret $U ^ t $ för alla verkliga värdefulla $t $.
Det är viktigt att du går igenom var och en av de sista ouncena av fas uppskattnings algoritmer eftersom vi kan välja exakt det experiment som skulle ge mest information om $E $; metoder som baseras på diskreta frågor måste göra detta genom att välja det bästa heltals antalet frågor i algoritmen.

Som ett konkret exempel på detta bör du överväga problemet med att uppskatta inte rotations vinkeln för en grind, men process frekvensen för ett roterande Quantum-system.
Den enhetliga som beskriver den här Quantum Dynamics är $U (t) = R_z (2 \ Omega t) $ för utvecklings tid $t $ och okänd frekvens $ \omega $.
I det här sammanhanget kan vi simulera $U (t) $ för alla $t $ med en enda $R _z $-grind och eftersom sådana inte behöver begränsa skapar till enbart diskreta frågor till den enhetliga.
En sådan kontinuerlig modell har också egenskapen att frekvenser som är större än $2 \ PI $ kan hämtas från fas uppskattnings processer som använder kontinuerliga frågor, eftersom den information som annars annars skulle maskeras av gren-klippen i logaritm-funktionen kan visas från resultaten av experiment som har utförts på värden som inte ligger i proportion till $t $.
Därför är det inte bara lämpligt för problem som den här kontinuerliga fråg ande frågan för fas uppskattning av Oracle, men det är också bättre än den diskreta fråge modellen.
Av den här orsaken Q# finns funktioner för båda typerna av frågor och lämna dem till användaren för att bestämma en fas uppskattnings algoritm som passar deras behov och vilken typ av Oracle som är tillgänglig.

## <a name="dynamical-generator-modeling"></a>Modell för dynamisk Generator ##

Generatorer för tids utveckling beskriver hur tillstånd utvecklas med tiden. Till exempel regleras dynamiken för ett Quantum-tillstånd $ \ket{\psi} $ av Schrödinger ekvation $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ med en Hermitian-matris $H $, kallat Hamiltonian, som generator av rörelse. Fått ett första tillstånd $ \ket{\psi (0)} $ vid tiden $t = $0, den formella lösningen till den här ekvationen vid tidpunkten $t $ kan i princip skriva $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $ där matrisen exponentiell $U (t) = e ^ {-i H t} $ är känd som den enhetliga tids utvecklings operatorn. Även om vi fokuserar på generatorer för det här formuläret i följande betonar vi att konceptet är mer brett, till exempel simuleringen av öppna Quantum-system, eller till fler abstrakta differential formler.

Ett primärt mål för dynamisk simulering är att implementera tids utvecklings operatorn för vissa Quantum-tillstånd som är kodade i qubits på en Quantum-dator.  I många fall kan Hamiltonian delas upp i en summa av vissa $d enklare och enklare villkor

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

där tids utvecklingen för varje enskilt fall är lätt att implementera på en Quantum-dator. Om $H _j $ till exempel är en Pauli $X _1X_2 $-operatör som agerar på de första och andra elementen i qubit `qubits` -registret, kan tids utvecklingen av den vara så fort som möjligt $t $ implementeras bara genom att anropa åtgärden `Exp([PauliX,PauliX], t, qubits[1..2])` , som har signatur `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Som vi diskuterade senare i Hamiltonian-simuleringen är det en lösning som sedan är att uppskatta tids utvecklingen genom $H $ med en sekvens med enklare åtgärder

$ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $

där heltals $r > $0 styr det ungefärliga felet.

Modell biblioteket för dynamisk generator ger ett ramverk för att systematiskt koda komplicerade generatorer i termer av enklare generatorer. En sådan beskrivning kan sedan skickas till, till exempel bibliotek för simulering för att implementera tids utveckling med en vald simulerings algoritm, med många detaljer som automatiskt tar hand om.

> [!TIP]
> Det dynamiska Generator biblioteket som beskrivs nedan beskrivs i exemplen. Ett exempel som baseras på Ising-modellen finns i [ **IsingGenerators** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators).
> Ett exempel som baseras på molekylen väte finns i exemplen [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) och [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui) .

### <a name="complete-description-of-a-generator"></a>Fullständig beskrivning av en generator ###

På den översta nivån finns en fullständig beskrivning av en Hamiltonian i den `EvolutionGenerator` användardefinierade typ som har två komponenter.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

Den `GeneratorSystem` användardefinierade typen är en klassisk Beskrivning av Hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

Det första elementet `Int` i tuppeln lagrar antalet termer $d $ i Hamiltonian och det andra elementet `(Int -> GeneratorIndex)` är en funktion som mappar ett heltals index i $ \{ 0, 1,..., d-1 \} $ till en `GeneratorIndex` användardefinierad typ som unikt identifierar varje primitiv term i Hamiltonian. Observera att genom att uttrycka samlings villkoren i Hamiltonian som en funktion i stället för som en matris `GeneratorIndex[]` , tillåter detta att du använder den här åtgärden på ett sätt `GeneratorIndex` som är särskilt användbart när du beskriver Hamiltonians med ett stort antal villkor.

Det är mycket viktigt att du inte tillämpar någon konvention om vilka primitiva termer som identifieras av `GeneratorIndex` är lätta att simulera. Primitiva termer kan till exempel vara Pauli-operatörer enligt beskrivningen ovan, men de kan också vara Fermionic Annihilation och skapande operatörer som ofta används i Quantum kemi-simulering. En `GeneratorIndex` är meningslös eftersom den inte beskriver hur tids utvecklingen på den period som det pekar på kan implementeras som en Quantum-krets.

Detta löses genom att ange en `EvolutionSet` användardefinierad typ som mappar alla, som `GeneratorIndex` hämtas från vissa kanoniska uppsättningar, till en enhetlig operatör, `EvolutionUnitary` uttryckt som en Quantum-krets. I `EvolutionSet` definieras konventionen för hur en `GeneratorIndex` är strukturerad och definierar också en uppsättning möjliga `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli-operatörs generatorer ###

Ett konkret och användbart exempel på generatorer är Hamiltonians som är en summa av Pauli-operatörer, var och en med olika koefficienter.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $ där varje $ \hat H_j $ nu har ritats från Pauli-gruppen. För sådana system tillhandahåller vi den `PauliEvolutionSet()` typ `EvolutionSet` som definierar en konvention för hur ett element i Pauli-gruppen och en koefficient kan identifieras av en `GeneratorIndex` , som har följande signatur.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

I vår kodning anger den första parametern `Int[]` en Pauli-sträng där $ \Hat I\rightarrow $0, $ \Hat X\rightarrow $1, $ \Hat Y\rightarrow $2 och $ \Hat Z\rightarrow $3. Den andra parametern `Double[]` lagrar koefficienten för Pauli-strängen i Hamiltonian. Observera att endast det första elementet i matrisen används. Den tredje parametern `Int[]` indexerar den qubits som den här Pauli-strängen agerar på och får inte ha några dubbla element. Därför kan Hamiltonian-termen $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ visas som

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`Är en funktion som mappar något `GeneratorIndex` av detta formulär till en `EvolutionUnitary` med följande signatur.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

Den första parametern representerar en tids period som kommer att multipliceras med koefficienten i den `GeneratorIndex` enhetliga utvecklingen. Den andra parametern är den qubit som registrerar de enhetliga åtgärderna på. 

### <a name="time-dependent-generators"></a>Tids beroende generatorer ###

I många fall är vi också intresserade av att utforma tids beroende generatorer som kan uppstå i Schrödinger ekvation $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $ där generatorn $ \hat H (t) $ nu är tids beroende. Det är enkelt att utöka tillägget från tids oberoende generatorer ovan till det här fallet. I stället för att ha en fast `GeneratorSystem` Beskrivning av Hamiltonian för alla tider $t $, har vi i stället den `GeneratorSystemTimeDependent` användardefinierade typen.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

Den första parametern är en kontinuerlig schema parameter $s \in [0, 1] $ och funktioner av den här typen returnerar a `GeneratorSystem` för det schemat. Observera att schema parametern kan vara linjärt relaterad till den fysiska tids parametern, t. ex. $s = t/T $, för viss total tid för simulering $T $. I allmänhet behöver detta inte vara fallet.

På samma sätt kräver en fullständig beskrivning av generatorn en `EvolutionSet` , och därför definieras en `EvolutionSchedule` användardefinierad typ.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
