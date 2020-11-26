---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: eb2dd8750ed5ad9fc75ca24bb4c8ef36298f69f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198783"
---
# <a name="r1frac-operation"></a><span data-ttu-id="ac4f9-102">R1Frac-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ac4f9-102">R1Frac operation</span></span>

<span data-ttu-id="ac4f9-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ac4f9-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ac4f9-105">Använder en rotation för $ \ket {1} $-läget med en vinkel angiven som en dyadic fraktion.</span><span class="sxs-lookup"><span data-stu-id="ac4f9-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="ac4f9-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="ac4f9-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="ac4f9-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ac4f9-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="ac4f9-108">Den här åtgärden använder **motsatt** inloggnings konvention från @"microsoft.quantum.intrinsic.r" och inkluderar inte faktorn på $1/2 $ som ingår i @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="ac4f9-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac4f9-109">Indata</span><span class="sxs-lookup"><span data-stu-id="ac4f9-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ac4f9-110">täljare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac4f9-111">Täljare i dyadic fraktions representation av den vinkel som qubit ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="ac4f9-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="ac4f9-112">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac4f9-113">Kraften hos två anger nämnaren för den vinkel som qubit ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="ac4f9-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ac4f9-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac4f9-115">Qubit som porten ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="ac4f9-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac4f9-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac4f9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ac4f9-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ac4f9-117">Remarks</span></span>

<span data-ttu-id="ac4f9-118">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="ac4f9-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```