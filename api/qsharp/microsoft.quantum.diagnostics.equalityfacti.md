---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: Funktionen EqualityFactI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853355"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="ffeb6-102">Funktionen EqualityFactI</span><span class="sxs-lookup"><span data-stu-id="ffeb6-102">EqualityFactI function</span></span>

<span data-ttu-id="ffeb6-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ffeb6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffeb6-105">Förutsätter att en klassisk int-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ffeb6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="ffeb6-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="ffeb6-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffeb6-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="ffeb6-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffeb6-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ffeb6-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ffeb6-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ffeb6-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ffeb6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

