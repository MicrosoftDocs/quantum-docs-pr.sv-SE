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
# <a name="oracletodiscrete-function"></a><span data-ttu-id="7b517-102">Funktionen OracleToDiscrete</span><span class="sxs-lookup"><span data-stu-id="7b517-102">OracleToDiscrete function</span></span>

<span data-ttu-id="7b517-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="7b517-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="7b517-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b517-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b517-105">En åtgärd som representerar en "svart box" Oracle returnerar en separat tids Oracle som representerar den svarta-Box-Oracle som upprepas flera gånger.</span><span class="sxs-lookup"><span data-stu-id="7b517-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="7b517-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7b517-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="7b517-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="7b517-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7b517-108">Åtgärden som ska exponentiateds.</span><span class="sxs-lookup"><span data-stu-id="7b517-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="7b517-109">Utdata: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="7b517-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="7b517-110">En åtgärd som delvis tillämpats över "svart box"-Oracle som representerar den diskreta tiden Oracle</span><span class="sxs-lookup"><span data-stu-id="7b517-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>