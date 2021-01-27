---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Funktionen GreaterThanD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 26a963645758b6de83654304c38830af5c561b3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849225"
---
# <a name="greaterthand-function"></a><span data-ttu-id="b9c0e-102">Funktionen GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="b9c0e-102">GreaterThanD function</span></span>

<span data-ttu-id="b9c0e-103">Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b9c0e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9c0e-105">Returnerar true om och endast om ett tal är större än ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b9c0e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b9c0e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b9c0e-107">a: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b9c0e-108">Det första värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b9c0e-109">b: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b9c0e-110">Det andra värdet som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="b9c0e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b9c0e-111">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b9c0e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b9c0e-112">`true` om och bara om `a` är strikt större än `b` .</span><span class="sxs-lookup"><span data-stu-id="b9c0e-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9c0e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b9c0e-113">Remarks</span></span>

<span data-ttu-id="b9c0e-114">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="b9c0e-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanD(a, b);
```