---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198630"
---
# <a name="rz-operation"></a><span data-ttu-id="09daf-102">RZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="09daf-102">Rz operation</span></span>

<span data-ttu-id="09daf-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="09daf-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="09daf-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="09daf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="09daf-105">Använder en rotation om $z $-axeln med en viss vinkel.</span><span class="sxs-lookup"><span data-stu-id="09daf-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="09daf-106">\begin{align} R_z (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="09daf-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="09daf-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="09daf-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="09daf-108">Indata</span><span class="sxs-lookup"><span data-stu-id="09daf-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="09daf-109">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="09daf-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="09daf-110">Vinkel för vilken qubit ska roteras.</span><span class="sxs-lookup"><span data-stu-id="09daf-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="09daf-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="09daf-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="09daf-112">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="09daf-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09daf-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09daf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09daf-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="09daf-114">Remarks</span></span>

<span data-ttu-id="09daf-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="09daf-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```