---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728167"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement-åtgärd

Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)

Paketfilerna [](https://nuget.org/packages/)


Utför en qubit process tomography mått i Pauli-basen, med tanke på en viss kanal av intresse.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Indata

### <a name="preparation--pauli"></a>förberedelse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli-basen $P $ där en qubit ska förberedas.


### <a name="measurement--pauli"></a>Mått: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli-basen $Q $ i vilken en qubit ska mätas.


### <a name="channel--qubit--unit"></a>kanal: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

En enda qubit-kanal $ \Lambda $ vars beteende beräknas med process tomography.



## <a name="output--__invalidresult__"></a>Utdata: __ogiltig <Result>__

Resultatet `Zero` med sannolikhet $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Kommentarer

Distributionen över resultaten som returneras av den här åtgärden är ett specialfall av qubit status tomography. Låt $ \rho = J (\Lambda)/$2 vara Choi – Jamiłkowski-tillstånd för $ \Lambda $. Sedan är fördelningen ovan identisk med $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ där $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 är den effektiva mätning som motsvarar $P $ och $Q $.