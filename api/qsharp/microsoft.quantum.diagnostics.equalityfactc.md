---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: Funktionen EqualityFactC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853364"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="92890-102">Funktionen EqualityFactC</span><span class="sxs-lookup"><span data-stu-id="92890-102">EqualityFactC function</span></span>

<span data-ttu-id="92890-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="92890-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="92890-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92890-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92890-105">Förutsätter att ett komplext tal har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="92890-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="92890-106">Indata</span><span class="sxs-lookup"><span data-stu-id="92890-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="92890-107">faktiskt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="92890-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="92890-108">Det värde som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="92890-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="92890-109">förväntat: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="92890-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="92890-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="92890-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="92890-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="92890-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="92890-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="92890-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92890-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92890-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

