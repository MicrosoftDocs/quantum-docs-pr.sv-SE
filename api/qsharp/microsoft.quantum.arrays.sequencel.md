---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funktionen Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730022"
---
# <a name="sequencel-function"></a><span data-ttu-id="0878d-102">Funktionen Sequence</span><span class="sxs-lookup"><span data-stu-id="0878d-102">SequenceL function</span></span>

<span data-ttu-id="0878d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0878d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0878d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0878d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0878d-105">Hämta en matris med heltal inom ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="0878d-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="0878d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0878d-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="0878d-107">från: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0878d-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0878d-108">Ett inklusiv start index för intervallet.</span><span class="sxs-lookup"><span data-stu-id="0878d-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="0878d-109">till: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0878d-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0878d-110">Ett partiellt slut index för intervallet som inte är mindre än `from` .</span><span class="sxs-lookup"><span data-stu-id="0878d-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="0878d-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="0878d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="0878d-112">En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="0878d-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0878d-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0878d-113">Remarks</span></span>

<span data-ttu-id="0878d-114">Skillnaden mellan `from` och `to` måste passa in i ett `Int` värde.</span><span class="sxs-lookup"><span data-stu-id="0878d-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>