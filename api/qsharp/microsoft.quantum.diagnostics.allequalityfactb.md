---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Funktionen AllEqualityFactB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213709"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="7b689-102">Funktionen AllEqualityFactB</span><span class="sxs-lookup"><span data-stu-id="7b689-102">AllEqualityFactB function</span></span>

<span data-ttu-id="7b689-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7b689-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7b689-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b689-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b689-105">Förutsätter att två matriser med booleska värden är lika.</span><span class="sxs-lookup"><span data-stu-id="7b689-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7b689-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7b689-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="7b689-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7b689-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7b689-108">Matrisen som produceras av ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="7b689-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="7b689-109">förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7b689-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7b689-110">Matrisen som förväntas från ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="7b689-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="7b689-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7b689-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7b689-112">Ett meddelande som ska skrivas ut om matriserna inte är lika.</span><span class="sxs-lookup"><span data-stu-id="7b689-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b689-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b689-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

