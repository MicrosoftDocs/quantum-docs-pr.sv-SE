---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Funktionen OracleToDiscrete
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842542"
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

## <a name="example"></a>Exempel

`OracleToDiscrete(U)(3, target)` motsvarar `U(target)` tre gånger upprepade gånger.