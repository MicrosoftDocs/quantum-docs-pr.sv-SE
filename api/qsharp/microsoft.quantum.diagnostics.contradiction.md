---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Motstridig funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829371"
---
# <a name="contradiction-function"></a><span data-ttu-id="e9c44-102">Motstridig funktion</span><span class="sxs-lookup"><span data-stu-id="e9c44-102">Contradiction function</span></span>

<span data-ttu-id="e9c44-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e9c44-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e9c44-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e9c44-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e9c44-105">Deklarerar att ett klassiskt villkor är falskt.</span><span class="sxs-lookup"><span data-stu-id="e9c44-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e9c44-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e9c44-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e9c44-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9c44-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9c44-108">Villkoret som ska deklareras.</span><span class="sxs-lookup"><span data-stu-id="e9c44-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e9c44-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e9c44-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e9c44-110">Fel meddelande strängen som ska skrivas ut om klassiskt villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="e9c44-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9c44-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9c44-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="e9c44-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="e9c44-112">Example</span></span>

<span data-ttu-id="e9c44-113">Följande Q #-kod skriver ut "Hello, World":</span><span class="sxs-lookup"><span data-stu-id="e9c44-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="e9c44-114">Se även</span><span class="sxs-lookup"><span data-stu-id="e9c44-114">See Also</span></span>

- [<span data-ttu-id="e9c44-115">Microsoft. Quantum. Diagnostics. faktumet</span><span class="sxs-lookup"><span data-stu-id="e9c44-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)