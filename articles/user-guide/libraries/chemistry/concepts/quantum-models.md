---
title: Quantum-modeller för elektroniska system
description: Lär dig hur molekylbaserade elektroniska system simuleras med Quantum-modellering.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: c12ab277f06bed61991a26af96953ccdbf72b642
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856225"
---
# <a name="quantum-models-for-electronic-systems"></a>Quantum-modeller för elektroniska system

För att kunna simulera elektroniska system måste vi först börja med att ange Hamiltonian, som kan hittas av den kanoniska kvantifieringsfel-proceduren som beskrivs ovan.
Mer specifikt, för $N _e $ electrons med Momenta $p _i $ (i tre dimensioner) och Mass $m _e $ och positions vektorer $x _i $ tillsammans med probiteringen $Z _k e $ på positionerna $y _k $, Hamiltonian-operatorn läser \begin{Equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2 m \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\sum \_ {i, k} \frac{Z: \_ ^ 2} {| \hat{x} \_ i-{y} \_ k |} + \frac {1} {2} \ sum_ {k\ne k '} \frac{Z \_ kZ \_ {k '} e ^ 2} {| y \_ k-y \_ k ' |}. \label{EQ: Ham} \end{Equation} de Momenta operatorerna $ \hat{p} \_ i ^ 2 $ kan visas i real tid som Laplacian-operatörer, d.v.s. $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\partial \_ {y \_ i} ^ 2-\partial \_ {z \_ i} ^ 2 $.
Här har vi gjort det enklare att utföra antagandet att kärnorna är i vila för molekylen.
Detta kallas för Born-Oppenheimer uppskattning och är i så fall giltigt för energi spektrumet för låg energi i $ \hat{H} $ eftersom Electron massa är cirka $1/1836 $ massan av en Proton.
Den här Hamiltonian-operatören kan enkelt hittas genom att skriva ut energin för ett system med $N \_ e $ electrons och tillämpa den kanoniska kvantifieringsfel-processen som beskrivs i [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

För att kunna konstruera den enhetliga mat ris representationen för $e ^ {-i\hat {H} t} $ måste vi representera operatorn $ \hat{H} $ som en matris.
För detta måste vi välja ett koordinatsystem eller en grund för att representera problemet i.
Om t. ex. $ \ psi_j $ är en uppsättning med rätvinkliga bas funktioner för $N _e $ electrons kan vi definiera matrisen

\begin{Equation} H \_ {i, j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \psi ^ { \* } \_ i (x \_ 1) \hat{H} \psi \_ j (x \_ 2) \dd ^ 3x \_ 1 \dd ^ 3x \_ 2. \ Label {EQ: discreteHam} \end{Equation}

I princip är operatorn $ \hat{H} $ obunden och fungerar inte på ett begränsat dimensions utrymme, matrisen med element $H \_ \{ i j \} $ ovan.
Det innebär att fel uppstår vid plockning för små av grund uppsättningarna. en stor grund kan dock göra det möjligt att simulera den kemiska dynamiken.
Av den anledningen är det viktigt att välja en grund som kan vara ett koncist problem för att lösa det elektroniska struktur problemet.

Det finns många lämpliga baseer som kan användas och valet av bra grund för att passa problemet är mycket av den som är en del av Quantum kemi.
De enklaste de här bas uppsättningarna är t. ex. Slater (sluta) som är (rätvinkliga) lösningar till Schrödinger-ekvationen (t. ex. eigenfunctions av $ \hat{H} $) för väte-liknande atomer.
Andra grund uppsättningar, t. ex. plan vågor eller banor med Real utrymme, kan användas och mer information finns i den undrar läsaren till standard texten ["molekylen Electronic-Structure teori"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) av Helgaker.

Även om de tillstånd som används i modellen ovan kan verka godtyckliga, begränsar Quantum Mechanics begränsningar för de tillstånd som kan befunnits i natur.
I synnerhet måste alla giltiga elektroniska Quantum-tillstånd vara antisymmetriska i utbyte av Electron-etiketter.
Det vill säga om $ \psi (x_1, x_2) $ var våg funktionen för det gemensamma Quantum-läget för två electrons, måste vi ha det $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ Pauli uteslutnings principen som tillåter två electrons att någonsin vara i samma Quantum-tillstånd är fascinatingly, en direkt följd av den här lagen som kan vara förklarad från det faktum att om vi växlar två electrons som finns på samma position $ \psi (x_1, x_1) \mapsto \psi (x_1, x_1) \ne-\psi (x_1, x_1) $ om inte $ \psi (x_1 , x_1) = 0 $.
De ursprungliga tillstånden måste därför väljas för att följa den här antisymmetri egenskapen och har i sin tur aldrig två electrons i samma tillstånd.
Detta är viktigt för elektronisk struktur eftersom den inte tillåter att flera electrons är i samma tillstånd, och i sin tur kan quantum datorer använda en enda Quantum-bit för att lagra antalet electrons i ett visst Quantum-tillstånd.

Även om Quantum Mechanics kan simuleras på en Quantum-dator genom att diskretiseringen de här tillstånden, har de flesta arbeten i fältet eschewed den här metoden eftersom det kräver många qubits för att lagra tillstånden och behöver en komplicerad tillstånds förberedelse procedur för att förbereda ett antisymmetriskt initialt tillstånd.
Som tur är kan dessa problem vara sidesteppeda genom att Visa simulerings problemet från ett annat perspektiv.
