---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fakta funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853313"
---
# <a name="fact-function"></a><span data-ttu-id="16592-102">Fakta funktion</span><span class="sxs-lookup"><span data-stu-id="16592-102">Fact function</span></span>

<span data-ttu-id="16592-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="16592-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="16592-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16592-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16592-105">Deklarerar att ett klassiskt villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="16592-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="16592-106">Indata</span><span class="sxs-lookup"><span data-stu-id="16592-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="16592-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16592-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16592-108">Villkoret som ska deklareras.</span><span class="sxs-lookup"><span data-stu-id="16592-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="16592-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="16592-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="16592-110">Fel meddelande strängen som ska skrivas ut om klassiskt villkor är falskt.</span><span class="sxs-lookup"><span data-stu-id="16592-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16592-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16592-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="16592-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="16592-112">Example</span></span>

<span data-ttu-id="16592-113">Följande Q #-kodfragment kommer att Miss Missing:</span><span class="sxs-lookup"><span data-stu-id="16592-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="16592-114">Se även</span><span class="sxs-lookup"><span data-stu-id="16592-114">See Also</span></span>

- [<span data-ttu-id="16592-115">Microsoft. Quantum. Diagnostics. motstridighet</span><span class="sxs-lookup"><span data-stu-id="16592-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)