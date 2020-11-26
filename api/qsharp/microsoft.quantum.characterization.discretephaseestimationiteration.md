---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204393"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en enkel upprepning av en iterativ (klassisk) fas uppskattnings algoritm med hjälp av heltals befogenheter för en enhetlig Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Åtgärder som utförs på ett heltal och ett register, t. ex. $U ^ m $ tillämpas på den aktuella registreringen, där $U $ är den kraft vars fas är att uppskatta, och där $m $ är den heltals effekt som ges till Oracle


### <a name="power--int"></a>effekt: [int](xref:microsoft.quantum.lang-ref.int)

Antal gånger som den erhållna Oracle-gruppen ska tillämpas.


### <a name="theta--double"></a>theta: [dubbel](xref:microsoft.quantum.lang-ref.double)

Vinkel för vilken du vill invertera fasen i kontrollen qubit innan du agerar på mål tillstånd.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig för det tillstånd som har åtgärd ATS av den enhetliga Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En hjälp qubit som används för att kontrol lera programmet för den specifika Oracle.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

