---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: Funktionen NearEqualityFactD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201520"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="9d7c5-102">Funktionen NearEqualityFactD</span><span class="sxs-lookup"><span data-stu-id="9d7c5-102">NearEqualityFactD function</span></span>

<span data-ttu-id="9d7c5-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9d7c5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9d7c5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d7c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d7c5-105">Garanterar att ett klassiskt flytt ALS värde har det förväntade värdet upp till en liten tolerans för 1e-10.</span><span class="sxs-lookup"><span data-stu-id="9d7c5-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9d7c5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9d7c5-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="9d7c5-107">faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d7c5-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d7c5-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="9d7c5-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="9d7c5-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d7c5-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d7c5-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="9d7c5-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d7c5-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d7c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d7c5-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9d7c5-112">Remarks</span></span>

<span data-ttu-id="9d7c5-113">Detta motsvarar <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> med hårdkodad tolerans på $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="9d7c5-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>