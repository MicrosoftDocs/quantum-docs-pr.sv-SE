---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: Funktionen EmptyArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846182"
---
# <a name="emptyarray-function"></a><span data-ttu-id="6be2d-102">Funktionen EmptyArray</span><span class="sxs-lookup"><span data-stu-id="6be2d-102">EmptyArray function</span></span>

<span data-ttu-id="6be2d-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6be2d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6be2d-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6be2d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6be2d-105">Returnerar den tomma matrisen av en specifik typ.</span><span class="sxs-lookup"><span data-stu-id="6be2d-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="6be2d-106">Utdata: ' TElein []</span><span class="sxs-lookup"><span data-stu-id="6be2d-106">Output : 'TElement[]</span></span>

<span data-ttu-id="6be2d-107">Den tomma matrisen.</span><span class="sxs-lookup"><span data-stu-id="6be2d-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6be2d-108">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="6be2d-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="6be2d-109">"Teleteleering"</span><span class="sxs-lookup"><span data-stu-id="6be2d-109">'TElement</span></span>

<span data-ttu-id="6be2d-110">Typ av element i matrisen.</span><span class="sxs-lookup"><span data-stu-id="6be2d-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="6be2d-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="6be2d-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```