---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakta funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727207"
---
# <a name="fact-function"></a><span data-ttu-id="93480-102">Fakta funktion</span><span class="sxs-lookup"><span data-stu-id="93480-102">Fact function</span></span>

<span data-ttu-id="93480-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="93480-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="93480-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93480-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93480-105">Deklarerar att ett klassiskt villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="93480-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="93480-106">Indata</span><span class="sxs-lookup"><span data-stu-id="93480-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="93480-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93480-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93480-108">Villkoret som ska deklareras.</span><span class="sxs-lookup"><span data-stu-id="93480-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="93480-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="93480-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="93480-110">Fel meddelande strängen som ska skrivas ut om klassiskt villkor är falskt.</span><span class="sxs-lookup"><span data-stu-id="93480-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93480-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93480-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="93480-112">Se även</span><span class="sxs-lookup"><span data-stu-id="93480-112">See Also</span></span>

- [<span data-ttu-id="93480-113">Microsoft. Quantum. Diagnostics. motstridighet</span><span class="sxs-lookup"><span data-stu-id="93480-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)