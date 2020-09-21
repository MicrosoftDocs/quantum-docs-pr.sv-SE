---
title: Jordanien – Wigner-representation
description: Lär dig mer om den Jordanien-Wigner-representation som mappar Hamiltonian-operatörer till enhetliga matriser som kan vara enklare att implementera på en Quantum-dator.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833879"
---
# <a name="jordan-wigner-representation"></a>Jordanien – Wigner-representation

Andra quantized-Hamiltonians är bekvämt representerade i termer av $a ^ \dagger $ (skapas) och $a $ (Annihilation), men dessa åtgärder är inte grundläggande åtgärder på quantum-datorer.
Det innebär att om vi vill att det ska implementera dem på en Quantum-dator måste vi mappa operatörerna till enhetliga matriser som kan implementeras på en Quantum-dator.
The Jordanien – Wigner-representationen ger en sådan karta.
Andra som Bravyi – Kitaev-representation finns också och har sina egna relativa fördelar och nack delar.
Den största fördelen med den Jordanien-Wigner-representation är dess enkelhet.

Den Jordanien-Wigner-representation är rakt framåt för att bli härledd.
Kom ihåg att ett tillstånd $ \ket {0} _J $ innebär att rotations orbital $j $ är tomt och att $ \ket {1} _J $ indikerar att den är upptagen.
Det innebär att qubits kan lagra yrket i ett angivet varv orbital.
Sedan har vi $a ^ \ dagger_j \ket {0} _J = \ket {1} _J $ och $a ^ \ dagger_j \ket {1} _J = $0.
Det är enkelt att verifiera att \begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align} där $X _J $ och $Y _J $ är Pauli-$X $ och-$Y $-operatörer som agerar på qubit $j $.

>[!NOTE]
> I Q# läget $ \ket {0} $ representerar den + 1 eigenstate av $Z $-operatorn. I vissa områden av fysik $ \ket {0} $ representerar jord-och $Z eigenstate på låg energi nivå. Därför kan vissa formler skilja sig från populära litteratur.

I kemi-biblioteket använder vi $ \ket {0} $ för att representera ett intaget varv-orbital.
Detta visar att för ett enda varv-orbital är det enkelt att representera skapande-och Annihilation-operatörer i termer av enhetliga matriser som Quantum Computers förstår.
Observera att medan $X $ och $Y $ är enhetliga $a ^ \dagger $ och $a $ inte.
Vi kommer att se senare att detta inte utgör en utmaning för simulering.

Ett problem som är kvar är att medan byggnaden ovan fungerar för en enda varv-orbital, så Miss lyckas system med två eller flera rotations banor.
Eftersom Fermions är antisymmetic vet vi att $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ för alla $j $ och $k $.
Men $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).
$ $ Med andra ord fungerar inte de två skapande operatorerna som krävs.
Detta kan åtgärdas med hjälp av en enkel, om så är möjligt.
Korrigeringen är att notera att Pauli-operatörerna är naturligt inaktuella.
I synnerhet $XZ =-ZX $ och $YZ =-ZY $.
Genom att blanda $Z $-operatörer i driften av operatören kan vi därför emulera rätt anti-arbetslösare.
Den fullständiga konstruktionen är följande: 

\begin{align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iY} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iY} {2} \right). \label{eq:JW} \end{align}

Det är också enkelt att uttrycka antalet operatorer $n _j $, vad gäller Pauli-operatörer.
Thankfully, strängarna i $Z $-operatörer (kallade Wigner-strängar) avbryts efter att den här ersättningen har utförts.
Efter att ha utfört detta (och återkallar $X _jY_j = iZ_j $) har vi \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Skapa Hamiltonians i Wigner-representation

När vi har åberopat den Jordanien-Wigner-representation som översätter Hamiltonian till en summa av Pauli-operatörer rakt framåt.
Du behöver bara ersätta var och en av de $a ^ \dagger $-och $a $-operatörerna i Fermionic-Hamiltonian med strängarna för Pauli-operatörerna ovan.
När en utför denna ersättning finns det bara fem villkors klasser inom Hamiltonian.
Dessa fem klasser motsvarar de olika sätt som vi kan välja mellan $p, q $ och $p, q, r, s $ i en Body-och två-Body-termer i Hamiltonian.
Dessa fem klasser, i de fall där $p>q>r>s $ och Real värdes banor, är

\begin{align} H_ {PP} a_p ^ \dagger a_p &= \ sum_p \frac{H_ {PP}} {2} (1-Z_p) \\ \\ H_ {PQ} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{H_ {PQ}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ H_ {pqqp} n_p n_q &= \frac{H_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {PQRS} &= \frac{H_ {PQRS}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (xxxx-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Under genereringen av sådana Hamiltonians kräver bara att de här ersättnings reglerna tillämpas, så det skulle vara omöjligt för stora molekyler som kan bestå av miljon tals Hamiltonian villkor.
Alternativt kan vi automatiskt konstruera den `JordanWignerEncoding` erhållna en `FermionHamiltonian` representation av Hamiltonian.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

När Hamiltonians har skapats i det här formuläret kan vi använda en värd med Quantum Compilation-algoritmer för att kompilera den Dynamics som genereras av $e ^ {-iHt} $ till en sekvens av elementära grindar (inom vissa användar definierbara fel tolerans).
Vi diskuterar de två mest populära metoderna för Quantum simulering, qubitization och Trotter – Suzuki formler i den algoritmiska dokumentationen. Vi tillhandahåller implementeringar för båda metoderna i biblioteket för Hamiltonian-simulering.
