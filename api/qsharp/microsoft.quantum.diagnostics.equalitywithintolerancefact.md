---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Funktionen EqualityWithinToleranceFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828756"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="08033-102">Funktionen EqualityWithinToleranceFact</span><span class="sxs-lookup"><span data-stu-id="08033-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="08033-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="08033-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="08033-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08033-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08033-105">Representerar anspråket att ett klassiskt flytt ALS värde har det förväntade värdet upp till en viss absolut tolerans.</span><span class="sxs-lookup"><span data-stu-id="08033-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="08033-106">Indata</span><span class="sxs-lookup"><span data-stu-id="08033-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="08033-107">faktiskt: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08033-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08033-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="08033-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="08033-109">förväntat: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08033-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08033-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="08033-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="08033-111">tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08033-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08033-112">Absolut tolerans för skillnaden mellan faktiskt och förväntat värde.</span><span class="sxs-lookup"><span data-stu-id="08033-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="08033-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08033-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

