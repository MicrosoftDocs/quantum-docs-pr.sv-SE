---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216293"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utför en enkel upprepning av en iterativ (klassisk) fas uppskattnings algoritm med godtyckliga verkliga befogenheter hos en enhetlig Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Indata

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Åtgärder som utförs på en dubbel $t $ och ett register, t. ex. $U ^ t $ tillämpas på den aktuella registreringen, där $U $ är den kraft vars fas är att uppskatta, och där $t $ är den heltals effekt som ges till Oracle


### <a name="time--double"></a>tid: [dubbel](xref:microsoft.quantum.lang-ref.double)

Antal gånger som den erhållna Oracle-gruppen ska tillämpas.


### <a name="theta--double"></a>theta: [dubbel](xref:microsoft.quantum.lang-ref.double)

Vinkel för vilken du vill invertera fasen i kontrollen qubit innan du agerar på mål tillstånd.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registrera dig för det tillstånd som har åtgärd ATS av den enhetliga Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

