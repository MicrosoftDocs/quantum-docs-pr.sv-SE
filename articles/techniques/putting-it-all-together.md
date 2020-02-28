---
title: 'Q #-tekniker – placera allt tillsammans'
description: 'Gå igenom ett Basic Q #-program som visar Quantum Teleportion.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906839"
---
# <a name="putting-it-all-together-teleportation"></a>Placera allt tillsammans: Teleportion #
Vi går tillbaka till exemplet på den Teleportion-krets som definieras i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits). Vi ska använda det här för att illustrera de koncept vi har lärt dig hittills. En förklaring av Quantum Teleportion finns nedan för de som inte är bekanta med teori, följt av en genom gång av kod implementeringen i Q #. 

## <a name="quantum-teleportation-theory"></a>Quantum Teleportion: teori
Quantum Teleportion är en teknik för att skicka ett okänt Quantum-tillstånd (som vi refererar till som "__meddelande__") från en qubit på en plats till en qubit på en annan plats (vi kommer att se dessa qubits som "__här__" och "__där__"). Vi kan representera vårt __meddelande__ som en Vector med Dirac-notation: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

__Meddelandets__ qubit tillstånd är okänt för oss eftersom vi inte vet värdena för $ \alpha $ och $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Steg 1: skapa ett Entangled-tillstånd
För att kunna skicka det __meddelande__ __som krävs för att qubit ska__ kunna Entangled med qubit __där__. Detta uppnås genom att använda en Hadamard-grind, följt av en CNOT-grind. Nu ska vi titta på det matematiska arbetet bakom dessa grind åtgärder.

Vi kommer att börja med qubits __här__ och __där__ både i $ \ket{0}$ State. När Entangling dessa qubits är de i ett tillstånd:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Steg 2: skicka meddelandet
För att skicka __meddelandet__ använder vi först en CNOT-port med __meddelandet__ qubit och __här__ qubit som indata ( __meddelandet__ qubit som kontrollen och __här__ qubit är mål-qubit, i den här instansen). Det går att skriva till det här ingångs läget:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Detta utökar till:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

Som en påminnelse vänder CNOT-grinden mål-qubit när kontroll-qubit är 1. Till exempel resulterar en inmatare på $ \ket{000}$ ingen ändring som den första qubit (kontrollen) är 0. Använd dock ett fall där den första qubit är 1 – till exempel en inmatad $ \ket{100}$. I den här instansen är utdata $ \ket{110}$ som den andra qubit (målet) vändas av CNOT-porten.

Nu ska vi ta med våra utdata när CNOT-porten har handlat på vår indata ovan. Resultatet är:

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

Nästa steg för att skicka __meddelandet__ är att tillämpa en Hadamard-grind på __meddelandet__ qubit (det är den första qubit i varje term). 

Som en påminnelse gör Hadamard-grinden följande:

Indata | Resultat
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Om vi tillämpar Hadamard-porten på den första qubit av varje term i våra utdata ovan får vi följande resultat:

$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Observera att varje term har $2 \frac{1}{\sqrt{2}} $ faktorer. Vi kan multiplicera dessa resultat genom att ge följande resultat:

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

$ \Frac{1}{2}$-faktorn är gemensam för varje term, så vi kan nu ta den utanför hakparenteserna:

$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Vi kan sedan multiplicera hakparenteserna för varje term som ger:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Steg 3: mät resultatet

På grund av detta __och Entangled__ kommer eventuella mått för __detta__ att påverka status för __där__. Om vi mäter det första och andra qubit (__meddelande__ och __här__) kan vi lära sig det tillstånd som __finns__ i, på grund av den här egenskapen för entanglement. 

* Om vi mäter och får resultat 00, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet lämnas. Det är $ \alpha\ket{000} + \beta\ket{001}$. Detta kan omanpassas till $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Om vi mäter den första och andra qubit till 00, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $.
* Om vi mäter och erhåller ett resultat 01, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet lämnas. Det är $ \alpha\ket{011} + \beta\ket{010}$. Detta kan omanpassas till $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Om vi mäter den första och andra qubit till 01, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1} + \beta\ket{0}) $.
* Om vi mäter och erhåller ett resultat 10, komprimeras överplaceringen och endast de villkor som stämmer med det här resultatet. Det är $ \alpha\ket{100}-\beta\ket{101}$. Detta kan omanpassas till $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Om vi mäter den första och andra qubit till 10, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0}-\beta\ket{1}) $.
* Om vi mäter och erhåller ett resultat 11, komprimeras överplaceringen och endast de villkor som är konsekventa med det här resultatet lämnas. Det är $ \alpha\ket{111}-\beta\ket{110}$. Detta kan omanpassas till $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Om vi mäter den första och andra qubit till 11, vet vi att det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Steg 4: tolka resultatet

Som en påminnelse skulle det ursprungliga __meddelandet__ som vi vill skicka var:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Vi måste hämta __det__ qubit i det här läget, så att det mottagna läget är det som avsågs. 

* Om vi mätte och fick resultatet 00 är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $. Eftersom det här är det avsedda __meddelandet__krävs ingen ändring.
* Om vi mätte och fick resultatet 01, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1} + \beta\ket{0}) $. Detta skiljer sig från det avsedda __meddelandet__, men att använda en icke-grind ger oss det önskade tillstånd $ (\alpha\ket{0} + \beta\ket{1}) $.
* Om vi mätte och fick resultatet 10, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{0}-\beta\ket{1}) $. Detta skiljer sig från det avsedda __meddelandet__, men att använda en Z-grind ger oss det önskade läget $ (\alpha\ket{0} + \beta\ket{1}) $.
* Om vi mätte och fick resultatet 11, är det tredje qubit, __där__, är i tillstånd $ (\alpha\ket{1}-\beta\ket{0}) $. Detta skiljer sig från det avsedda __meddelandet__, men att använda en icke-grind följt av en Z-grind ger oss det önskade läget $ (\alpha\ket{0} + \beta\ket{1}) $.

Om vi mäter och det första qubit är 1, används en Z-grind för att sammanfatta. Om vi mäter och den andra qubit är 1, tillämpas en icke-grind.

### <a name="summary"></a>Sammanfattning
Nedan visas en text boks Quantum-krets som implementerar Teleportion. Flytta från vänster till höger kan du se:
- Steg 1: Entangling __här__ och __där__ genom att tillämpa en Hadamard-grind och CNOT-grind.
- Steg 2: skicka __meddelandet__ med en CNOT-grind och en Hadamard-grind.
- Steg 3: ta en mätning av den första och andra qubits, ett __meddelande__ och __här__.
- Steg 4: tillämpa en NOT-grind eller en Z-grind, beroende på resultatet av måttet i steg 3.

![' Teleport (MSG: qubit, där: qubit): enhet '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Quantum Teleportion: kod

Vi har vår krets för Quantum Teleportion:

![' Teleport (MSG: qubit, där: qubit): enhet '](~/media/teleportation.svg)

Vi kan nu översätta vart och ett av stegen i den här Quantum-kretsen till Q #.

### <a name="step-0-definition"></a>Steg 0: definition
När vi utför Teleportion måste vi känna till det __meddelande__ vi vill skicka och var vi vill skicka det (__där__). Därför börjar vi genom att definiera en ny Teleport-åtgärd som har två qubits som argument, `msg` och `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Vi måste också allokera en qubit `here` som vi uppnår med ett `using` block:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Steg 1: skapa ett Entangled-tillstånd
Vi kan sedan skapa Entangled-paret mellan `here` och `there` med hjälp av @"microsoft.quantum.intrinsic.h" och @"microsoft.quantum.intrinsic.cnot" åtgärder:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Steg 2: skicka meddelandet
Vi använder sedan nästa $ \operatorname{CNOT} $ och $H $ Gates för att flytta vårt meddelande qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Steg 3 & 4: mäta och tolka resultatet
Slutligen använder vi @"microsoft.quantum.intrinsic.m" för att utföra mätningarna och utföra de åtgärder som krävs för att få önskat tillstånd, som betecknas med `if`-satser:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Detta slutför definitionen av vår Teleportion-operatör, så att vi kan frigöra `here`, avsluta bröd texten och avsluta åtgärden.

```qsharp
    }
}
```
