---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kodad funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203186"
---
# <a name="encoded-function"></a><span data-ttu-id="ebd6f-102">Kodad funktion</span><span class="sxs-lookup"><span data-stu-id="ebd6f-102">Encoded function</span></span>

<span data-ttu-id="ebd6f-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ebd6f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ebd6f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebd6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebd6f-105">Koda sanningen-tabellen i {1,-1} kodning</span><span class="sxs-lookup"><span data-stu-id="ebd6f-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ebd6f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ebd6f-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="ebd6f-107">Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ebd6f-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ebd6f-108">Sanningen-tabell som en matris med sanningen-värden</span><span class="sxs-lookup"><span data-stu-id="ebd6f-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="ebd6f-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebd6f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebd6f-110">Sanningen-tabell som matris med {1,-1} heltal</span><span class="sxs-lookup"><span data-stu-id="ebd6f-110">Truth table as array of {1,-1} integers</span></span>