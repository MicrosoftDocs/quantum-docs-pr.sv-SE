---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: Funktionen EqualityFactCP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727243"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="f7945-102">Funktionen EqualityFactCP</span><span class="sxs-lookup"><span data-stu-id="f7945-102">EqualityFactCP function</span></span>

<span data-ttu-id="f7945-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f7945-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f7945-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7945-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7945-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="f7945-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f7945-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f7945-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="f7945-107">faktiskt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f7945-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f7945-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="f7945-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="f7945-109">förväntat: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f7945-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f7945-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="f7945-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="f7945-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f7945-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f7945-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="f7945-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7945-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7945-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

