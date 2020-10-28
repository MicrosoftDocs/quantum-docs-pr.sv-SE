---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726433"
---
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation-åtgärd

Namnrymd: [Microsoft. Quantum. Research. karakterisering](xref:Microsoft.Quantum.Research.Characterization)

Paketfilerna [](https://nuget.org/packages/)


Utför iterativ fas uppskattning med en slumpmässig genom gång för att approximera Bayesian-härledningen på de klassiska mått resultaten från en specifik Oracle och eigenstate.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Indata

### <a name="initialmean--double"></a>initialMean: [dubbel](xref:microsoft.quantum.lang-ref.double)

Medelvärde för den första normala tidigare distributionen över $ \phi $.


### <a name="initialstddev--double"></a>initialStdDev: [dubbel](xref:microsoft.quantum.lang-ref.double)

Standard avvikelse för den initiala normal tidigare distributionen över $ \phi $.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mätningar som ska godkännas i den slutliga beräkningen i efterhand.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Det totala antalet mätningar som kan vidtas innan åtgärden anses ha misslyckats.


### <a name="unwind--int"></a>avspolning: [int](xref:microsoft.quantum.lang-ref.int)

Antal resultat som ska glömmas när konsekvens kontroller misslyckats.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

En åtgärd som representerar en enhetlig $U $ t. ex. $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ för eigenstates $ \ket{\phi} $ med okänd fas $ \phi \in \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register som $U $ handlar om.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Den slutliga uppskattningen $ \hat{\phi} \mathrel{: =} \expect [\phi] $, där förväntat sker över alla accepterade data.

## <a name="remarks"></a>Kommentarer

### <a name="iterative-phase-estimation-and-eigenstates"></a>Uppskattning av iterativa faser och Eigenstates

I allmänhet behöver ingångs registreringen `eigenstate` inte vara en eigenstate $ \ket{\phi} $ $U $, men kan vara en överposition över eigenstates. Anta att indatamängden anges av \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} där $ \{ \alpha \_ j \} $ är komplexa koefficienter som $ \sum \_ j | \alpha \_ j | ^ 2 = $1 och där $U \ket{\phi \_ j} = \phi \_ j\ket {\ Fi \_ j} $.

Sedan konvergerar periodiska fas uppskattningar till en enda eigenstate enligt beskrivningen i [utvecklings guiden](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Experiment design

Mätnings tiderna $t $ och inversions vinklarna $ \theta $ som `oracle` väljs enligt *partikel gissans heuristik* , \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.
\end{align} den här heuristiken är optimal för att minska den förväntade föregående avvikelsen i upprepnings fas uppskattningen under antagandet av en normal tidigare period.

### <a name="optimality"></a>Optimalhet

Den här åtgärden uppskattar den optimala uppskattningen för fasen $ \phi $, som utvärderas med hjälp av kvadratisk förlust $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.

Se [uppskattning av Bayesian-fasen](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) för mer information om statistik för uppskattning av iterativa faser.

## <a name="references"></a>Referenser

- Uppskjuten *et al.* 2011 [Doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [Doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe och granade 2018 *(i förberedelse)* .