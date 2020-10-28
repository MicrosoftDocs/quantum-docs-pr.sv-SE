---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726694"
---
# <a name="expfrac-operation"></a><span data-ttu-id="fcc59-102">ExpFrac-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fcc59-102">ExpFrac operation</span></span>

<span data-ttu-id="fcc59-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fcc59-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fcc59-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcc59-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcc59-105">Använder exponenten för en multi-qubit Pauli-operator med ett argument som angetts av en dyadic-fraktion.</span><span class="sxs-lookup"><span data-stu-id="fcc59-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="fcc59-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align} där $P _i $ är $i $ th-elementet i `paulis` och där $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="fcc59-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fcc59-107">Indata</span><span class="sxs-lookup"><span data-stu-id="fcc59-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="fcc59-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="fcc59-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="fcc59-109">Matris med qubit Pauli-värden som indikerar betalares produkt faktorer på varje qubit.</span><span class="sxs-lookup"><span data-stu-id="fcc59-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="fcc59-110">täljare: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcc59-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcc59-111">Täljare ($k $) i dyadic fraktions representation av den vinkel som qubit-registret ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="fcc59-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="fcc59-112">effekt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcc59-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcc59-113">Kraften hos två ($n $) som anger nämnaren för den vinkel som qubit-registret ska roteras med.</span><span class="sxs-lookup"><span data-stu-id="fcc59-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fcc59-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcc59-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcc59-115">Registrera dig för att tillämpa den aktuella rotationen på.</span><span class="sxs-lookup"><span data-stu-id="fcc59-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcc59-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcc59-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

