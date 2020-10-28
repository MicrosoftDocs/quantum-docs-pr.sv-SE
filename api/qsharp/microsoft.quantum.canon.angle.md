---
uid: Microsoft.Quantum.Canon.Angle
title: Funktionen vinkel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729763"
---
# <a name="angle-function"></a><span data-ttu-id="d578f-102">Funktionen vinkel</span><span class="sxs-lookup"><span data-stu-id="d578f-102">Angle function</span></span>

<span data-ttu-id="d578f-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d578f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d578f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d578f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d578f-105">Returnerar 1, om `index` har ett udda antal 1s och-1, om `index` har ett jämnt antal 1s.</span><span class="sxs-lookup"><span data-stu-id="d578f-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d578f-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d578f-106">Description</span></span>

<span data-ttu-id="d578f-107">Värdet motsvarar tecknet för koefficienten för det Rademacher-Walsh spektrumet av n-variabeln och funktionen för en viss tilldelning som bestämmer rotations vinkeln.</span><span class="sxs-lookup"><span data-stu-id="d578f-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="d578f-108">Indata</span><span class="sxs-lookup"><span data-stu-id="d578f-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="d578f-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d578f-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d578f-110">Inmatad tilldelning som heltal (från 0 till 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="d578f-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="d578f-111">Utdata: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d578f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

