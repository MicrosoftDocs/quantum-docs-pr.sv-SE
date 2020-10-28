---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Funktionen AllEqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727375"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="89b7d-102">Funktionen AllEqualityFactB</span><span class="sxs-lookup"><span data-stu-id="89b7d-102">AllEqualityFactB function</span></span>

<span data-ttu-id="89b7d-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="89b7d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="89b7d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89b7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89b7d-105">Förutsätter att två matriser med booleska värden är lika.</span><span class="sxs-lookup"><span data-stu-id="89b7d-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="89b7d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="89b7d-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="89b7d-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="89b7d-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="89b7d-108">Matrisen som produceras av ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="89b7d-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="89b7d-109">förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="89b7d-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="89b7d-110">Matrisen som förväntas från ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="89b7d-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="89b7d-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="89b7d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="89b7d-112">Ett meddelande som ska skrivas ut om matriserna inte är lika.</span><span class="sxs-lookup"><span data-stu-id="89b7d-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89b7d-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89b7d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

