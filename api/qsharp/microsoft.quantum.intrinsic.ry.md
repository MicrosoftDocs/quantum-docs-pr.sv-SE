---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Nätverk-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 5a1f762aacca5c72dc8dbe450ab8e8a4aef12c69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198613"
---
# <a name="ry-operation"></a><span data-ttu-id="9fa57-102">Nätverk-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9fa57-102">Ry operation</span></span>

<span data-ttu-id="9fa57-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="9fa57-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="9fa57-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9fa57-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9fa57-105">Använder en rotation om $y $-axeln med en viss vinkel.</span><span class="sxs-lookup"><span data-stu-id="9fa57-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="9fa57-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="9fa57-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="9fa57-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9fa57-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9fa57-108">Indata</span><span class="sxs-lookup"><span data-stu-id="9fa57-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="9fa57-109">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fa57-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fa57-110">Vinkel för vilken qubit ska roteras.</span><span class="sxs-lookup"><span data-stu-id="9fa57-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9fa57-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9fa57-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9fa57-112">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="9fa57-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9fa57-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fa57-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9fa57-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9fa57-114">Remarks</span></span>

<span data-ttu-id="9fa57-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="9fa57-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```