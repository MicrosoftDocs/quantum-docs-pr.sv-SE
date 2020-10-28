---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732006"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification-åtgärd

Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paketfilerna [](https://nuget.org/packages/)


Oblivious amplitud-förstärkning genom att ange partiella reflektioner.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="phases--reflectionphases"></a>faser: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Faser av partiella reflektioner


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Reflektions operator om start tillstånd för hjälp register


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Reflektions operator om mål tillstånd för hjälp registrering


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Enhetlig Oracle-$O $ av typ `ObliviousOracle` som fungerar tillsammans i hjälp-och system registren.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Hjälp register


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

System register



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Angett ett särskilt start tillstånd $ \ket{\text{Start}} \_ a $, ett visst hjälp mål tillstånd $ \ket{\text{Target}} \_ a $ och alla system tillstånd $ \ket{\psi} \_ s $, Antag att \begin{align} O\ket {\ text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{Target} ^ \perp} \_ a\cdots \end{align} för en del $U $.
Med en sekvens av reflektioner om start-och mål tillstånden i det extra register som överlämnas av program `signalOracle` och dess intilliggande, kan sannolikheten för att använda U ändras.

I de flesta fall `auxiliaryRegister` initieras status $ \ket{\text{Start}} \_ a $.

## <a name="references"></a>Referenser

Se

- [ *D.W. bär, am, barn, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) för standard versionen.
  Se
- [ *G.H. låg, I.L. Chuang*](https://arxiv.org/abs/1610.06546) för en generalisering till partiella reflektioner.