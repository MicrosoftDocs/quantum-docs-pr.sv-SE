---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: Funktionen EqualityFactI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727240"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="1b463-102">Funktionen EqualityFactI</span><span class="sxs-lookup"><span data-stu-id="1b463-102">EqualityFactI function</span></span>

<span data-ttu-id="1b463-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1b463-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1b463-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b463-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b463-105">Förutsätter att en klassisk int-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="1b463-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1b463-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1b463-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="1b463-107">faktiskt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b463-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b463-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="1b463-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="1b463-109">förväntat: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b463-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b463-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="1b463-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1b463-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1b463-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1b463-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="1b463-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b463-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b463-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

