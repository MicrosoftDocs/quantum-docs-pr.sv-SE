---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Motstridig funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727285"
---
# <a name="contradiction-function"></a><span data-ttu-id="14e18-102">Motstridig funktion</span><span class="sxs-lookup"><span data-stu-id="14e18-102">Contradiction function</span></span>

<span data-ttu-id="14e18-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="14e18-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="14e18-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14e18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14e18-105">Deklarerar att ett klassiskt villkor är falskt.</span><span class="sxs-lookup"><span data-stu-id="14e18-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="14e18-106">Indata</span><span class="sxs-lookup"><span data-stu-id="14e18-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="14e18-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="14e18-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="14e18-108">Villkoret som ska deklareras.</span><span class="sxs-lookup"><span data-stu-id="14e18-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="14e18-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="14e18-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="14e18-110">Fel meddelande strängen som ska skrivas ut om klassiskt villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="14e18-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14e18-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e18-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="14e18-112">Se även</span><span class="sxs-lookup"><span data-stu-id="14e18-112">See Also</span></span>

- [<span data-ttu-id="14e18-113">Microsoft. Quantum. Diagnostics. faktumet</span><span class="sxs-lookup"><span data-stu-id="14e18-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)