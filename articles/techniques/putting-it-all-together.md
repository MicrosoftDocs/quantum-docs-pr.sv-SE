---
title: 'Q # tekniker - Sätta ihop allt'
description: Gå igenom ett grundläggande Q# program som visar kvantteleportering.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030573"
---
# <a name="putting-it-all-together-teleportation"></a>Sätta ihop allt: Teleportering #
Låt oss återgå till exemplet med teleporteringskretsen som definieras i [Kvantkretsar](xref:microsoft.quantum.concepts.circuits). Vi ska använda detta för att illustrera de begrepp vi har lärt oss hittills. En förklaring av kvantteleportering ges nedan för dem som är obekanta med teorin, följt av en genomgång av koden genomförandet i Q # . 

## <a name="quantum-teleportation-theory"></a>Quantum Teleportation: Teori
Quantum teleportering är en teknik för att skicka ett okänt kvanttillstånd (som vi kommer att hänvisa till som "__meddelande__" ) från en qubit på en plats till en qubit på en annan plats (vi hänvisar till dessa qubits som "__här__" och "__där__", respektive). Vi kan representera vårt __budskap__ som en vektor med Dirac notation: 

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

__Meddelandet__ qubit tillstånd är okänd för oss eftersom vi inte vet värdena för $\alpha$ och $\beta$.

### <a name="step-1-create-an-entangled-state"></a>Steg 1: Skapa ett insnärjt tillstånd
För att skicka __meddelandet__ behöver vi för qubit __här__ att trasslad med qubit __där__. Detta uppnås genom att tillämpa en Hadamard gate, följt av en CNOT gate. Låt oss titta på matten bakom gate operationer.

Vi börjar med qubits __här__ och __där__ både{0}i $ \ ket $ staten. Efter att ha trasslar in dessa qubits, är de i staten:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Steg 2: Skicka meddelandet
För att skicka __meddelandet__ tillämpar vi först en CNOT-port med __meddelandet__ qubit och __här__ qubit som ingångar __(meddelandet__ qubit är kontrollen och __här__ qubit är målet qubit, i detta fall). Det här indatatillståndet kan skrivas:

$$ \ket{\psi}\ket{\phi^+}{0} = (\alpha\ket +{1}\beta\ket{1})(\frac{2}{\sqrt }(\ket{00} + \ket{11})) $$

Detta utökas till:

$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} +{2}\frac{\beta}{\\sqrt }\ket{111} $$ $

Som en påminnelse vänder CNOT-porten målsansen när kontrolls qubit är 1. Så till exempel kommer en inmatning av $\ket{000}$ resultera i någon förändring eftersom den första qubit (kontrollen) är 0. Men ta ett fall där den första qubit är 1 -{100}till exempel en ingång på $\ket $. I det här fallet är utdata $\ket{110}$ som den andra qubit (målet) vänds av CNOT gate.

Låt oss nu överväga vår produktion när CNOT gate har agerat på våra synpunkter ovan. Resultatet är:

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$

Nästa steg för att skicka __meddelandet__ är att tillämpa en Hadamard-port på __meddelandet__ qubit (det är den första qubit av varje term). 

Som en påminnelse gör Hadamard-porten följande:

Indata | Resultat
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$

Om vi tillämpar Hadamard gate till den första qubit av varje term av vår produktion ovan, får vi följande resultat:

$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket ))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $ket $$

Observera att varje term har{1}två $\frac{2}{\sqrt }$ faktorer. Vi kan multiplicera dessa ger följande resultat:

$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} +{1}\ket)\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket - \ket\ket{0} {1}{01} $$ $

Den $ \{1}{2}frac $ faktor är gemensam för varje term så att vi nu kan ta det utanför parentes:

$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket \ket{01}\big] $$

Vi kan sedan multiplicera ut parenteserna för varje term som ger:

{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \big] $$

### <a name="step-3-measure-the-result"></a>Steg 3: Mät resultatet

På grund av __här__ och __där__ är insnärjda, någon mätning på __här__ kommer att påverka tillståndet i __det__. Om vi mäter den första och andra qubit __(meddelande__ och __här)__ kan vi lära oss vilket tillstånd __det finns__ i, på grund av denna egenskap av trassel. 

* Om vi mäter och får ett resultat 00 kollapsar superpositionen, vilket innebär att endast termer överensstämmer med detta resultat. Det är $\alpha\ket{000} +\beta\ket{001}$. Detta kan återfactoreras till $\ket{00}(\alpha\ket{0} +\beta\ket{1})$. Därför om vi mäter den första och andra qubit vara 00, vet vi att den tredje qubit, det ,{1} __är__i staten $(\alpha\ket{0} +\beta\ket)$.
* Om vi mäter och får ett resultat 01 kollapsar superpositionen, vilket innebär att endast termer överensstämmer med detta resultat. Det är $\alpha\ket{011} +\beta\ket{010}$. Detta kan återfactoreras till $\ket{01}(\alpha\ket{1} +\beta\ket{0})$. Därför om vi mäter den första och andra qubit vara 01, vet vi att den tredje qubit, det ,{0} __är__i staten $(\alpha\ket{1} +\beta\ket)$.
* Om vi mäter och får ett resultat 10 kollapsar superpositionen och lämnar endast termer som överensstämmer med detta resultat. Det är $\alpha\ket{100} -\beta\ket{101}$. Detta kan återfactoreras till $\ket{10}(\alpha\ket{0} -\beta\ket{1})$. Därför om vi mäter den första och andra qubit vara 10, vet vi att den tredje qubit, det ,{1} __är__i staten $(\alpha\ket{0} -\beta\ket)$.
* Om vi mäter och får ett resultat 11 kollapsar superpositionen och lämnar endast termer som överensstämmer med detta resultat. Det är $\alpha\ket{111} -\beta\ket{110}$. Detta kan återfactoreras till $\ket{11}(\alpha\ket{1} -\beta\ket{0})$. Därför om vi mäter den första och andra qubit vara 11, vet vi att den tredje qubit, det ,{0} __är__i staten $(\alpha\ket{1} -\beta\ket)$.

### <a name="step-4-interpret-the-result"></a>Steg 4: Tolka resultatet

Som en påminnelse, det ursprungliga __meddelandet__ vi ville skicka var:

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Vi måste få __in det__ i detta tillstånd, så att den mottagna staten är den som var avsedd. 

* Om vi mätte och fick ett resultat av 00, då den tredje qubit,{0} __det__, är i staten $(\alpha\ket +\beta\ket)$.{1} Eftersom detta är det avsedda __meddelandet__krävs ingen ändring.
* Om vi mätte och fick ett resultat av 01, då den tredje qubit,{1} __det__, är i staten $(\alpha\ket +\beta\ket)$.{0} Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en INTE gate{0} ger oss önskat{1}tillstånd $(\alpha\ket +\beta\ket)$.
* Om vi mätte och fick ett resultat av 10, då den tredje qubit,{0} __det__, är i staten $(\alpha\ket -\beta\ket)$.{1} Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en Z gate{0} ger oss önskat{1}tillstånd $(\alpha\ket +\beta\ket)$.
* Om vi mätte och fick ett resultat av 11, då den tredje qubit,{1} __det__, är i staten $(\alpha\ket -\beta\ket)$.{0} Detta skiljer sig från det avsedda __meddelandet__, men tillämpa en INTE gate följt av en{0} Z gate ger{1}oss önskat tillstånd $(\alpha\ket +\beta\ket)$.

Sammanfattningsvis, om vi mäter och den första qubit är 1, appliceras en Z-port. Om vi mäter och den andra qubit är 1, en INTE gate tillämpas.

### <a name="summary"></a>Sammanfattning
Nedan visas en textbokskrets som implementerar teleporteringen. Om du flyttar från vänster till höger kan du se:
- Steg 1: Entangling __här__ och __där__ genom att tillämpa en Hadamard gate och CNOT gate.
- Steg 2: Skicka __meddelandet__ med en CNOT-grind och en Hadamard-port.
- Steg 3: Med ett mått på den första och andra qubits, __meddelande__ och __här__.
- Steg 4: Applicera en NOT-grind eller en Z-grind, beroende på resultatet av mätningen i steg 3.

!["Teleport(msg: Qubit, där: Qubit) : Enhet"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Quantum Teleportering: Kod

Vi har vår krets för kvantteleportering:

!["Teleport(msg: Qubit, där: Qubit) : Enhet"](~/media/teleportation.svg)

Vi kan nu översätta vart och ett av stegen i denna kvantkrets till Q#.

### <a name="step-0-definition"></a>Steg 0: Definition
När vi utför teleportering, måste vi veta __det budskap__ vi vill skicka, och där vi vill skicka det __(där).__ Av denna anledning börjar vi med att definiera en ny Teleport operation `msg` `there`som ges två qubits som argument, och:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Vi måste också fördela en `here` qubit som `using` vi uppnår med ett block:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Steg 1: Skapa ett insnärjt tillstånd
Vi kan sedan skapa det insnärjda paret mellan `here` och `there` genom att använda @"microsoft.quantum.intrinsic.h" och @"microsoft.quantum.intrinsic.cnot" operationer:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Steg 2: Skicka meddelandet
Vi använder sedan nästa $\operatorname{CNOT}$ och $H $ grindar för att flytta vårt meddelande qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Steg 3 & 4: Mätning och tolkning av resultatet
Slutligen använder @"microsoft.quantum.intrinsic.m" vi för att utföra mätningarna och utföra nödvändiga gate operationer för `if` att få önskat tillstånd, som betecknas med uttalanden:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Steg 5: Starta om qubit-registret

I slutet av varje Q # operation måste vi låta qubits{0}i staten $ \ ket $. Vi kan @"microsoft.quantum.intrinsic.reset" använda för att starta om alla qubits till noll tillstånd och detta kommer att avsluta vår operation.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


