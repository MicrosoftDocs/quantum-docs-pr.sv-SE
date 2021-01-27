---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Funktionen AllEqualityFactI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830893"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="80435-102">Funktionen AllEqualityFactI</span><span class="sxs-lookup"><span data-stu-id="80435-102">AllEqualityFactI function</span></span>

<span data-ttu-id="80435-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="80435-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="80435-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80435-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80435-105">Förutsätter att två matriser med heltals värden är lika.</span><span class="sxs-lookup"><span data-stu-id="80435-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="80435-106">Indata</span><span class="sxs-lookup"><span data-stu-id="80435-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="80435-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="80435-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="80435-108">Matrisen som produceras av ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="80435-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="80435-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="80435-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="80435-110">Matrisen som förväntas från ett test fall av intresse.</span><span class="sxs-lookup"><span data-stu-id="80435-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="80435-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="80435-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="80435-112">Ett meddelande som ska skrivas ut om matriserna inte är lika.</span><span class="sxs-lookup"><span data-stu-id="80435-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80435-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80435-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

