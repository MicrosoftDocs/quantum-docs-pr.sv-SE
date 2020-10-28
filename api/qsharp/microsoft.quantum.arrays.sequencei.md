---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Funktionen Sequencer
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730035"
---
# <a name="sequencei-function"></a><span data-ttu-id="00867-102">Funktionen Sequencer</span><span class="sxs-lookup"><span data-stu-id="00867-102">SequenceI function</span></span>

<span data-ttu-id="00867-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="00867-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="00867-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00867-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00867-105">Hämta en matris med heltal inom ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="00867-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="00867-106">Indata</span><span class="sxs-lookup"><span data-stu-id="00867-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="00867-107">från: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00867-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00867-108">Ett inklusiv start index för intervallet.</span><span class="sxs-lookup"><span data-stu-id="00867-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="00867-109">till: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00867-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00867-110">Ett partiellt slut index för intervallet som inte är mindre än `from` .</span><span class="sxs-lookup"><span data-stu-id="00867-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="00867-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="00867-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="00867-112">En matris som innehåller sekvensen med tal `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="00867-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>