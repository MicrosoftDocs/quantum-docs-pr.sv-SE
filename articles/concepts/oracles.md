---
title: Kvantorakel
description: Lär dig hur du arbetar med och definierar Quantum Oracles, svarta Box-åtgärder som används som inmatade i en annan algoritm.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904935"
---
# <a name="quantum-oracles"></a>Quantum Oracle

En Oracle $O $ är en "svart box"-åtgärd som används som inmatad till en annan algoritm.
Ofta definieras sådana åtgärder med hjälp av en klassisk funktion $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $ som tar en $n $-bit Binary-indata och genererar en $m $-bitars binär utdata.
Det gör du genom att tänka på en viss binär in$x = (x_{0}x_{1}, \dots, x_ {n-1}) $.
Vi kan märka qubit-tillstånd som $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $.

Vi kan först försöka definiera $O $ så att $O \ket{x} = \ket{f (x)} $, men det har ett par problem.
Först, $f $ kan ha en annan storlek på indata och utdata ($n \ne m $), som att använda $O $ skulle ändra antalet qubits i registreringen.
Den andra, även om $n = m $, kan inte funktionen vara inverteras: om $f (x) = f (y) $ för vissa $x \ne y $, $O \ket{x} = O\ket {y} $, $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.
Det innebär att vi inte kan skapa den angränsande åtgärden $O ^ \dagger $, och Oracle måste ha ett angränsande definierat.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definiera en Oracle genom att påverka beräknings bas staterna
Vi kan hantera båda dessa problem genom att introducera ett andra register med $m $ qubits för att hålla vårt svar.
Därefter definierar vi resultatet av Oracle i alla beräknings grund tillstånd: för alla $x \in \\{0, 1\\} ^ n $ och $y \in \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

Nu $O = O ^ \dagger $ per konstruktion, så har vi löst båda de tidigare problemen.

> [!TIP]
> Om du vill se att $O = O ^ {\dagger} $, Observera att $O ^ 2 = \boldone $ sedan $a \oplus b \oplus b = a $ för alla $a, b \in \{0, 1\}$.
> Därför bör $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

Det är viktigt att definiera en Oracle på det här sättet för varje beräknings grund tillstånd $ \ket{x}\ket{y} $ och även definiera hur $O $ fungerar för alla andra tillstånd.
Detta följer omedelbart från det faktum att $O $, som alla Quantum-åtgärder, är linjärt i det tillstånd som det fungerar på.
Överväg Hadamard-åtgärden, till exempel, som definieras av $H \ket{0} = \ket{+} $ och $H \ket{1} = \ket{-}$.
Om vi vill veta hur $H $ reagerar på $ \ket{+} $ kan vi använda den $H $ är linjär,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

Om du definierar vår Oracle $O $ kan vi på samma sätt använda att alla tillstånd $ \ket{\psi} $ på $n + m $ qubits kan skrivas som

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $

där $ \alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ representerar koefficienterna för tillstånd $ \ket{\psi} $. Därför

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0, 1\\} ^ n, y \in \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0, 1\\} ^ n , y \in \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Fas Oracle
Alternativt kan vi koda $f $ till en Oracle $O $ genom att använda en _fas_ baserat på indatamängden för att $O $.
Vi kan till exempel definiera $O $ så att $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $ om en fas Oracle agerar i ett register inlednings vis i ett beräknings bas tillstånd $ \ket{x} $, är den här fasen en global fas och går därför inte att observera.
Men en sådan Oracle kan vara en mycket kraftfull resurs om den tillämpas på en överposition eller som en kontrollerad åtgärd.
Anta till exempel en fas orcale $O _f $ för en qubit-funktion $f $.
Sedan $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

I allmänhet kan båda vyerna i Oracle utökas för att representera klassiska funktioner som returnerar reella tal i stället för bara en enda bit.

Att välja det bästa sättet att implementera en Oracle är beroende av hur den här Oracle kommer att användas inom en specifik algoritm.
Till exempel är [Deutsch-Jozsa-algoritmen](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) beroende av den Oracle som implementerats på det första sättet, medan [algoritmen för Grover är](https://en.wikipedia.org/wiki/Grover's_algorithm) beroende av den Oracle som implementerats på det andra sättet.


För mer information, föreslår vi diskussionen i [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
