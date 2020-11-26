---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216259"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med tanke på förberedelse och mätning beräknar den frekvens med vilken mätningen lyckas (returnerar `Zero` ) genom att utföra ett angivet antal utvärderings versioner.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Indata

### <a name="preparation--qubit--unit"></a>förberedelse: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

En åtgärd $P $ som förbereder ett angivet tillstånd $ \rho $ på sin ingående registrering.


### <a name="measurement--qubit--__invalidresult__"></a>Mått: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __ogiltigt <Result>__ 

En åtgärd $M $ som representerar uppskattning av ränta.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som förberedelsen och mätar varje åtgärd för.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger som mätningen ska utföras för att uppskatta ränte frekvensen.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)

En uppskattning i $ \hat{p} $ av den frekvens med vilken $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ returnerar `Zero` , som erhålls med hjälp av den ej vägd binomialfördelningen $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, där $n \_ {\uparrow} $ är antalet `Zero` resultat som observerats.

Detta är särskilt viktigt på mål datorer som respekterar fysiska begränsningar, så att sannolikheten inte kan mätas.