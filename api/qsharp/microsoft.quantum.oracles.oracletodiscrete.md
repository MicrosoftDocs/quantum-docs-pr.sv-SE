---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Funktionen OracleToDiscrete
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193853"
---
# <a name="oracletodiscrete-function"></a>Funktionen OracleToDiscrete

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En åtgärd som representerar en "svart box" Oracle returnerar en separat tids Oracle som representerar den svarta-Box-Oracle som upprepas flera gånger.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Indata

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Åtgärden som ska exponentiateds.



## <a name="output--discreteoracle"></a>Utdata: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

En åtgärd som delvis tillämpats över "svart box"-Oracle som representerar den diskreta tiden Oracle