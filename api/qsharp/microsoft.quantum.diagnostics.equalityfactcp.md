---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: Funktionen EqualityFactCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201860"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="19896-102">Funktionen EqualityFactCP</span><span class="sxs-lookup"><span data-stu-id="19896-102">EqualityFactCP function</span></span>

<span data-ttu-id="19896-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="19896-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="19896-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19896-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19896-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="19896-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="19896-106">Indata</span><span class="sxs-lookup"><span data-stu-id="19896-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="19896-107">faktiskt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="19896-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="19896-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="19896-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="19896-109">förväntat: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="19896-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="19896-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="19896-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="19896-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="19896-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="19896-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="19896-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19896-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19896-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

