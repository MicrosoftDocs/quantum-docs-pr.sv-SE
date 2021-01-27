---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835674"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation-åtgärd

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Beräknar den energi som är kopplad till en specifik Jordan-Wigner Hamiltonian-period

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Description

Den här åtgärden uppskattar förväntat värde som är kopplat till varje mått operator och multiplicerar det med motsvarande koefficient, med hjälp av sampling.
Resultaten sammanställs i en variabel som innehåller Jordan-Wigner periodens energi.

## <a name="input"></a>Indata

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Den plats som används för förberedelse av tillstånd.


### <a name="ops--pauli"></a>Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Jordan-Wigner periodens mått operatorer.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner termns koefficienter.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som krävs för att simulera molekyl systemet.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Antalet prover som ska användas för uppskattning av förväntad term.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

Den energi som är kopplad till Jordan-Wigners perioden.