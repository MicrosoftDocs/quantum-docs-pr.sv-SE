---
uid: Microsoft.Quantum.Intrinsic.R
title: R-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199037"
---
# <a name="r-operation"></a><span data-ttu-id="ff814-102">R-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ff814-102">R operation</span></span>

<span data-ttu-id="ff814-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ff814-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ff814-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ff814-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ff814-105">Använder en rotation om den aktuella Pauli-axeln.</span><span class="sxs-lookup"><span data-stu-id="ff814-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="ff814-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align} där $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="ff814-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ff814-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ff814-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ff814-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ff814-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ff814-109">Pauli-operatorn ($ \mu $) ska exponentiated för att forma rotationen.</span><span class="sxs-lookup"><span data-stu-id="ff814-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ff814-110">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff814-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff814-111">Vinkel för vilken qubit ska roteras.</span><span class="sxs-lookup"><span data-stu-id="ff814-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ff814-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ff814-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ff814-113">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ff814-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff814-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff814-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff814-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ff814-115">Remarks</span></span>

<span data-ttu-id="ff814-116">När den anropas `pauli = PauliI` , tillämpar den här åtgärden en *Global fas*.</span><span class="sxs-lookup"><span data-stu-id="ff814-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="ff814-117">Den här fasen kan vara viktig när den används med `Controlled` Functor.</span><span class="sxs-lookup"><span data-stu-id="ff814-117">This phase can be significant when used with the `Controlled` functor.</span></span>