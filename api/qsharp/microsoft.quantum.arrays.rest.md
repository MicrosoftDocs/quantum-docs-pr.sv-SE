---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845481"
---
# <a name="rest-function"></a><span data-ttu-id="5a16c-102">Rest-funktion</span><span class="sxs-lookup"><span data-stu-id="5a16c-102">Rest function</span></span>

<span data-ttu-id="5a16c-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5a16c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5a16c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a16c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a16c-105">Skapar en matris som är lika med en indataparameter förutom att det första mat ris elementet har släppts.</span><span class="sxs-lookup"><span data-stu-id="5a16c-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5a16c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5a16c-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="5a16c-107">matris: ' ' []</span><span class="sxs-lookup"><span data-stu-id="5a16c-107">array : 'T[]</span></span>

<span data-ttu-id="5a16c-108">En matris vars andra till sista element är att skapa en matris för utdata.</span><span class="sxs-lookup"><span data-stu-id="5a16c-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5a16c-109">Utdata: ' t []</span><span class="sxs-lookup"><span data-stu-id="5a16c-109">Output : 'T[]</span></span>

<span data-ttu-id="5a16c-110">En matris som innehåller elementen `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="5a16c-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5a16c-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="5a16c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a16c-112">Inte</span><span class="sxs-lookup"><span data-stu-id="5a16c-112">'T</span></span>

<span data-ttu-id="5a16c-113">Typ av mat ris element.</span><span class="sxs-lookup"><span data-stu-id="5a16c-113">The type of the array elements.</span></span>