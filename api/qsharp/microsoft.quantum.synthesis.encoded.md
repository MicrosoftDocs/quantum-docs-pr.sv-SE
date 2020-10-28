---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kodad funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733907"
---
# <a name="encoded-function"></a><span data-ttu-id="34289-102">Kodad funktion</span><span class="sxs-lookup"><span data-stu-id="34289-102">Encoded function</span></span>

<span data-ttu-id="34289-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="34289-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="34289-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34289-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34289-105">Koda sanningen-tabellen i {1,-1} kodning</span><span class="sxs-lookup"><span data-stu-id="34289-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="34289-106">Indata</span><span class="sxs-lookup"><span data-stu-id="34289-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="34289-107">Tabell: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="34289-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="34289-108">Sanningen-tabell som en matris med sanningen-värden</span><span class="sxs-lookup"><span data-stu-id="34289-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="34289-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="34289-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="34289-110">Sanningen-tabell som matris med {1,-1} heltal</span><span class="sxs-lookup"><span data-stu-id="34289-110">Truth table as array of {1,-1} integers</span></span>