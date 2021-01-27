---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Funktionen FormattedFailure
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828283"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="99d7f-102">Funktionen FormattedFailure</span><span class="sxs-lookup"><span data-stu-id="99d7f-102">FormattedFailure function</span></span>

<span data-ttu-id="99d7f-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="99d7f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="99d7f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99d7f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99d7f-105">Intern funktion som används för att rapportera fel i meningsfulla fel meddelanden.</span><span class="sxs-lookup"><span data-stu-id="99d7f-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="99d7f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="99d7f-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="99d7f-107">faktiskt: ' t</span><span class="sxs-lookup"><span data-stu-id="99d7f-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="99d7f-108">förväntat: ' t</span><span class="sxs-lookup"><span data-stu-id="99d7f-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="99d7f-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="99d7f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="99d7f-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99d7f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99d7f-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="99d7f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99d7f-112">Inte</span><span class="sxs-lookup"><span data-stu-id="99d7f-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="99d7f-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="99d7f-113">Remarks</span></span>

<span data-ttu-id="99d7f-114">Den här funktionen är avsedd att emuleras av simulerings körningar, så att du kan tillåta vidarebefordrande motstridiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="99d7f-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>