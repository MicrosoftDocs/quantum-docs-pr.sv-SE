---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: Funktionen EqualityFactC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727249"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="07795-102">Funktionen EqualityFactC</span><span class="sxs-lookup"><span data-stu-id="07795-102">EqualityFactC function</span></span>

<span data-ttu-id="07795-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="07795-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="07795-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07795-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07795-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="07795-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="07795-106">Indata</span><span class="sxs-lookup"><span data-stu-id="07795-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="07795-107">faktiskt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="07795-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="07795-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="07795-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="07795-109">förväntat: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="07795-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="07795-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="07795-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="07795-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="07795-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="07795-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="07795-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07795-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07795-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

