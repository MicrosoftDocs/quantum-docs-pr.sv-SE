---
uid: Microsoft.Quantum.Arrays.Reversed
title: Omvänd funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730043"
---
# <a name="reversed-function"></a><span data-ttu-id="71157-102">Omvänd funktion</span><span class="sxs-lookup"><span data-stu-id="71157-102">Reversed function</span></span>

<span data-ttu-id="71157-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="71157-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="71157-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71157-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71157-105">Skapa en matris som innehåller samma element som en inmatad matris men i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="71157-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="71157-106">Indata</span><span class="sxs-lookup"><span data-stu-id="71157-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="71157-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="71157-107">array : 'T[]</span></span>

<span data-ttu-id="71157-108">En matris vars element ska kopieras i omvänd ordning.</span><span class="sxs-lookup"><span data-stu-id="71157-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="71157-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="71157-109">Output : 'T[]</span></span>

<span data-ttu-id="71157-110">En matris som innehåller elementen `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="71157-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="71157-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="71157-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="71157-112">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="71157-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71157-113">Inte</span><span class="sxs-lookup"><span data-stu-id="71157-113">'T</span></span>

<span data-ttu-id="71157-114">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="71157-114">The type of the array elements.</span></span>