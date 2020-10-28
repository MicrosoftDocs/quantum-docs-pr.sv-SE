---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Funktionen OracleToDiscrete
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733358"
---
# <a name="oracletodiscrete-function"></a>Funktionen OracleToDiscrete

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


En åtgärd som representerar en "svart box" Oracle returnerar en separat tids Oracle som representerar den svarta-Box-Oracle som upprepas flera gånger.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Indata

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL

Åtgärden som ska exponentiateds.



## <a name="output--discreteoracle"></a>Utdata: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

En åtgärd som delvis tillämpats över "svart box"-Oracle som representerar den diskreta tiden Oracle