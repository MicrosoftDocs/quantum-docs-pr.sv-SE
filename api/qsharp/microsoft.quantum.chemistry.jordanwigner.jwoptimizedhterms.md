---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: JWOptimizedHTerms-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 1588adc0edb95e347616dd6260200c09fee0f190
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837619"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="c5654-102">JWOptimizedHTerms-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="c5654-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="c5654-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c5654-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c5654-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c5654-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c5654-105">Formatet på data som skickas från C# till Q # för att representera Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c5654-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="c5654-106">Innebörden av de data som representeras bestäms av algoritmen som tar emot den.</span><span class="sxs-lookup"><span data-stu-id="c5654-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

