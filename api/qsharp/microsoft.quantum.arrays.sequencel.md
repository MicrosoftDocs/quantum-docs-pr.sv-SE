---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850990"
---
# <a name="sequencel-function"></a><span data-ttu-id="47d5e-102">Funktionen Sequence</span><span class="sxs-lookup"><span data-stu-id="47d5e-102">SequenceL function</span></span>

<span data-ttu-id="47d5e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="47d5e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="47d5e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47d5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47d5e-105">Hämta en matris med heltal inom ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="47d5e-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="47d5e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="47d5e-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="47d5e-107">från: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="47d5e-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="47d5e-108">Ett inklusiv start index för intervallet.</span><span class="sxs-lookup"><span data-stu-id="47d5e-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="47d5e-109">till: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="47d5e-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="47d5e-110">Ett partiellt slut index för intervallet som inte är mindre än `from` .</span><span class="sxs-lookup"><span data-stu-id="47d5e-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="47d5e-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="47d5e-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="47d5e-112">En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="47d5e-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="example"></a><span data-ttu-id="47d5e-113">Exempel</span><span class="sxs-lookup"><span data-stu-id="47d5e-113">Example</span></span>

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a><span data-ttu-id="47d5e-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="47d5e-114">Remarks</span></span>

<span data-ttu-id="47d5e-115">Skillnaden mellan `from` och `to` måste passa in i ett `Int` värde.</span><span class="sxs-lookup"><span data-stu-id="47d5e-115">The difference between `from` and `to` must fit into an `Int` value.</span></span>