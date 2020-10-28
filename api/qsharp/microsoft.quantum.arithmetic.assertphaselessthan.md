---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731686"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="4c6d7-102">AssertPhaseLessThan-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4c6d7-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="4c6d7-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4c6d7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4c6d7-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c6d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c6d7-105">Förutsätter att den `number` kodade i PhaseLittleEndian är mindre än `value` .</span><span class="sxs-lookup"><span data-stu-id="4c6d7-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4c6d7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4c6d7-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="4c6d7-107">värde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c6d7-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c6d7-108">`number` måste vara mindre än så.</span><span class="sxs-lookup"><span data-stu-id="4c6d7-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="4c6d7-109">nummer: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4c6d7-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="4c6d7-110">Osignerat heltal som jämförs med `value` .</span><span class="sxs-lookup"><span data-stu-id="4c6d7-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c6d7-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c6d7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4c6d7-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4c6d7-112">Remarks</span></span>

<span data-ttu-id="4c6d7-113">Den kontrollerade versionen av den här åtgärden ignorerar kontroller.</span><span class="sxs-lookup"><span data-stu-id="4c6d7-113">The controlled version of this operation ignores controls.</span></span>