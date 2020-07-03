---
title: Linjär algebra för kvantberäkning
description: Lär dig vilka grundläggande begrepp inom linjär algebra som behövs för att du ska förstå kvantberäkning
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4cf6cce870c7661a7fffc21dcb60dd53cf281ddd
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415453"
---
# <a name="linear-algebra-for-quantum-computing"></a>Linjär algebra för kvantberäkning

Linjär algebra är språket för kvantberäkning. Du behöver inte kunna det för att implementera eller skriva kvantprogram, men det används ofta för att beskriva kvantbitstillstånd och kvantåtgärder samt för att förutsäga vad en kvantdator kommer att göra som svar på en sekvens med instruktioner.

På samma sätt som kunskaper om [de grundläggande begreppen inom kvantfysik](xref:microsoft.quantum.overview.understanding) kan hjälpa dig att förstå kvantberäkning kan grundläggande linjär algebra vara till hjälp när du vill lära dig hur kvantalgoritmer fungerar. Du bör åtminstone ha kunskaper om **vektorer** och **matrismultiplikation**. Om du behöver uppdatera dina kunskaper om dessa algebrabegrepp finns här några självstudier som beskriver grunderna:

- [Jupyter Notebook-självstudie om linjär algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [Jupyter Notebook-självstudie om komplex aritmetik](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [Linjär algebra för kvantberäkning](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Grunderna inom linjär algebra](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Introduktion till kvantberäkning](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vektorer och matriser i kvantberäkning

I ämnet [Så här fungerar kvantberäkning](xref:microsoft.quantum.overview.understanding) lärde du dig att en kvantbit kan ha tillståndet 1 eller 0 eller en superposition med båda. Med linjär algebra betecknas statusen för en kvantbit som en vektor och representeras av en **matris** med en enskild kolumn: $\begin{bmatrix} a \\\\  b \end{bmatrix}$. Det kallas även för en **kvanttillståndsvektor** och måste uppfylla kravet att $|a|^2 + |b|^2 = 1$.  

Elementen i matrisen representerar sannolikheten att kvantbiten kollapsar åt det ena eller andra hållet. $|a|^2$ är då sannolikheten att den kollapsar till noll, och $|b|^2$ är sannolikheten att den kollapsar till ett. Alla dessa matriser representerar giltiga kvanttillståndsvektorer:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

I [Kvantdatorer och kvantsimulatorer](xref:microsoft.quantum.overview.simulators) såg du även att kvantåtgärder används för att ändra status för en kvantbit.  Kvantåtgärder kan även representeras av en matris. När en kvantåtgärd tillämpas på en kvantbit multipliceras de två matriser som representerar dem, och det resulterande svaret representerar kvantbitens nya tillstånd efter åtgärden.  

Här följer två vanliga kvantåtgärder som representeras med matrismultiplikation.


[`X`-åtgärden](xref:microsoft.quantum.intrinsic.x) representeras av Paulipatrisen $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
och används för att ändra status för en kvantbit från 0 till 1 (eller vice versa), till exempel

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

["H"-åtgärden](xref:microsoft.quantum.intrinsic.h) representeras av Hadamardtransformationen $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 och placerar en kvantbit i ett superpositionstillstånd där den har lika stor sannolikhet att kollapsa åt ettdera hållet såsom det visas här

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

En matris som representerar en kvantåtgärd har ett krav – den måste vara en **enhetlig** matris. En matris är enhetlig om **inversen** av matrisen är lika med matrisens **hermiteska konjugat**.

## <a name="representing-two-qubit-states"></a>Representera tillstånd för två kvantbitar

I exemplen ovan beskrevs statusen för en kvantbit med hjälp av matrisen med en enskild kolumn $\begin{bmatrix} a \\\\  b \end{bmatrix}$, och tillämpningen av en åtgärd på den beskrevs genom multiplikation av de två matriserna. Kvantdatorer använder dock fler än en kvantbit, så hur skulle man beskriva de två kvantbitarnas kombinerade tillstånd? 

Kom ihåg att varje kvantbit är ett vektorrum och därför inte kan multipliceras rakt av. I stället använder du en **tensorprodukt**, en relaterad åtgärd som skapar ett nytt vektorrum från enskilda vektorrum. Den representeras av symbolen $\otimes$. Till exempel beräknas tensorprodukten för tillståndet för två kvantbitar $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$ så här:

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Resultatet är en fyrdimensionell matris där varje element representerar en sannolikhet. Exempelvis är $ac$ sannolikheten att de två kvantbitarna kollapsar till 0 och 0, $ad$ är sannolikheten för 0 och 1 och så vidare. 

Liksom tillståndet för en kvantbit $\begin{bmatrix} a \\\\  b \end{bmatrix}$ måste uppfylla kravet att $|a|^2 + |b|^2 = 1$ för att representera ett kvanttillstånd måste tillståndet för två kvantbitar $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ uppfylla kravet att $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Sammanfattning

Linjär algebra är standardspråket för att beskriva kvantberäkning och kvantfysik. Även om de [bibliotek](xref:microsoft.quantum.libraries) som ingår i Microsoft Quantum Development Kit hjälper dig att köra avancerade kvantalgoritmer utan att du behöver gå in närmare på den underliggande matematiken kommer du igång snabbare om du känner dig säker med grunderna.

## <a name="next-steps"></a>Nästa steg

[Installera QDK](xref:microsoft.quantum.install)
