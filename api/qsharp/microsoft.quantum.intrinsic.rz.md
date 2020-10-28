---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731347"
---
# <a name="rz-operation"></a><span data-ttu-id="0b7b6-102">RZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="0b7b6-102">Rz operation</span></span>

<span data-ttu-id="0b7b6-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0b7b6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0b7b6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b7b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b7b6-105">Använder en rotation om $z $-axeln med en viss vinkel.</span><span class="sxs-lookup"><span data-stu-id="0b7b6-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="0b7b6-106">\begin{align} R_z (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="0b7b6-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="0b7b6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0b7b6-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0b7b6-108">Indata</span><span class="sxs-lookup"><span data-stu-id="0b7b6-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="0b7b6-109">theta: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b7b6-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b7b6-110">Vinkel för vilken qubit ska roteras.</span><span class="sxs-lookup"><span data-stu-id="0b7b6-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0b7b6-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0b7b6-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0b7b6-112">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="0b7b6-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b7b6-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b7b6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0b7b6-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0b7b6-114">Remarks</span></span>

<span data-ttu-id="0b7b6-115">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="0b7b6-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```