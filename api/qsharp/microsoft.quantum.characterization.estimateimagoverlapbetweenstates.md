---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851871"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>EstimateImagOverlapBetweenStates-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med två åtgärder som var och en förbereder kopior av ett tillstånd, beräknar den imaginära delen av överlappningen mellan de stadier som bearbetas av varje åtgärd.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Indata

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

En åtgärd som förbereder ett fast ingångs tillstånd.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den första av de två tillstånds förberedelse åtgärderna som ska jämföras.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Den andra av de två tillstånds förberedelse åtgärderna som ska jämföras.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som `commonPreparation` , `preparation1` och `preparation2` alla Act.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet mätningar som ska användas vid uppskattning av överlappningen.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Kommentarer

Den här åtgärden använder Hadamard-testet för att hitta den imaginära delen av $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $ där $ \ket{\psi} $ är det tillstånd som förberetts av `commonPreparation` , $U $ är den enhetliga representationen av åtgärden `preparation1` och där $V $ motsvarar `preparation2` .

## <a name="references"></a>Referenser

- Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. karakterisering. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. karakterisering. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)