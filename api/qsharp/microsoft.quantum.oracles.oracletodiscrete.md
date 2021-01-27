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
# <a name="oracletodiscrete-function"></a><span data-ttu-id="06df4-102">Funktionen OracleToDiscrete</span><span class="sxs-lookup"><span data-stu-id="06df4-102">OracleToDiscrete function</span></span>

<span data-ttu-id="06df4-103">Namnrymd: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="06df4-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="06df4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06df4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06df4-105">En åtgärd som representerar en "svart box" Oracle returnerar en separat tids Oracle som representerar den svarta-Box-Oracle som upprepas flera gånger.</span><span class="sxs-lookup"><span data-stu-id="06df4-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="06df4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="06df4-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="06df4-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="06df4-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="06df4-108">Åtgärden som ska exponentiateds.</span><span class="sxs-lookup"><span data-stu-id="06df4-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="06df4-109">Utdata: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="06df4-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="06df4-110">En åtgärd som delvis tillämpats över "svart box"-Oracle som representerar den diskreta tiden Oracle</span><span class="sxs-lookup"><span data-stu-id="06df4-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="06df4-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="06df4-111">Example</span></span>

<span data-ttu-id="06df4-112">`OracleToDiscrete(U)(3, target)` motsvarar `U(target)` tre gånger upprepade gånger.</span><span class="sxs-lookup"><span data-stu-id="06df4-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>