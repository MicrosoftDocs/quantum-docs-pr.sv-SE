---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: Funktionen EqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727246"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="2abbd-102">Funktionen EqualityFactB</span><span class="sxs-lookup"><span data-stu-id="2abbd-102">EqualityFactB function</span></span>

<span data-ttu-id="2abbd-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2abbd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2abbd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2abbd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2abbd-105">Förutsätter att en klassisk bool-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="2abbd-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2abbd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2abbd-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2abbd-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2abbd-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2abbd-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="2abbd-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2abbd-109">förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2abbd-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2abbd-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="2abbd-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2abbd-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2abbd-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2abbd-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="2abbd-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2abbd-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2abbd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

