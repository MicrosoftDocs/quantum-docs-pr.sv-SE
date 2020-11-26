---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Funktionen EqualityWithinToleranceFact
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201724"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="980d8-102">Funktionen EqualityWithinToleranceFact</span><span class="sxs-lookup"><span data-stu-id="980d8-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="980d8-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="980d8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="980d8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="980d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="980d8-105">Representerar anspråket att ett klassiskt flytt ALS värde har det förväntade värdet upp till en viss absolut tolerans.</span><span class="sxs-lookup"><span data-stu-id="980d8-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="980d8-106">Indata</span><span class="sxs-lookup"><span data-stu-id="980d8-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="980d8-107">faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="980d8-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="980d8-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="980d8-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="980d8-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="980d8-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="980d8-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="980d8-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="980d8-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="980d8-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="980d8-112">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="980d8-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="980d8-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="980d8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

