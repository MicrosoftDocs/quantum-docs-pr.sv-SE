---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730046"
---
# <a name="rest-function"></a><span data-ttu-id="0e55d-102">Rest-funktion</span><span class="sxs-lookup"><span data-stu-id="0e55d-102">Rest function</span></span>

<span data-ttu-id="0e55d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0e55d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0e55d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e55d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e55d-105">Skapar en matris som är lika med en indataparameter förutom att det första mat ris elementet har släppts.</span><span class="sxs-lookup"><span data-stu-id="0e55d-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0e55d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="0e55d-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="0e55d-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="0e55d-107">array : 'T[]</span></span>

<span data-ttu-id="0e55d-108">En matris vars andra till sista element är att skapa en matris för utdata.</span><span class="sxs-lookup"><span data-stu-id="0e55d-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="0e55d-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="0e55d-109">Output : 'T[]</span></span>

<span data-ttu-id="0e55d-110">En matris som innehåller elementen `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="0e55d-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0e55d-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="0e55d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e55d-112">Inte</span><span class="sxs-lookup"><span data-stu-id="0e55d-112">'T</span></span>

<span data-ttu-id="0e55d-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="0e55d-113">The type of the array elements.</span></span>