---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223756"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="2e6ca-102">AssertPhaseLessThan-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2e6ca-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="2e6ca-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2e6ca-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2e6ca-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e6ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e6ca-105">Förutsätter att den `number` kodade i PhaseLittleEndian är mindre än `value` .</span><span class="sxs-lookup"><span data-stu-id="2e6ca-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2e6ca-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2e6ca-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2e6ca-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e6ca-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e6ca-108">`number` måste vara mindre än så.</span><span class="sxs-lookup"><span data-stu-id="2e6ca-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="2e6ca-109">nummer: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2e6ca-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="2e6ca-110">Osignerat heltal som jämförs med `value` .</span><span class="sxs-lookup"><span data-stu-id="2e6ca-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e6ca-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e6ca-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e6ca-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2e6ca-112">Remarks</span></span>

<span data-ttu-id="2e6ca-113">Den kontrollerade versionen av den här åtgärden ignorerar kontroller.</span><span class="sxs-lookup"><span data-stu-id="2e6ca-113">The controlled version of this operation ignores controls.</span></span>