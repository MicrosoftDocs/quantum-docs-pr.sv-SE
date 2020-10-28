---
uid: Microsoft.Quantum.Intrinsic.Rx
title: RX-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732934"
---
# <a name="rx-operation"></a><span data-ttu-id="5dd47-102">RX-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5dd47-102">Rx operation</span></span>

<span data-ttu-id="5dd47-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5dd47-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5dd47-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dd47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dd47-105">Använder en rotation om $x $-axeln med en viss vinkel.</span><span class="sxs-lookup"><span data-stu-id="5dd47-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="5dd47-106">\begin{align} R_x (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="5dd47-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="5dd47-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5dd47-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5dd47-108">Indata</span><span class="sxs-lookup"><span data-stu-id="5dd47-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="5dd47-109">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5dd47-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5dd47-110">Vinkel för vilken qubit ska roteras.</span><span class="sxs-lookup"><span data-stu-id="5dd47-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5dd47-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5dd47-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5dd47-112">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="5dd47-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5dd47-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dd47-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dd47-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5dd47-114">Remarks</span></span>

<span data-ttu-id="5dd47-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="5dd47-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```