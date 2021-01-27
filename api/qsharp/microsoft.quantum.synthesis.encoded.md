---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kodad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855483"
---
# <a name="encoded-function"></a><span data-ttu-id="b6b1b-102">Kodad funktion</span><span class="sxs-lookup"><span data-stu-id="b6b1b-102">Encoded function</span></span>

<span data-ttu-id="b6b1b-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b6b1b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b6b1b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6b1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6b1b-105">Koda sanningen-tabellen i {1,-1} kodning</span><span class="sxs-lookup"><span data-stu-id="b6b1b-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b6b1b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b6b1b-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="b6b1b-107">Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b6b1b-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b6b1b-108">Sanningen-tabell som en matris med sanningen-värden</span><span class="sxs-lookup"><span data-stu-id="b6b1b-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="b6b1b-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6b1b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6b1b-110">Sanningen-tabell som matris med {1,-1} heltal</span><span class="sxs-lookup"><span data-stu-id="b6b1b-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="b6b1b-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="b6b1b-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```