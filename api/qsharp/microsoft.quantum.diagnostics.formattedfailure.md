---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Funktionen FormattedFailure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727204"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="4ddf8-102">Funktionen FormattedFailure</span><span class="sxs-lookup"><span data-stu-id="4ddf8-102">FormattedFailure function</span></span>

<span data-ttu-id="4ddf8-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4ddf8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4ddf8-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4ddf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4ddf8-105">Intern funktion som används för att rapportera fel i meningsfulla fel meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4ddf8-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4ddf8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="4ddf8-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="4ddf8-107">faktiskt: ' t</span><span class="sxs-lookup"><span data-stu-id="4ddf8-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="4ddf8-108">förväntat: ' t</span><span class="sxs-lookup"><span data-stu-id="4ddf8-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="4ddf8-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4ddf8-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="4ddf8-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ddf8-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4ddf8-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="4ddf8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4ddf8-112">Inte</span><span class="sxs-lookup"><span data-stu-id="4ddf8-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="4ddf8-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4ddf8-113">Remarks</span></span>

<span data-ttu-id="4ddf8-114">Den här funktionen är avsedd att emuleras av simulerings körningar, så att du kan tillåta vidarebefordrande motstridiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="4ddf8-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>