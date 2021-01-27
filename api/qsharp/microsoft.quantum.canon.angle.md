---
uid: Microsoft.Quantum.Canon.Angle
title: Funktionen vinkel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842041"
---
# <a name="angle-function"></a><span data-ttu-id="13092-102">Funktionen vinkel</span><span class="sxs-lookup"><span data-stu-id="13092-102">Angle function</span></span>

<span data-ttu-id="13092-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="13092-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="13092-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13092-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13092-105">Returnerar 1, om `index` har ett udda antal 1s och-1, om `index` har ett jämnt antal 1s.</span><span class="sxs-lookup"><span data-stu-id="13092-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="13092-106">Description</span><span class="sxs-lookup"><span data-stu-id="13092-106">Description</span></span>

<span data-ttu-id="13092-107">Värdet motsvarar tecknet för koefficienten för det Rademacher-Walsh spektrumet av n-variabeln och funktionen för en viss tilldelning som bestämmer rotations vinkeln.</span><span class="sxs-lookup"><span data-stu-id="13092-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="13092-108">Indata</span><span class="sxs-lookup"><span data-stu-id="13092-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="13092-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13092-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13092-110">Inmatad tilldelning som heltal (från 0 till 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="13092-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="13092-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13092-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

