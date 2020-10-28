---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727360"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="a964e-102">AssertAllZeroWithinTolerance-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a964e-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="a964e-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a964e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a964e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a964e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a964e-105">Assert att de aktuella qubits är i $ \ket {0} $-tillstånd upp till en bestämd tolerans.</span><span class="sxs-lookup"><span data-stu-id="a964e-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a964e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a964e-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="a964e-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a964e-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a964e-108">Qubits som ska vara i läget $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a964e-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a964e-109">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a964e-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a964e-110">Noggrannhet med vilken status ska vara i läget $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="a964e-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="a964e-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a964e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a964e-112">Se även</span><span class="sxs-lookup"><span data-stu-id="a964e-112">See Also</span></span>

- [<span data-ttu-id="a964e-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="a964e-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)