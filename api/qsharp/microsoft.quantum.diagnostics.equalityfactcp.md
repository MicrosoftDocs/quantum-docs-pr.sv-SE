---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: Funktionen EqualityFactCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829177"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="6e5c0-102">Funktionen EqualityFactCP</span><span class="sxs-lookup"><span data-stu-id="6e5c0-102">EqualityFactCP function</span></span>

<span data-ttu-id="6e5c0-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6e5c0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e5c0-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="6e5c0-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6e5c0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6e5c0-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="6e5c0-107">faktiskt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6e5c0-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="6e5c0-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="6e5c0-109">förväntat: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6e5c0-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="6e5c0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6e5c0-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6e5c0-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="6e5c0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e5c0-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e5c0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

