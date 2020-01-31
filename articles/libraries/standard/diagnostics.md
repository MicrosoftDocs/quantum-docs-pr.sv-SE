---
title: 'Q # standard bibliotek – diagnostik | Microsoft Docs'
description: 'Q # standard bibliotek – diagnostik'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 67ec6780d8cbbda7223d46026a9df97cebc92b33
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820988"
---
# <a name="diagnostics"></a>Diagnostik #

Precis som med klassisk utveckling är det viktigt att kunna diagnostisera misstag och fel i Quantum-program.
Standard biblioteken för Q # är en mängd olika sätt att säkerställa att Quantum program är korrekt, enligt beskrivningen i <xref:microsoft.quantum.techniques.testing-and-debugging>.
Den här supporten är i stort sett i form av funktioner och åtgärder som antingen instruerar mål datorn att tillhandahålla ytterligare diagnostikinformation till värd programmet eller utvecklaren, eller tillämpa rätt villkor och invarianter som uttrycks av funktions-eller åtgärds anropet.

## <a name="machine-diagnostics"></a>Machine Diagnostics ##

Diagnostik med klassiska värden kan erhållas med hjälp av funktionen <xref:microsoft.quantum.intrinsic.message> för att logga ett meddelande på ett dator beroende sätt.
Som standard skriver detta strängen till-konsolen.
<xref:microsoft.quantum.intrinsic.message> är tillsammans med interpolerade strängar och gör det enkelt att rapportera diagnostikinformation om klassiska värden:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` har signatur `(String -> Unit)`, som visar att ett fel söknings logg meddelande inte kan observeras inifrån Q #.

<xref:microsoft.quantum.diagnostics.dumpmachine>-och <xref:microsoft.quantum.diagnostics.dumpregister>-callables instruerar mål datorerna att tillhandahålla diagnostikinformation om alla aktuella allokerade qubits eller om ett särskilt register över qubits.
Varje måldator varierar i vilken diagnostikinformation som anges som svar på en dump-instruktion.
Den fullständiga mål datorn för [tillstånds simulatorn](xref:microsoft.quantum.machines.full-state-simulator) tillhandahåller till exempel värd programmet med den tillstånds vektor som används internt för att representera ett register över qubits.
Som jämförelse ger [Toffoli Simulator](xref:microsoft.quantum.machines.toffoli-simulator) -mål datorn en enkel klassiskt bit för varje qubit.

 Om du vill veta mer om [full State simulators](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` utdata tar du en titt på avsnittet dumpa funktioner i [artikeln test och fel sökning](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Fakta och intyg ##

Som du ser i [testa och felsöka](xref:microsoft.quantum.techniques.testing-and-debugging), kan en funktion eller åtgärd med signaturen `Unit -> Unit` respektive `Unit => Unit`markeras som ett *enhets test*.
Varje enhets test består vanligt vis av ett litet Quantum-program, tillsammans med ett eller flera villkor som kontrollerar att programmet är korrekt.
Dessa villkor kan komma i form av antingen _fakta_, som kontrollerar värdena för deras indata, eller _intyg_, som kontrollerar tillstånden för en eller flera qubits som skickas som indata.

`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` representerar till exempel det matematiska faktum att $1 + 1 = $2, medan `AssertQubit(One, qubit)` representerar villkoret som mäter `qubit` returnerar en `One` med säkerhet.
I det förra fallet kan vi kontrol lera att villkoret är korrekt, men i det senare måste vi känna till något om status för qubit för att utvärdera försäkran.

Standard biblioteken för Q # innehåller flera olika funktioner för att representera fakta, inklusive:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Testa qubit-tillstånd ###

I praktiken förlitar sig på att de klassiska simuleringarna av Quantum Mechanics inte behöver följa [no-klonings-satsen](https://arxiv.org/abs/quant-ph/9607018), så att vi kan göra icke-fysiska mätningar och intyg när de använder en simulator för vår mål dator.
Därför kan vi testa enskilda åtgärder på en klassisk Simulator innan du distribuerar på maskin vara.
På mål datorer som inte tillåter utvärdering av intyg kan anrop till <xref:microsoft.quantum.intrinsic.assert> ignoreras på ett säkert sätt.

Mer allmänt sett är <xref:microsoft.quantum.intrinsic.assert> åtgärden som mäter att de tilldelade qubits i den aktuella Pauli-basen alltid har det aktuella resultatet.
Om kontrollen Miss lyckas avslutas körningen genom att anropa `fail` med det aktuella meddelandet.
Den här åtgärden är inte implementerad som standard. simulatorer som har stöd för den bör tillhandahålla en implementering som utför körnings kontroll.
`Assert` har signatur `((Pauli[], Qubit[], Result, String) -> ())`.
Eftersom `Assert` är en funktion med en tom tupel som Utdatatyp, kan inga effekter från att ha anropade `Assert` vara synliga i ett Q #-program.

Funktionen <xref:microsoft.quantum.intrinsic.assertprob> funktion förutsätter att mätning av de tilldelade qubits i den aktuella Pauli-grunden har det resultat som har givit den sannolikheten, inom viss tolerans.
Toleransen är additiv (t. ex. `abs(expected-actual) < tol`).
Om kontrollen Miss lyckas avslutas körningen genom att anropa `fail` med det aktuella meddelandet.
Den här åtgärden är inte implementerad som standard. simulatorer som har stöd för den bör tillhandahålla en implementering som utför körnings kontroll.
`AssertProb` har signatur `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`. Den första av `Double` parametrar ger den önskade sannolikheten för resultatet och den andra som toleransen.

Vi kan göra mer än att kontrol lera en enda mätning, med hjälp av att den klassiska information som används av en simulator för att representera det interna läget för en qubit är lämpar att kopiera, så att vi inte behöver utföra någon mätning för att testa vår kontroll.
I synnerhet gör detta att vi kan ta del av *inkompatibla* mått som skulle vara omöjliga vid den faktiska maskin varan.

Anta att `P : Qubit => Unit` är en åtgärd som är avsedd att förbereda status $ \ket{\psi} $ när indatamängden är i läget $ \ket{0}$.
Låt $ \ket{\psi '} $ vara det faktiska tillstånd som förberetts av `P`.
Sedan returnerar $ \ket{\psi} = \ket{\psi '} $ om och endast om mätningen $ \ket{\psi '} $ i axeln som beskrivs av $ \ket{\psi} $ alltid returnerar `Zero`.
Det vill säga \begin{align} \ket{\psi} = \ket{\psi '} \text{om och bara om} \braket{\psi | \psi '} = 1.
\end{align} med de primitiva åtgärder som definierats i inledning kan vi direkt utföra en mätning som returnerar `Zero` om $ \ket{\psi} $ är en eigenstate av en av Pauli-operatörerna.


Åtgärden <xref:microsoft.quantum.diagnostics.assertqubit> ger en särskilt praktisk stenografisk funktion i det fall då vi vill testa undersökningen $ \ket{\psi} = \ket{0}$.
Detta är vanligt, till exempel när vi har gjort en uncompute för att returnera Ancilla qubits till $ \ket{0}$ innan de släpps.
Att kontrollera mot $ \ket{0}$ är också användbart när vi vill att två tillstånds förberedelser `P` och `Q` åtgärder ska kunna förbereda samma tillstånd, och när `Q` stöder `Adjoint`.
Särskilt,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

I allmänhet är det dock inte säkert att vi har åtkomst till intyg om tillstånd som inte sammanfaller med eigenstates av Pauli-operatörer.
Till exempel, $ \ket{\psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ är inte en eigenstate av någon Pauli-Operator, så att vi inte kan använda <xref:microsoft.quantum.intrinsic.assertprob> för att unikt fastställa att ett tillstånd $ \ket{\psi '} $ är lika med $ \ket{\psi} $.
I stället måste du dela upp intyget $ \ket{\psi '} = \ket{\psi} $ i antaganden som kan testas direkt med hjälp av de primitiver som stöds av vår Simulator.
Det gör du genom att låta $ \ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ för komplexa tal $ \alpha = a\_r + a\_i $ och $ \beta $.
Observera att det här uttrycket kräver fyra reella tal $\{ett\_r, en\_i, b\_r, b\_i\}$ för att ange, eftersom varje komplext tal kan uttryckas som summan av en verklig och en imaginär del.
På grund av den globala fasen kan vi dock välja $a\_i = $0, så att vi bara behöver tre reella siffror för att unikt ange ett qubit tillstånd.

Därför måste vi ange tre intyg som är oberoende av varandra för att fastställa det tillstånd som vi förväntar sig.
Vi gör detta genom att ta reda på sannolikheten för att observera `Zero` för varje Pauli-mätning, som har getts $ \alpha $ och $ \beta $, och som garanterar var och en oberoende.
Låt $x $, $y $ och $z $ vara `Result` värden för Pauli $X $, $Y $ och $Z $.
Sedan använder du funktionen sannolikhet för Quantum-mätningar, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_\\\\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).
\end{align}

Åtgärden <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementerar de här försäkrarna om $ \alpha $ och $ \beta $ som värden av typen <xref:microsoft.quantum.math.complex>.
Detta är användbart när det förväntade läget kan beräknas matematiskt.

### <a name="asserting-equality-of-quantum-operations"></a>Kontroll av jämställdhet mellan Quantum-åtgärder ###

Hittills har vi varit intresserade av test åtgärder som är avsedda att förbereda särskilda tillstånd.
Vi är ofta intresserade av hur en åtgärd fungerar för godtyckliga indata i stället för en enda fast inmatning.
Anta till exempel att vi har implementerat en åtgärd `U : ((Double, Qubit[]) => () : Adjoint)` som motsvarar en familj med enhetliga operatörer $U (t) $, och har angett ett explicit `adjoint` block i stället för att använda `adjoint auto`.
Vi kan vara intresserade av att förutsätta att $U ^ \dagger (t) = U (-t) $, som förväntat om $t $ representerar en utvecklings tid.

Det finns i stort sett två olika strategier som vi kan följa för att göra den försäkran att två åtgärder `U` och `V` fungerar identiskt.
Först kan vi kontrol lera att `U(target); (Adjoint V)(target);` bevarar varje tillstånd med en specifik grund.
För det andra kan vi kontrol lera att `U(target); (Adjoint V)(target);` som agerar på hälften av ett Entangled-tillstånd bevarar entanglement.
Dessa strategier implementeras av Canon-åtgärderna <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> respektive <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>.

> [!NOTE]
> Den refererade kontrollen som diskuteras ovan fungerar baserat på [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), ett matematiskt ramverk som relaterar åtgärder på $n $ qubits till Entangled-tillstånd på $2n $ qubits.
> I synnerhet representeras identitets åtgärden på $n $ qubits av $n $-kopior av Entangled-tillstånd $ \ket{\ beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$.
> Åtgärden <xref:microsoft.quantum.preparation.preparechoistate> implementerar den här isomorphism och förbereder ett tillstånd som representerar en specifik åtgärd.

Den här typen av strategier särskiljs ungefär i en tid – utrymmes kompromisser.
Att gå igenom varje ingångs tillstånd tar ytterligare tid, medan du använder entanglement som referens kräver att du lagrar ytterligare qubits.
I de fall där en åtgärd implementerar en klassisk klassisk åtgärd, så att vi bara är intresse rad av dess beteende i beräknings bas staterna, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testerna är likvärdiga med denna begränsade uppsättning indata.

> [!TIP]
> Iterationen över indatamängds tillstånd hanteras av uppräknings åtgärder <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> och <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Dessa åtgärder är användbara för att tillämpa en åtgärd för varje element i kartesiska-produkten mellan två eller flera uppsättningar.

Det är dock viktigt att de två metoderna testar olika egenskaper för de åtgärder som utförs under undersökning.
Eftersom den på plats-kontrollen anropar varje åtgärd flera gånger, en gång för varje ingångs tillstånd, kan eventuella slumpmässiga val och mått resultat ändras mellan anrop.
Den refererade kontrollen anropar däremot varje åtgärd exakt en gång, så att den kontrollerar att åtgärderna är lika *i en enda bild*.
Båda dessa tester är användbara för att säkerställa att Quantum program är korrekta.


## <a name="further-reading"></a>Mer läsning ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
