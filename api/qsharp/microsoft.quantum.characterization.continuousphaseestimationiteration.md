---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851898"
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

