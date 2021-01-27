---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Funktionen ControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840790"
---
# <a name="controlledonint-function"></a><span data-ttu-id="2454f-102">Funktionen ControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="2454f-102">ControlledOnInt function</span></span>

<span data-ttu-id="2454f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2454f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2454f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2454f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2454f-105">Returnerar en enhetlig operator som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar ett angivet positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="2454f-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2454f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2454f-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="2454f-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2454f-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2454f-108">Positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="2454f-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="2454f-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="2454f-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2454f-110">Enhetlig operatör.</span><span class="sxs-lookup"><span data-stu-id="2454f-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="2454f-111">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="2454f-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2454f-112">En enhetlig operatör som gäller `oracle` för mål registret om kontroll registerets tillstånd motsvarar nummer tillstånd `numberState` .</span><span class="sxs-lookup"><span data-stu-id="2454f-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2454f-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="2454f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2454f-114">Inte</span><span class="sxs-lookup"><span data-stu-id="2454f-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2454f-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2454f-115">Remarks</span></span>

<span data-ttu-id="2454f-116">Värdet för `numberState` tolkas med en lite-endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="2454f-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>