---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852535"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="f29ec-102">MultiplexOperations-åtgärd</span><span class="sxs-lookup"><span data-stu-id="f29ec-102">MultiplexOperations operation</span></span>

<span data-ttu-id="f29ec-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f29ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f29ec-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f29ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f29ec-105">Tillämpar en matris med åtgärder som styrs av en matris med tal tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f29ec-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="f29ec-106">Det vill säga använder en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="f29ec-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="f29ec-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="f29ec-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f29ec-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f29ec-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="f29ec-109">unitaries: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL []</span><span class="sxs-lookup"><span data-stu-id="f29ec-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="f29ec-110">Matris med upp till $2 ^ n $-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f29ec-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="f29ec-111">$J $ th indexeras av Number State $ \ket{j} $ som kodats i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="f29ec-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="f29ec-112">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f29ec-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f29ec-113">$n $-qubit Control register som kodar nummer tillstånden $ \ket{j} $ i litet endian-format.</span><span class="sxs-lookup"><span data-stu-id="f29ec-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="f29ec-114">mål: ' t</span><span class="sxs-lookup"><span data-stu-id="f29ec-114">target : 'T</span></span>

<span data-ttu-id="f29ec-115">Allmän qubit-registrering som $V _j $ agerar på.</span><span class="sxs-lookup"><span data-stu-id="f29ec-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f29ec-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f29ec-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f29ec-117">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f29ec-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f29ec-118">Inte</span><span class="sxs-lookup"><span data-stu-id="f29ec-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f29ec-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f29ec-119">Remarks</span></span>

<span data-ttu-id="f29ec-120">`coefficients` fylls i med identitets element om färre än $2 ^ n $ anges.</span><span class="sxs-lookup"><span data-stu-id="f29ec-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="f29ec-121">Den här implementeringen använder $n-$1-hjälp qubits.</span><span class="sxs-lookup"><span data-stu-id="f29ec-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="f29ec-122">Referenser</span><span class="sxs-lookup"><span data-stu-id="f29ec-122">References</span></span>

- <span data-ttu-id="f29ec-123">Mot den första Quantum-simuleringen med Quantum SpeedUp Andrew M. Children, Dmitri Maslov, Yunseongt, Neil J. Värskogsnätverksväxling, Yuan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="f29ec-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>