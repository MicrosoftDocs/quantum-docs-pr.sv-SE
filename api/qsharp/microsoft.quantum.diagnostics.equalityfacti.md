---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: Funktionen EqualityFactI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201843"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="7829d-102">Funktionen EqualityFactI</span><span class="sxs-lookup"><span data-stu-id="7829d-102">EqualityFactI function</span></span>

<span data-ttu-id="7829d-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7829d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7829d-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7829d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7829d-105">Förutsätter att en klassisk int-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="7829d-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7829d-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7829d-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="7829d-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7829d-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7829d-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="7829d-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="7829d-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7829d-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7829d-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="7829d-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="7829d-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7829d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7829d-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="7829d-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7829d-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7829d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

