---
uid: Microsoft.Quantum.Canon.GrayCode
title: Funktionen GrayCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728698"
---
# <a name="graycode-function"></a><span data-ttu-id="db8fd-102">Funktionen GrayCode</span><span class="sxs-lookup"><span data-stu-id="db8fd-102">GrayCode function</span></span>

<span data-ttu-id="db8fd-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db8fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db8fd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db8fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db8fd-105">Skapar grå kod sekvenser</span><span class="sxs-lookup"><span data-stu-id="db8fd-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="db8fd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="db8fd-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="db8fd-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db8fd-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db8fd-108">Antal bitar</span><span class="sxs-lookup"><span data-stu-id="db8fd-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="db8fd-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="db8fd-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="db8fd-110">Matris med tupler.</span><span class="sxs-lookup"><span data-stu-id="db8fd-110">Array of tuples.</span></span> <span data-ttu-id="db8fd-111">Det första värdet i tuppeln är ett värde i GrayCode-sekvensens andra värde i tuppeln är positionen att ändra i det aktuella värdet för att hämta nästa.</span><span class="sxs-lookup"><span data-stu-id="db8fd-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>