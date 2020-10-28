---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733398"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paketfilerna [](https://nuget.org/packages/)


Representerar en löpande Oracle-enhet.

Det här är en Oracle som implementerar $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ för alla tider $t $, där $U $ är en fast åtgärd och där $ \delta t $ är ett icke-negativt reellt tal.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

