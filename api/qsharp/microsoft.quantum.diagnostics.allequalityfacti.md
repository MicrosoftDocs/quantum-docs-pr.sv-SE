---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Funktionen AllEqualityFactI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727372"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="8d3a1-102">Funktionen AllEqualityFactI</span><span class="sxs-lookup"><span data-stu-id="8d3a1-102">AllEqualityFactI function</span></span>

<span data-ttu-id="8d3a1-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8d3a1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8d3a1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d3a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d3a1-105">Förutsätter att två matriser med heltals värden är lika.</span><span class="sxs-lookup"><span data-stu-id="8d3a1-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8d3a1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8d3a1-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="8d3a1-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d3a1-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d3a1-108">Matrisen som produceras av ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="8d3a1-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="8d3a1-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8d3a1-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8d3a1-110">Matrisen som förväntas från ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="8d3a1-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="8d3a1-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8d3a1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8d3a1-112">Ett meddelande som ska skrivas ut om matriserna inte är lika.</span><span class="sxs-lookup"><span data-stu-id="8d3a1-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d3a1-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d3a1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

