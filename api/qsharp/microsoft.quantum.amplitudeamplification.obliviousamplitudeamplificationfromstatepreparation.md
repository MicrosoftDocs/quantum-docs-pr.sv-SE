---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: Funktionen ObliviousAmplitudeAmplificationFromStatePreparation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845810"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>Funktionen ObliviousAmplitudeAmplificationFromStatePreparation

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som implementerar Oblivious amplitud-förstärkning baserat på partiella reflektioner.

## <a name="remarks"></a>Kommentarer

Detta tillämpar strängare villkor på form av hjälp start-och mål tillstånd än i `AmpAmpObliviousByReflectionPhases` .
Det antas att $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ förbereder start tillstånd $ \ket{\text{Start}} \_ {FA} $ från beräknings basen $ \ket {0} \_ f\ket {0} $.
Det förutsätts att mål tillstånd är markerat med $ \ket {1} \_ f $.
Det antas att \begin{align} O\ket {\ text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {all}} \_ a\ket {\ text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} för en del $U $.