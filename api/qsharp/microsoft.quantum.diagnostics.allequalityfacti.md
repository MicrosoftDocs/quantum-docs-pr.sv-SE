---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Funktionen AllEqualityFactI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223892"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="033b7-102">Funktionen AllEqualityFactI</span><span class="sxs-lookup"><span data-stu-id="033b7-102">AllEqualityFactI function</span></span>

<span data-ttu-id="033b7-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="033b7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="033b7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="033b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="033b7-105">Förutsätter att två matriser med heltals värden är lika.</span><span class="sxs-lookup"><span data-stu-id="033b7-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="033b7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="033b7-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="033b7-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="033b7-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="033b7-108">Matrisen som produceras av ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="033b7-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="033b7-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="033b7-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="033b7-110">Matrisen som förväntas från ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="033b7-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="033b7-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="033b7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="033b7-112">Ett meddelande som ska skrivas ut om matriserna inte är lika.</span><span class="sxs-lookup"><span data-stu-id="033b7-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="033b7-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="033b7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

