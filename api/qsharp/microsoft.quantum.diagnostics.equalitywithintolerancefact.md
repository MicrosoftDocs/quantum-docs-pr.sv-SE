---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Funktionen EqualityWithinToleranceFact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727234"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="52e90-102">Funktionen EqualityWithinToleranceFact</span><span class="sxs-lookup"><span data-stu-id="52e90-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="52e90-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="52e90-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="52e90-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52e90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52e90-105">Representerar anspråket att ett klassiskt flytt ALS värde har det förväntade värdet upp till en viss absolut tolerans.</span><span class="sxs-lookup"><span data-stu-id="52e90-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="52e90-106">Indata</span><span class="sxs-lookup"><span data-stu-id="52e90-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="52e90-107">faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52e90-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52e90-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="52e90-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="52e90-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52e90-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52e90-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="52e90-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="52e90-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52e90-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52e90-112">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="52e90-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52e90-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52e90-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

