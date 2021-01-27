---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830853"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="5c892-102">AssertAllZeroWithinTolerance-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5c892-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="5c892-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c892-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c892-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5c892-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5c892-105">Assert att de aktuella qubits är i $ \ket {0} $-tillstånd upp till en bestämd tolerans.</span><span class="sxs-lookup"><span data-stu-id="5c892-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5c892-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5c892-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="5c892-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5c892-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5c892-108">Qubits som ska vara i läget $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="5c892-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="5c892-109">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c892-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c892-110">Noggrannhet med vilken status ska vara i läget $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="5c892-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c892-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c892-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5c892-112">Se även</span><span class="sxs-lookup"><span data-stu-id="5c892-112">See Also</span></span>

- [<span data-ttu-id="5c892-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="5c892-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)