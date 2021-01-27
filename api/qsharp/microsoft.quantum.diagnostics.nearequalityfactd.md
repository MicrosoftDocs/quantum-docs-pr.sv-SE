---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: Funktionen NearEqualityFactD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827898"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="24a5f-102">Funktionen NearEqualityFactD</span><span class="sxs-lookup"><span data-stu-id="24a5f-102">NearEqualityFactD function</span></span>

<span data-ttu-id="24a5f-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="24a5f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="24a5f-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24a5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24a5f-105">Garanterar att ett klassiskt flytt ALS värde har det förväntade värdet upp till en liten tolerans för 1e-10.</span><span class="sxs-lookup"><span data-stu-id="24a5f-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="24a5f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="24a5f-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="24a5f-107">faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24a5f-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24a5f-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="24a5f-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="24a5f-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24a5f-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24a5f-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="24a5f-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24a5f-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24a5f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="24a5f-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="24a5f-112">Remarks</span></span>

<span data-ttu-id="24a5f-113">Detta motsvarar <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> med hårdkodad tolerans på $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="24a5f-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>