---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: Funktionen EqualityFactC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201911"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="4ad99-102">Funktionen EqualityFactC</span><span class="sxs-lookup"><span data-stu-id="4ad99-102">EqualityFactC function</span></span>

<span data-ttu-id="4ad99-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4ad99-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4ad99-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ad99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ad99-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="4ad99-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4ad99-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4ad99-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="4ad99-107">faktiskt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4ad99-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4ad99-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="4ad99-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="4ad99-109">förväntat: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="4ad99-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="4ad99-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="4ad99-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="4ad99-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4ad99-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4ad99-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="4ad99-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ad99-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ad99-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

