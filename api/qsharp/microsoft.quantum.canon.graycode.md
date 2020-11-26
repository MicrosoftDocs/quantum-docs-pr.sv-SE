---
uid: Microsoft.Quantum.Canon.GrayCode
title: Funktionen GrayCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206892"
---
# <a name="graycode-function"></a><span data-ttu-id="35468-102">Funktionen GrayCode</span><span class="sxs-lookup"><span data-stu-id="35468-102">GrayCode function</span></span>

<span data-ttu-id="35468-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35468-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35468-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35468-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35468-105">Skapar grå kod sekvenser</span><span class="sxs-lookup"><span data-stu-id="35468-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="35468-106">Indata</span><span class="sxs-lookup"><span data-stu-id="35468-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="35468-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35468-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35468-108">Antal bitar</span><span class="sxs-lookup"><span data-stu-id="35468-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="35468-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="35468-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="35468-110">Matris med tupler.</span><span class="sxs-lookup"><span data-stu-id="35468-110">Array of tuples.</span></span> <span data-ttu-id="35468-111">Det första värdet i tuppeln är ett värde i GrayCode-sekvensens andra värde i tuppeln är positionen att ändra i det aktuella värdet för att hämta nästa.</span><span class="sxs-lookup"><span data-stu-id="35468-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>