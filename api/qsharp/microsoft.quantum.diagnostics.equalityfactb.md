---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: Funktionen EqualityFactB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829210"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="c4754-102">Funktionen EqualityFactB</span><span class="sxs-lookup"><span data-stu-id="c4754-102">EqualityFactB function</span></span>

<span data-ttu-id="c4754-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c4754-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c4754-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4754-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4754-105">Förutsätter att en klassisk bool-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="c4754-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c4754-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c4754-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="c4754-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4754-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4754-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="c4754-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="c4754-109">förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4754-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4754-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="c4754-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="c4754-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c4754-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c4754-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="c4754-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4754-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4754-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

