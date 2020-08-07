---
title: Quantum-karakterisering och statistik
description: Lär dig hur mätnings statistik från fas uppskattningar används för att beräkna resultat värden i Quantum-programmering.
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0090fb2b9ac5f3c9d195a3ab02dcd21c848d8ef7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868635"
---
# <a name="quantum-characterization-and-statistics"></a>Quantum-karakterisering och statistik #

Det är viktigt att kunna karakterisera effekterna av åtgärder för att utveckla användbara Quantum-algoritmer.
Detta är en utmaning eftersom varje mätning av ett Quantum-system ger högst en information.
För att kunna lära sig en eigenvalue, så att det blir ett Quantum-tillstånd, måste resultatet av många mätningar sammanföras tillsammans så att användaren kan få de många bitar av information som krävs för att representera dessa begrepp.
Quantum State är särskilt vexing eftersom [no-kloningsing satsen](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) säger att det inte finns något sätt att lära sig ett godtyckligt Quantum-tillstånd från en enda kopia av tillståndet, eftersom det gör att du kan göra kopior av tillståndet.
Den här döljande av Quantum-tillstånd från användaren återspeglas i det faktum att Q# inte visar eller ens definierar vad ett tillstånd *är* till Quantum-program.
Vi närmar sig en Quantum-karakterisering genom att behandla drift och tillstånd som svart ruta. den här metoden delar mycket gemensamt med experiment metoden för Quantum-karakterisering, verifiering och validering (QCVV).

Karakteriseringen skiljer sig från många av de andra bibliotek som beskrivits tidigare.
Målet här är mindre för att lära sig att lära sig klassisk information om systemet, i stället för att utföra en enhetlig omvandling i en tillstånds vektor.
Dessa bibliotek måste därför blanda både klassisk och Quantum informations bearbetning.


## <a name="iterative-phase-estimation"></a>Uppskattning av iterativ fas ##

Om du visar Quantum-programmering i termer av Quantum-karakterisering föreslås ett användbart alternativ för uppskattning av Quantum-fasen.
I stället för att förbereda en $n $-qubit-register för att innehålla en binär representation av fasen som i en uppskattning av Quantum-fasen, kan vi Visa fas uppskattning som den process genom vilken en *klassisk* agent lär sig egenskaper för ett Quantum-system genom mätningar.
Vi fortsätter som i Quantum-fallet genom att använda fas Kickback för att aktivera program med en svart Box-åtgärd till rotationer med en okänd vinkel, men kommer att mäta Ancilla-qubit som vi roterar i varje steg direkt efter rotationen.
Detta har fördelen att vi bara behöver en enda ytterligare qubit för att utföra fasen Kickback som beskrivs i Quantum-fallet, eftersom vi sedan lär dig fasen från Mät resultaten vid varje steg på ett iterativt sätt.  
Var och en av de metoder som föreslås nedan använder en annan strategi för att utforma experiment och olika data bearbetnings metoder för att lära dig fasen.  De har en unik fördel som sträcker sig från att ha rigorösa fel gränser, till förmåga att ta med tidigare information, tolerera fel eller köra på minnes limitted klassiska datorer.

I att diskutera iterativa fas uppskattningar kommer vi att betrakta en enhetlig $U $ som en svart Box-åtgärd.
Som det beskrivs i avsnittet om Oracle i [data strukturer](xref:microsoft.quantum.libraries.data-structures), kan Q# Canon modellera sådana åtgärder av den <xref:microsoft.quantum.oracles.discreteoracle> användardefinierade typen som definieras av tuple-typen `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
Konkret, om `U : DiscreteOracle` , `U(m)` implementerar $U ^ m $ för `m : Int` .

Med den här definitionen på plats fortsätter varje steg i upprepnings fas uppskattningen genom att förbereda en tilläggs qubit i $ \ket{+} $ State tillsammans med det inledande tillstånd $ \ket{\phi} $ som vi antar är en [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) av $U (m) $, d.v.s. $U (m) \ket{\phi} = e ^ {im\phi} \ ket {\ Phi} $.  
En kontrollerad tillämpning av `U(m)` används sedan som förbereder status $ \left (R \_ 1 (m \phi) \ket{+} \right) \ket{\phi} $.
Som i Quantum-fallet är effekten av en kontrollerad tillämpning av Oracle `U(m)` exakt densamma som effekten av att tillämpa $R _1 $ för den okända fasen på $ \ket{+} $, så att vi kan beskriva effekterna av $U $ på det här enklare sättet.
Algoritmen roterar sedan kontrollen qubit genom att använda $R _1 (-m\theta) $ för att hämta ett tillstånd $ \ket{\psi} = \left (R \_ 1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
Den hjälp qubit som används som en kontroll för `U(m)` mäts sedan i $X $-basen för att få en enda klassisk `Result` .

I det här läget är det ett klassiskt statistiskt problem med att konstruera om fasen från `Result` värdena som erhålls genom iterativ fas uppskattning.
Att hitta värdet för $m $ som maximerar den information som erhålls, med en fast härlednings metod, är bara ett problem i statistiken.
Vi understryker detta genom att en kort beskrivning av uppskattning av iterativa faser på en teoretisk nivå i Bayesian parameter bedömning innan du fortsätter med att beskriva de statistiska algoritmer som finns i Q# Canon för att lösa detta problem med den här klassiska lösningen.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Uppskattning av iterativa faser utan Eigenstates ###

Om det finns ett indata-tillstånd som inte är en eigenstate, vilket är att anta att om $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $, så guidar processen för fas uppskattning icke-deterministiskt Quantum State mot en enda energi eigenstate.  Den eigenstate som den slutligen konvergerar till är den eigenstate som är mest sannolik för att producera den observerade `Result` .

Mer specifikt utför ett enda steg i PE följande icke-enhetliga omvandling i en tillstånds \begin{align} \ sum_j \sqrt{\Pr (\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \Ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \sum \_ j \Pr (\text{result} | \phi \_ j)}}.
\end{align} eftersom den här processen itereras över flera `Result` värden, eigenstates som inte har de maximala värdena $ \ prod_k \pr (\text{result} \_ k | \phi \_ j) $ kommer att döljas exponentiellt.
Som ett resultat kommer processen att konvergera till tillstånd med en enda eigenvalue om experimenten väljs korrekt.

Bayes ' satsen rekommenderar ytterligare att det tillstånd som resulterar från fas uppskattning skrivs i formatet \begin{align} \frac{\sqrt{\Pr (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \ket{\phi j} \_ } {\sqrt{\Pr (\phi \_ j) \Sum j \Pr \_ (\text{result} | \phi \_ j)}} = \ sum_j \sqrt{\Pr (\phi \_ j | \text{result})} \ket{\phi \_ j}.
\end{align} här $ \Pr (\phi \_ j | \text{result}) $ kan tolkas som sannolikheten att en skulle anskriva till varje hypotes om den eigenstates som ges:

1. kunskap om Quantum State före mätning,
2. kunskaper om eigenstates i $U $ och,
3. kunskaper om Eigenvalues för $U $.

Inlärning dessa tre saker är ofta exponentiellt hårda på en klassisk dator.
Verktyget för fas uppskattning uppstår i ingen liten utsträckning från det faktum att det kan utföra en sådan Quantum inlärning-uppgift utan att veta något av dem.
Fas uppskattning av den här orsaken visas i ett antal Quantum-algoritmer som ger exponentiell speedups.

### <a name="bayesian-phase-estimation"></a>Bayesian fas uppskattning ###

> [!TIP]
> Mer information om Bayesian fas uppskattning i praxis finns i [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) -exemplet.

Idén med uppskattning av Bayesian-fasen är enkel.
Du samlar in mått statistik från fas beräknings protokollet och bearbetar sedan resultaten med Bayesian-härledning och ger en uppskattning av parametern.
Den här bearbetningen ger dig en uppskattning av eigenvalue samt osäkerheten i beräkningen.
Du kan också utföra anpassningsbara experiment och använda tidigare information.
Metoden restitutionssystem är att den är i beräknings krävande.

Om du vill förstå hur den här Bayesian-härledningen fungerar, bör du tänka på att bearbeta ett enda `Zero` resultat.
Observera att $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, så att $ \ket{+} $ är den enda positiva eigenstate för $X $ som motsvarar `Zero` .
Sannolikheten för att `Zero` ett [ `PauliX` mått](xref:microsoft.quantum.concepts.pauli) på den första qubit har fått ett indatamängds värde $ \ket{\psi}\ket{\phi} $ är således \begin{Equation} \Pr (\texttt{Zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} i händelse av iterativ fas uppskattning, vi har den $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, till exempel \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: fas-Est-sannolikhet}.
\end{align}, det vill säga en iterativ fas uppskattning av hur svängnings frekvensen för en Sinusoidal-funktion fungerar, med möjlighet att vända en följd med en förskjutning som anges av den sinusoid.
Efter traditionell klassisk terminologi kallar vi $ \eqref{EQ: Phase Est-sannolikhet} $ *funktionen sannolikhet* för iterativa fas uppskattningar.

Efter att ha observerat en `Result` från sannolikhets funktionen iterativa fas bedömning kan vi sedan använda Bayes ' Rule för att fastställa vad vi bör tro för att följa denna observations fas.
Betong, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation} där $d \in \\ {\texttt{Zero}, \texttt{One} \\ } $ är a `Result` , och där $ \Pr (\phi) $ beskriver vår tidigare övertygelse om $ \phi $.
Detta gör att den iterativa arten av iterativa fas uppskattningen är explicit, eftersom den bakre fördelningen $ \Pr (\phi | d) $ beskriver vår övertygelse omedelbart före vår observation av Next `Result` .

Vi kan när som helst under den här proceduren rapportera den fas $ \hat{\phi} $ som är härledd av klassisk kontrollant som \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \text{data}] = \int \phi \Pr (\phi | \text{data}) {\mathrm d} \phi, \end{Equation} där $ \text{data} $ står för hela posten för alla `Result` värden som hämtas.

Exakt Bayesian-härledning är i praktiken indragbar.
För att se det här vill vi veta en $n $-bitars variabel $x $.
Den tidigare distributionen $ \Pr (x) $ har stöd för över $2 ^ n $ hypotetiska värden för $x $.
Det innebär att om vi behöver en mycket exakt uppskattning av $x $ kan Bayesian-fasen uppskattning kräva minnes-och bearbetnings tid.
När det gäller vissa program, till exempel Quantum-simulering, utesluter limitted-noggrannheten inte sådana metoder som andra program, till exempel Shor, kan inte använda en exakt Bayesian-härledning inom sitt fas beräknings steg.  Därför ger vi även implementeringar för ungefärliga Bayesian-metoder, till exempel [slumpmässig stegvis uppskattning (RWPE)](xref:microsoft.quantum.research.characterization.randomwalkphaseestimation) och även icke-Bayesian metoder som [robust fas uppskattning](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Robust fas uppskattning ###

En maximal återställnings period i *efterhand* Bayesian av en fas uppskattning från Mät resultaten är exponentiellt hårt i värsta fall. Därför kan de flesta praktiska fas uppskattnings algoritmer offra viss kvalitet i återuppbyggnaden, i utbyte mot en mängd av den klassiska efter bearbetningen som i stället skalas polynom med antalet mätningar som görs.

Ett exempel med ett effektivt klassiskt steg efter bearbetning är [algoritmen för den robusta fasen för fas uppskattning](https://arxiv.org/abs/1502.02677), med signaturen och de inmatningar som anges ovan. Det förutsätter att inmatade svarta rutor $U $ paketeras som `DiscreteOracle` typ, och därför endast frågor med heltals behörighet för kontrollerade-$U $. Om indatamängden i `Qubit[]` registret är en eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ PSI} $, returnerar algoritmen robust fas uppskattning en uppskattning $ \hat{\phi}\in [-\pi, \pi) $ av $ \phi $ som en `Double` .

Den viktigaste funktionen i robust fas uppskattning, som delas med de flesta andra användbara varianter, är att rekonstruktions kvaliteten för $ \hat{\phi} $ är i en viss Heisenberg-begränsad. Det innebär att om avvikelsen för $ \hat{\phi} $ från det sanna värdet är $ \sigma $ skalas $ \sigma $ i proportion till det totala antalet frågor som $Q $ gjorde till styrd-$U $, t. ex. $ \sigma = \mathcal{O} (1/Q) $. Nu varierar definitionen av avvikelse mellan olika algoritmer för bedömning. I vissa fall kan det innebära att minst $ \mathcal{O} (1) $ sannolikhet, uppskattnings felet $ | \hat{\phi}-\phi | \_ \circ\le \sigma $ på vissa cirkel mått $ \circ $. För robust fas uppskattning är avvikelsen exakt var Ian sen $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [(\mod \_ {2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $ om vi avbryter periodiska faser till ett enda ändligt intervall $ (-\pi, \pi] $. Mer exakt uppfyller standard avvikelsen i robust fas uppskattningen $ $ \begin{align} 2,0 \pi/Q \le \sigma \le 2 \ Pi/2 ^ {n} \le 10.7 \ PI/Q, \end{align} $ $ där den nedre gränsen uppnås inom gränsen på asymptotically Large $Q $ och den övre gränsen garanteras även för små urvals storlekar.  Observera att $n $ som har valts av `bitsPrecision` indatatypen, vilket implicit definierar $Q $.

Andra relevanta uppgifter inkluderar, t. ex. den små utrymmes kostnaden på bara $1 $ Ancilla qubit, eller att proceduren är icke-adaptiv, vilket innebär att den nödvändiga sekvensen av Quantum experiment är oberoende av de mellanliggande Mät resultat. I det här och kommande exempel där valet av algoritmen för fas uppskattning är viktigt bör en bör hänvisa till dokumentationen, till exempel @"microsoft.quantum.characterization.robustphaseestimation" och de refererade publikationerna, för att få mer information och för deras implementering.

> [!TIP]
> Det finns många exempel där robust fas uppskattning används. För fas uppskattning när du extraherar mark tillstånds energin för olika fysiska system kan du se exempel på [ **H2-simulering** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line), [ **SimpleIsing** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)och [ **Hubbard Model** -exemplet](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Kontinuerliga Oracle ###

Vi kan också generalisera från den Oracle-modell som används ovan för att tillåta löpande Oracle, som modelleras av typen Canon <xref:microsoft.quantum.oracles.continuousoracle> .
Tänk på att i stället för en enda enhetlig operatör $U $, har vi en familj med enhetliga operatörer $U (t) $ för $t \in \mathbb{R} $ så att $U (t) U (s) $ = $U (t + s) $.
Detta är en svagare instruktion än i det diskreta fallet eftersom vi kan konstruera en <xref:microsoft.quantum.oracles.discreteoracle> genom att begränsa $t = m \, \delta t $ för vissa fasta $ \delta t $.
I [sten satsen](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ för en viss operator $H $, där $ \exp $ är matrisen exponent enligt beskrivningen i [avancerade matriser](xref:microsoft.quantum.concepts.matrix-advanced).
En eigenstate $ \ket{\phi} $ $H $ så att $H \ket{\phi} = \phi \ket{\phi} $ också är en eigenstate av $U (t) $ för alla $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

Exakt samma analys som diskuteras vid [uppskattning av Bayesian-fasen](#bayesian-phase-estimation) kan tillämpas och sannolikhets funktionen är exakt densamma för den här mer generella Oracle-modellen: $ $ \Pr (\texttt{Zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} {2} \right).
$ $ Om $U $ är en simulering av en dynamisk generator, vilket är fallet för [simulering av Hamiltonian](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), tolkar vi $ \phi $ som energi.
Med hjälp av fas uppskattning med kontinuerliga frågor kan vi alltså lära sig det simulerade [energi spektrumet av molekyler](https://arxiv.org/abs/quant-ph/0604193), [material](https://arxiv.org/abs/1510.03859) eller [fält basreaktionsteorier](https://arxiv.org/abs/1111.3633v2) utan att behöva kompromissa med valet av experiment genom att kräva att $t $ måste vara ett heltal.

### <a name="random-walk-phase-estimation"></a>Beräkning av slumpmässig stegvis fas ###

Q#ger en användbar uppskattning av Bayesian-fasens uppskattning avsedd för användning nära Quantum-enheter som fungerar genom att en slumpmässig genom gång av data posten hämtas från en iterativ fas uppskattning.
Den här metoden är både anpassningsbar och helt deterministisk, vilket ger optimal skalning av fel i den uppskattade fasen $ \hat{\phi} $ med mycket låga minnes omkostnader.

Protokollet använder en ungefärlig Bayesian-härlednings metod som förutsätter att den tidigare distributionen är Gaussisk.
Detta Gaussisk-antagande gör att vi kan använda en analys formel för experimentet som minimerar den bakre avvikelsen.
Algoritmen, baserat på resultatet av experimentet, byter uppskattningen av $ \phi $ till vänster eller höger med ett fördefinierat belopp och minskar avvikelsen med ett fördefinierat belopp.
Det här medelvärdet och avvikelsen ger all information som behövs för att ange en Gaussisk före $ \phi $ för nästa experiment.
Oväntade Mät fel eller det sanna resultatet är i början av den första föregående, kan orsaka att metoden Miss lyckas.
Den återställs från problem genom att utföra experiment för att testa om det aktuella medelvärdet och standard avvikelsen är lämpliga för systemet.
Om de inte är det gör algoritmen ett inverterat steg i processen och processen fortsätter.
Med möjligheten att gå baklänges kan algoritmen även lära sig även om den inledande föregående standard avvikelsen är inapropriately liten.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmer för att anropa fas uppskattning ##

Varje fas uppskattnings åtgärd som tillhandahålls med Q# Canon tar en annan uppsättning indata som Parameters ATS till den kvalitet som vi tar emot från den slutliga uppskattningen $ \hat{\phi} $.
Dessa olika indata, men alla delar flera indata, så att partiell program över kvalitets parametrarna resulterar i en gemensam signatur.
Den <xref:microsoft.quantum.characterization.robustphaseestimation> åtgärd som diskuteras i nästa avsnitt har till exempel följande signatur:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision`Indatamängden är unik för `RobustPhaseEstimation` , medan `oracle` och `eigenstate` är i vanliga.
Som det visas i **H2Sample**kan en åtgärd på detta sätt acceptera en upprepnings uppskattnings algoritm med indata från formuläret `(DiscreteOracle, Qubit[]) => Unit` så att en användare kan ange godtyckliga algoritmer för fas uppskattning:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Dessa algoritmer för myriaden-bedömning är optimerade för olika egenskaper och indataparametrar, vilket måste förstås för att göra det bästa valet för mål programmet. Till exempel är vissa algoritmer för fas uppskattning anpassningsbara, vilket innebär att framtida steg styrs klassiskt av mät resultaten i föregående steg. Vissa kräver möjligheten att exponentiate den svarta Box-gruppen av andra verkliga befogenheter, och andra kräver bara heltals befogenheter, men det går bara att lösa en fas Beräknad modulo $2 \ PI $. Vissa kräver många hjälp qubits och andra kräver bara en.

På samma sätt går det bra att använda slumpmässig stegvisa beräknings steg på samma sätt som för andra algoritmer som medföljer Canon:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
