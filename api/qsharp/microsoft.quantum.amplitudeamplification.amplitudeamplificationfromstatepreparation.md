---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: Funktionen AmplitudeAmplificationFromStatePreparation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732043"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>Funktionen AmplitudeAmplificationFromStatePreparation

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Amplitud förstärkning av Oracle för partiella reflektioner.

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="phases--reflectionphases"></a>faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Faser av partiella reflektioner


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Enhetlig Oracle $A $ som förbereder start tillstånd


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index för att flagga qubit



## <a name="output--qubit--unit-adj--ctl"></a>Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En åtgärd som implementerar amplitud-förstärkning av Oracle som implementeras av partiella reflektioner.

## <a name="remarks"></a>Kommentarer

Detta tillämpar strängare villkor i form av start-och mål tillstånd än i `AmpAmpByReflectionPhases` .
Det förutsätts att mål tillstånd är markerat med $ \ket {1} \_ f $.
Det förutsätts att \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} i de flesta fall `flagQubit` och `auxiliaryRegister` initieras i tillstånd $ \ket {0} \_ {f} \ket {0} \_ s $.