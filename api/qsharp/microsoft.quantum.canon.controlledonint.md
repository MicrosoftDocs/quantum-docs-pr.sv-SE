---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Funktionen ControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728806"
---
# <a name="controlledonint-function"></a><span data-ttu-id="02404-102">Funktionen ControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="02404-102">ControlledOnInt function</span></span>

<span data-ttu-id="02404-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02404-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02404-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02404-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02404-105">Returnerar en enhetlig operator som tillämpar en Oracle på mål registret om kontroll registerets tillstånd motsvarar ett angivet positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="02404-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="02404-106">Indata</span><span class="sxs-lookup"><span data-stu-id="02404-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="02404-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02404-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="02404-108">Positivt heltal.</span><span class="sxs-lookup"><span data-stu-id="02404-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="02404-109">Oracle: t => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="02404-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="02404-110">Enhetlig operatör.</span><span class="sxs-lookup"><span data-stu-id="02404-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="02404-111">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], inte) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="02404-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="02404-112">En enhetlig operatör som gäller `oracle` för mål registret om kontroll registerets tillstånd motsvarar nummer tillstånd `numberState` .</span><span class="sxs-lookup"><span data-stu-id="02404-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02404-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="02404-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02404-114">Inte</span><span class="sxs-lookup"><span data-stu-id="02404-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="02404-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="02404-115">Remarks</span></span>

<span data-ttu-id="02404-116">Värdet för `numberState` tolkas med en lite-endian-kodning.</span><span class="sxs-lookup"><span data-stu-id="02404-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>