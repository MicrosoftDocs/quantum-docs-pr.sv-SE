---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Funktionen StandardAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731931"
---
# <a name="standardamplitudeamplification-function"></a>Funktionen StandardAmplitudeAmplification

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Standardalgoritm för Amplituds förstärkning

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Antal iterationer $n $ för amplitud förstärkning


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Enhetlig Oracle $A $ som förbereder start tillstånd


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index för att flagga qubit



## <a name="output--qubit--unit-adj--ctl"></a>Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL

En åtgärd som implementerar en Quantum-algoritm för standard amplituds förstärkning

## <a name="remarks"></a>Kommentarer

Det här är standardalgoritmen för amplituds förstärkning som erhålls genom ett val av reflektions faser som beräknas genom `AmpAmpPhasesStandard` att \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} den här åtgärden förbereder status \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f\ket {\ text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} i de flesta fall, `flagQubit` och `auxiliaryRegister` initieras i tillstånd $ \ket {0} \_ f\ket {0} \_ a $.

## <a name="references"></a>Referenser

- [*G. Brassard, P. Hoyer, M. Mosca, A. tapp*](https://arxiv.org/abs/quant-ph/0005055)