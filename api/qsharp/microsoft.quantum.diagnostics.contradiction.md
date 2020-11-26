---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Motstridig funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202149"
---
# <a name="contradiction-function"></a><span data-ttu-id="40cdb-102">Motstridig funktion</span><span class="sxs-lookup"><span data-stu-id="40cdb-102">Contradiction function</span></span>

<span data-ttu-id="40cdb-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="40cdb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="40cdb-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="40cdb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="40cdb-105">Deklarerar att ett klassiskt villkor är falskt.</span><span class="sxs-lookup"><span data-stu-id="40cdb-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="40cdb-106">Indata</span><span class="sxs-lookup"><span data-stu-id="40cdb-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="40cdb-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="40cdb-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="40cdb-108">Villkoret som ska deklareras.</span><span class="sxs-lookup"><span data-stu-id="40cdb-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="40cdb-109">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="40cdb-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="40cdb-110">Fel meddelande strängen som ska skrivas ut om klassiskt villkor är sant.</span><span class="sxs-lookup"><span data-stu-id="40cdb-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40cdb-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40cdb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="40cdb-112">Se även</span><span class="sxs-lookup"><span data-stu-id="40cdb-112">See Also</span></span>

- [<span data-ttu-id="40cdb-113">Microsoft. Quantum. Diagnostics. faktumet</span><span class="sxs-lookup"><span data-stu-id="40cdb-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)