---
title: 'Q # standard bibliotek – algoritmer | Microsoft Docs'
description: Q#-standardbibliotek
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 91f65b05c83367c2d2ece93212369dc448d8c2a8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821022"
---
# <a name="quantum-algorithms"></a>Quantum-algoritmer #

## <a name="amplitude-amplification"></a>Amplitudförstärkning ##

*Amplitud förstärkning* är ett av de grundläggande verktygen i Quantum Computing. Det är den grundläggande idén som ligger under Grover sökning, amplitud uppskattning och många Quantum Machine Learning-algoritmer.  Det finns många varianter och i Q # tillhandahåller vi en allmän version som baseras på Oblivious amplitud-förstärkning med partiella reflektioner för att tillåta det största programmet.

Den centrala idén bakom amplitud förstärkning är att utvidga sannolikheten för att ett önskat resultat inträffar genom att utföra en följd av reflektioner.  Dessa reflektioner roterar det initiala läget närmare ett önskat mål tillstånd, ofta kallat ett märkt tillstånd.  Om sannolikheten för att mäta det initiala läget ska vara i ett markerat tillstånd är $ \sin ^ 2 (\theta) $ sedan efter att ha använt amplitud-förstärkning $m $ gånger sannolikheten att lyckas blir $ \sin ^ 2 ((2 m + 1) \theta) $.  Det innebär att om $ \theta = \ Pi/[2 (2n + 1)] $ för ett värde av $n $, kan amplitud-förstärkningen förbättra sannolikheten för att lyckas till $100\\% $ efter $n $-iterationer av amplitud-förstärkning.  Sedan $ \theta = \sin ^{-1}(\sqrt{\Pr (lyckades)}) $ betyder det att antalet iterationer som krävs för att hämta en lyckad deterministiskt är korrekt lägre än det förväntade antalet som krävs för att hitta ett markerat tillstånd som inte är deterministiskt med slumpmässig provtagning.

Varje iteration av amplitud-förstärkning kräver att två reflektions operatorer anges. Mer specifikt, om $Q $ är amplitud-förstärkningen iterera och $P _0 $ är en projektor operator på det inledande under utrymmet och $P _1 $ är projektorn på det markerade under utrymmet $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Kom ihåg att en projektor är en Hermitian-operator som har Eigenvalues $ + $1 och $0 $ och att $ (\boldone-2P_0) $ är enhetlig eftersom den har Eigenvalues som är enhets rötter (i det här fallet $ \pm $1). Som exempel kan du titta på fallet med Grover Sök med initialt tillstånd $H ^ {\otimes n} \ket{0}$ och markerat tillstånd $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ och $P _1 = \ket{m}\bra{m} $.  I de flesta program av amplitud förstärkning $P _0 $ en projektor i ett initialt tillstånd som $P _0 = \boldone-2 \ ket {\ PSI} \ bra {\ PSI} $ för vissa vektor $ \ket{\psi} $; för Oblivious amplitud amplication $P _0 $ vanligt vis projekt till många Quantum-tillstånd (d.v.s. multipliciteten hos $ + $1-eigenvalue för $P _0 $ är större än $1 $).

Logiken bakom amplitud-förstärkningen följer direkt från Eigen-dekompositionen för $Q $.  Mer specifikt, eigenvectors i $Q $ att det ursprungliga läget har icke-noll-support över kan visas som linjära kombinationer av $ + $1-eigenvectors för $P _0 $ och $P _1 $.  Mer specifikt är det ursprungliga läget för amplitud förstärkning (förutsatt att det är en $ + $1 eigenvector av $P _0 $) som kan skrivas som $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left (e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \right). $ $ Where $ \ket{\ psi_ \pm} $ eigenvectors $Q $ med Eigenvalues $e ^ {\pm 2i \ theta} $ och har bara stöd för $ + $1 eigenvectors för $P _0 $ och $P _1 $.  Det faktum att Eigenvalues är $e ^ {\pm i \theta} $ betyder att operatorn $Q $ utför en rotation i ett tvådimensionellt del utrymme som anges av de två projektorerna och det inledande tillstånd där rotations vinkeln är $2 \ theta $.  Detta är varför efter $m $-iterationer av $Q $ den lyckade sannolikheten är $ \sin ^ 2 ([2 m + 1] \theta) $.

En annan användbar egenskap som kommer från detta är att eigenvalue $ \theta $ är direkt relaterad till sannolikheten att det ursprungliga läget skulle markeras (i det fall där $P _0 $ är en projektor på endast det ursprungliga läget).  Eftersom eigenphases i $Q $ är $2 \ theta = 2 \ sin ^{-1}(\sqrt{\Pr (lyckades)}) $, följer det sedan på att om vi använder fas uppskattning i $Q $ kan vi lära dig sannolikheten för en enhetlig Quantum-procedur.  Detta är användbart eftersom det kräver kvadratiskt färre program i Quantum-proceduren för att få en bra sannolikhet än vad som annars skulle behövas.

Q # introducerar amplitud-förstärkning som en specialisering av Oblivious amplitud-förstärkning.  Oblivious amplitud-förstärkningen använder denna moniker eftersom projektorn på den ursprungliga eigenspace inte behöver vara en projektor i det ursprungliga läget.  I detta mening är protokollet Oblivious till det ursprungliga läget.  Nyckel tillämpningen av Oblivious amplitud-förstärkning är i vissa *linjära kombinationer av enhetliga* Hamiltonian-simulerings metoder, där start tillstånd är okänt men blir Entangled med en Ancilla-registrering i simulerings protokollet.  Om det här Ancilla-registret skulle mätas som ett fast värde, t. ex. $0 $, tillämpar dessa simulerings metoder den önskade enhetliga omvandlingen för återstående qubits (kallas system registret).  Alla andra mått kommer att leda till ett problem.  Oblivious amplitud-förstärkning gör att det går att öka sannolikheten för att denna mätning ska höjas till $100\\% $ med ovanstående orsak.  Dessutom motsvarar den vanliga amplitud förstärkningen det fall där system registret är tomt.  Det här är anledningen till att Q # använder Oblivious amplitud-förstärkning som dess grundläggande amplituds förstärknings subrutin.

Den allmänna rutinen (`AmpAmpObliviousByReflectionPhases`) har två kassor som vi kallar `ancillaRegister` och `systemRegister`. Den accepterar också två Oracle-uppgifter för nödvändiga reflektioner. `ReflectionOracle` fungerar bara på `ancillaRegister` medan `ObliviousOracle` fungerar gemensamt i båda registren. Indatamängden till `ancillaRegister` måste initieras till en-1-eigenstate av den första reflektions operatorn $ \boldone-2P_1 $.

Oracle förbereder vanligt vis stadiet i beräknings basen $ \ket{0...0} $. I vår implementering består `ancillaRegister` av en qubit (`flagQubit`) som styr `stateOracle` och resten av önskad ancillas. `stateOracle` tillämpas när `flagQubit` är $ \ket{1}$.

En kan också tillhandahålla Oracle `StateOracle` och `ObliviousOracle` i stället för att avspeglas via ett anrop till `AmpAmpObliviousByOraclePhases`.

Som vi nämnt är den traditionella amplitud ökningen bara ett specialfall av dessa rutiner där `ObliviousOracle` är identitets operatören och det inte finns någon system qubits (t. ex. `systemRegister` tom). Om du vill hämta faser för partiella reflektioner (t. ex. för Grover-sökning) är funktionen `AmpAmpPhasesStandard` tillgänglig. Se `DatabaseSearch.qs` för en exempel implementering av Grover-algoritmen.

Vi relaterar qubit rotations faser till reflektions operator faserna som beskrivs på papperet av [G.H. Low, I. L. Chuang](https://arxiv.org/abs/1707.05391). De fasta punkt faserna som används beskrivs i [Yoder, låg och Chuang](https://arxiv.org/abs/1409.3305) tillsammans med faserna i [låg, Yoder och Chuang](https://arxiv.org/abs/1603.03996).

I bakgrunden kan du starta från [standard-amplitud-förstärkningen](https://arxiv.org/abs/quant-ph/0005055) och sedan övergå till en introduktion till [Oblivious amplitud-förstärkning](https://arxiv.org/abs/1312.1414) och finally-generaliseringar som presenteras i [låg och Chuang](https://arxiv.org/abs/1610.06546). En bra översikt över hela det här utrymmet (som det rör Hamiltonian simulering) gavs av [Dominic bär](http://www.dominicberry.org/presentations/Durban.pdf).

## <a name="quantum-fourier-transform"></a>Quantum Fourier-transformering ##

Fourier Transform är ett grundläggande verktyg för klassisk analys och är precis lika viktigt för Quantum-beräkningar.
Dessutom överskrider *Fourier-transformeringens* effektivitet (QFT) mycket vad som är möjligt på en klassisk dator som gör det till ett av de första verktyg som du väljer när du skapar en Quantum-algoritm.

Som en ungefärlig generalisering av QFT tillhandahåller vi <xref:microsoft.quantum.canon.approximateqft>-åtgärden som möjliggör ytterligare optimering genom att rensa rotationer som inte är absolut nödvändiga för den önskade algoritmen.
Den ungefärliga QFT kräver att dyadic $Z $-rotations åtgärd <xref:microsoft.quantum.intrinsic.rfrac> samt <xref:microsoft.quantum.intrinsic.h> åtgärden.
Indata och utdata antas vara kodade i big endian encoding (lägsta bit-/qubit är till vänster, samma som [ket-notation](xref:microsoft.quantum.concepts.dirac)).
Den ungefärliga parametern $a $ fastställer rensnings nivån för $Z $-rotationer, t. ex. $a \in [0.. n] $.
I detta fall alla $Z $-rotationer $2 \ Pi/2 ^ k $ där $k > en $ tas bort från QFT-kretsen.
Det är känt att för $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. en kan vara kopplad till $\\| \operatorname{QFT} – \operatorname{AQFT} \\| < \epsilon $.
Här $\\| \cdot\\| $ är operator norm, som i det här fallet kvadratroten av den största [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) $ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritmetiska ##

Precis som det aritmetiska spelar en central roll i klassisk data behandling, är den också indispensible i Quantum Computing.  Algoritmer som Shor, Quantum simulerings metoder och många Oracular-algoritmer förlitar sig på sammanhängande aritmetiska åtgärder.  De flesta metoder för aritmetiska byggen vid Quantum egenskapsangivning-kretsar.  Den enklaste egenskapsangivning tar en klassisk in$b $ och lägger till värdet i ett Quantum-tillstånd som innehåller ett heltal $ \ket{a} $.  Matematiskt, egenskapsangivning (som vi betecknar $ \operatorname{Add} (b) $ för klassisk in$b $) har egenskapen som

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Den här grundläggande egenskapsangivning-kretsen är mer av en ökning än en egenskapsangivning.
Den kan konverteras till en egenskapsangivning som har två Quantum-indata via $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}. $ $ använda $n $ kontrollerade program av Adders av formatet \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda\_{a\_0} \left (\operatorname{Add} (1) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cdots \Lambda\_{a\_{n-1}} \left (\ operatorname {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} för $n $-bitars heltal $a $ och $b $ och additionen modulo $2 ^ n $.  Kom ihåg att notationen $ \Lambda\_x (A) $ refererar, för alla åtgärder $A $, till den kontrollerade versionen av åtgärden med qubit $x $ as Control.

På samma sätt kan en klassisk och kontrollerad multiplikation (en modulär form av som är viktig för Shor) utföras med hjälp av en liknande serie med kontrollerade tillägg: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \right \cdots\_{\Lambda\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + AX}.
\end{align} det finns en subtlety med multiplikation på quantum-datorer som du kan märka från definitionen av $ \operatorname{Mult} $ ovan.  Till skillnad från addition lagrar den Quantum-versionen av den här kretsen produkten av indata i ett hjälp register i stället för i inmatnings register.  I det här exemplet initieras registreringen med värdet $b $, men vanligt vis börjar det att ha värdet noll.  Detta krävs i eftersom det inte finns någon multiplicative-invers för General $a $ och $x $.  Eftersom alla Quantum-åtgärder sparar måttet, måste vi ha tillräckligt med information runt för att invertera multiplikationen.  Av den anledningen lagras resultatet i en separat matris.  Detta är ett exempel på hur du sparar utdata från en oåterkallelig åtgärd, som multiplikation, i ett separat register kallas "Bennette stick" efter Kalle Bennett och är ett grundläggande verktyg i både reversibel och Quantum data behandling.

Många Quantum-kretsar har föreslagits för addition och var och en har en annan kompromiss avseende antalet qubits (utrymme) och antalet grind åtgärder (tid) som krävs.  Vi går igenom två mycket utrymmes effektiva Adders nedan kallad Draper egenskapsangivning och Beauregard egenskapsangivning.

### <a name="draper-adder"></a>Draper Egenskapsangivning ###

Draper-egenskapsangivning är utan tvekan en av de mest eleganta Quantum-Adders, eftersom det direkt anropar Quantum-egenskaperna för att utföra addition.  Insikterna bakom Draper-egenskapsangivning är att Fourier-transformeringen kan användas för att översätta fas växlingar till en bit-Shift.  Därefter följer det genom att använda en Fourier-transformering, tillämpa lämpliga fas växlingar och sedan ångra Fourier-transformeringen kan du implementera en egenskapsangivning.  Till skillnad från många andra Adders som har föreslagits använder Draper-egenskapsangivning Quantum-effekter som introduceras genom Quantum Fourier-transformeringen.  Den har ingen naturlig klassisk motsvarighet.  De speciella stegen i Draper-egenskapsangivning anges nedan.

Anta att du har två $n $-bitars qubit-register som lagrar heltalen $a $ och $b $ och sedan för alla $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (aj)/2 ^ n} \ket{j}.
$ $ Om vi definierar $ $ \ket{\phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right), $ $ efter vissa algebra kan du se att $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 (a)} \otimes \cdots \otimes \ket{\phi\_n (a)}.
$ $ Sökvägen för att utföra en egenskapsangivning avmarkeras efter att du har iakttagit att summan av indata kan skrivas som $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 (a + b)} \otimes \cdots \otimes \ket{\phi\_n (a + b)}.
$ $ Heltalen $b $ och $a $ kan sedan läggas till genom att utföra rotation med styrd fas på varje qubits i nedbrytningen med hjälp av bitarna i $b $ som kontroller.

Den här utökningen kan för enklas ytterligare genom att notera att för alla heltal $j $ och reella tal $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Detta beror på att om du roterar $360 ^ {\circ} $ grader ($ 2 \ pi $ radianer) i en cirkel så slutar du exakt där du startade.  Den enda viktiga delen av $x $ för $e ^ {i2\pi x} $ är därför bråk delen av $x $.  Mer specifikt, om vi har en binär expansion av formuläret $x = y +0. x\_0x\_2 \ ldots x\_n $, $e ^ {i2\pi x} = e ^ {i2\pi (0). x\_0x\_2 \ ldots x\_{n-1})} $ och därmed $ $ \ket{\phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right). $ $ det innebär att om vi utför addition genom att öka var och en av de styrkorts faktorer i expanderingen av Fourier-transformeringen för $ \ket{a} $ krymper antalet rotationer som $k $ minskar.  Detta minskar avsevärt antalet Quantum-grindar som krävs i egenskapsangivning.  Vi betecknar Fourier Transform, Phase addition och inverterade Fourier-transformationer som utgör Draper egenskapsangivning som $ \operatorname{QFT} ^{-1} \left (\phi\\\!\operatorname{ADD}\right) \operatorname{QFT} $. En Quantum-krets som använder denna förenkling för att implementera hela processen kan visas nedan.

![Draper egenskapsangivning visas som krets diagram](~/media/draper.png)

Varje kontrollerad $e ^ {i2 \ PI/k} $ grind i kretsen refererar till en kontrollerad fas-grind.  Sådana grindar har egenskapen som finns på det qubits som de agerar på, $ \ket{00}\mapsto \ket{00}$ \ket $ \mapsto{11}i2 e ^ {ket \ PI/k} \{11}$.  Med den här kretsen kan vi utföra addition genom att inte använda ytterligare qubits förutom de som behövs för att lagra indata och utdata.

### <a name="beauregard-adder"></a>Beauregard Egenskapsangivning ###

Beauregard-egenskapsangivning är en Quantum modulär egenskapsangivning som använder Draper-egenskapsangivning för att utföra ytterligare modulo $N $ för ett godtyckligt värde med positivt heltal $N $.  Betydelsen av Quantum modulära Adders, t. ex. Beauregard-egenskapsangivning, står i stor utsträckning från användningen i modulärt exponent steg inom Shor-algoritmen för factoring.  En Quantum modulär egenskapsangivning har följande åtgärd för Quantum-ingången $ \ket{b} $ och klassisk in$a $ där $a $ och $b $ har utlovats som heltals mod $N $, vilket innebär att de är i intervallet $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{cases}.
$$

Beauregard-egenskapsangivning använder Draper egenskapsangivning, eller mer specifikt $ \phi\\\!\operatorname{ADD} $, för att lägga till $a $ och $b $ i fas.  Den använder sedan samma åtgärd för att identifiera om $a + b < N $ genom att subtrahera $N $ och testa om $a + b-N < 0 $.  Kretsen lagrar den här informationen i en hjälp qubit och lägger sedan till $N $ tillbaka registret om $a + b < N $.  Den kommer sedan att ingå i den här hjälp biten (det här steget krävs för att säkerställa att Ancilla kan avallokeras när egenskapsangivning har anropats).  Kretsen för Beauregard-egenskapsangivning anges nedan.

![Beauregard egenskapsangivning visas som krets diagram](~/media/beau.png)

Här är grinden $ \Phi\\\!\operatorname{ADD} $ tar samma formulär som $ \Phi\\\!\operatorname{ADD} $, förutom att i detta sammanhang är indatamängden klassisk i stället för Quantum.  Detta gör att de kontrollerade faserna i $ \Phi\\\!\operatorname{ADD} $ ersätts med fas grindar som sedan kan kompileras till färre åtgärder för att minska antalet qubits och antalet portar som behövs för egenskapsangivning.

Mer information finns i [M. Roetteler, Th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) och [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Uppskattning av kvantfasen ###

En särskilt viktig tillämpning av Quantum Fourier-transformeringen är att lära sig Eigenvalues av goda operatörer, ett problem som är känt som *fas uppskattning*.
Överväg en enhetlig $U $ och ett tillstånd $ \ket{\phi} $ så att $ \ket{\phi} $ är en eigenstate av $U $ med okänd eigenvalue $ \phi $, \begin{Equation} U\ket {\ Fi} = \phi\ket{\phi}.
\end{Equation} om vi bara har åtkomst till $U $ som Oracle, kan vi lära dig fasen $ \phi $ genom att använda $Z $-rotationer som tillämpas på målet för en kontrollerad åtgärd som sprids tillbaka till kontrollen.

Anta att $V $ är en kontrollerad tillämpning av $U $, till exempel \begin{align} V (\ket{0} \otimes \ket{\phi}) & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{och} V (\ket{1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket{1} \otimes \ket{\phi}.
\end{align} sedan linjärt, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket{0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket{1} \otimes \ket{\phi})} {\sqrt{2}}.
\end{align} vi kan samla in villkor för att hitta att \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align} där $R _1 $ är den som används av <xref:microsoft.quantum.intrinsic.r1>-åtgärden.
Det är på ett annat sätt att tillämpa $V $ på samma sätt som att använda $R _1 $ med en okänd vinkel, trots att vi bara har åtkomst till $V $ som Oracle.
För resten av denna diskussion kommer vi därför att diskutera fasens uppskattning i termer av $R _1 (\phi) $, som vi implementerar med hjälp av så kallade *fas Kickback*.

Eftersom kontroll-och mål registret fortfarande är untangled efter den här processen kan vi återanvända $ \ket{\phi} $ som mål för ett kontrollerat program med $U ^ $2 för att förbereda en andra kontroll qubit i tillstånd $R _1 (2 \phi) \ket{+} $.
Om du fortsätter på det här sättet kan vi hämta ett register över formatet \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket{0} + \exp (i 2 ^ {j} \phi) \ket{1}\right) \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align} där $n $ är antalet precisions bitar som vi behöver, och där vi har använt ${} \propto {}$ för att indikera att vi har ignorerat normaliserings faktorn för $ 1/\sqrt{2 ^ n} $.

Om vi antar att $ \phi = 2 \pi p/2 ^ k $ för ett heltal $p $, känner vi igen detta som $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, där $p _j $ är $j ^ {\textrm{th}} $ bit $2 \pi $.
Genom att använda det angränsande av Quantum Fourier-transformeringen får vi därför en binär representation av fasen som är kodad som ett Quantum-tillstånd.

I Q # implementeras detta av <xref:microsoft.quantum.characterization.quantumphaseestimation>-åtgärden, som tar en <xref:microsoft.quantum.oracles.discreteoracle> implementerande applikation av $U ^ m $ som en funktion av positiva heltal $m $.
