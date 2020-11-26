---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226799"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="bd76e-102">ContinuousOracle-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="bd76e-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="bd76e-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="bd76e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="bd76e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd76e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd76e-105">Representerar en löpande Oracle-enhet.</span><span class="sxs-lookup"><span data-stu-id="bd76e-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="bd76e-106">Det här är en Oracle som implementerar $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ för alla tider $t $, där $U $ är en fast åtgärd och där $ \delta t $ är ett icke-negativt reellt tal.</span><span class="sxs-lookup"><span data-stu-id="bd76e-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

