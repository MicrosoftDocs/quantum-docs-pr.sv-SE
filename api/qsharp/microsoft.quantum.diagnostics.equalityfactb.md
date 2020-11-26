---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: Funktionen EqualityFactB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201928"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="2f327-102">Funktionen EqualityFactB</span><span class="sxs-lookup"><span data-stu-id="2f327-102">EqualityFactB function</span></span>

<span data-ttu-id="2f327-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2f327-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2f327-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f327-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f327-105">Förutsätter att en klassisk bool-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="2f327-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2f327-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2f327-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2f327-107">faktiskt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f327-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f327-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="2f327-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2f327-109">förväntat: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f327-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f327-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="2f327-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2f327-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2f327-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2f327-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="2f327-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f327-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f327-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

