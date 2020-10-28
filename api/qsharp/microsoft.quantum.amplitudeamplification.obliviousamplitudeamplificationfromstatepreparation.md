---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: Funktionen ObliviousAmplitudeAmplificationFromStatePreparation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731979"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>Funktionen ObliviousAmplitudeAmplificationFromStatePreparation

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Oblivious amplitud-förstärkning av Oracle för partiella reflektioner.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="phases--reflectionphases"></a>faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Faser av partiella reflektioner


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Enhetlig Oracle $A $ som förbereder start tillstånd


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Enhetlig Oracle $O $ av typ `ObliviousOracle` som fungerar tillsammans i hjälp-och system registret


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index till Single-qubit flagga-register



## <a name="output--qubitqubit--unit-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En åtgärd som implementerar Oblivious amplitud-förstärkning baserat på partiella reflektioner.

## <a name="remarks"></a>Kommentarer

Detta tillämpar strängare villkor på form av hjälp start-och mål tillstånd än i `AmpAmpObliviousByReflectionPhases` .
Det antas att $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ förbereder start tillstånd $ \ket{\text{Start}} \_ {FA} $ från beräknings basen $ \ket {0} \_ f\ket {0} $.
Det förutsätts att mål tillstånd är markerat med $ \ket {1} \_ f $.
Det antas att \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {all}} \_ a\ket {\ text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} för en del $U $.