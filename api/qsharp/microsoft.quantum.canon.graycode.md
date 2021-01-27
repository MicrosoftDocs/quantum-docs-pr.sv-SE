---
uid: Microsoft.Quantum.Canon.GrayCode
title: Funktionen GrayCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840504"
---
# <a name="graycode-function"></a><span data-ttu-id="3102a-102">Funktionen GrayCode</span><span class="sxs-lookup"><span data-stu-id="3102a-102">GrayCode function</span></span>

<span data-ttu-id="3102a-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3102a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3102a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3102a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3102a-105">Skapar grå kod sekvenser</span><span class="sxs-lookup"><span data-stu-id="3102a-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="3102a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3102a-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="3102a-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3102a-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3102a-108">Antal bitar</span><span class="sxs-lookup"><span data-stu-id="3102a-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="3102a-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="3102a-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="3102a-110">Matris med tupler.</span><span class="sxs-lookup"><span data-stu-id="3102a-110">Array of tuples.</span></span> <span data-ttu-id="3102a-111">Det första värdet i tuppeln är ett värde i GrayCode-sekvensens andra värde i tuppeln är positionen att ändra i det aktuella värdet för att hämta nästa.</span><span class="sxs-lookup"><span data-stu-id="3102a-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="3102a-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="3102a-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```