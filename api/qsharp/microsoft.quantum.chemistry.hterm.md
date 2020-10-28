---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728143"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="d2278-102">HTerm-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="d2278-102">HTerm user defined type</span></span>

<span data-ttu-id="d2278-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d2278-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="d2278-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2278-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2278-105">Formatet på data som skickas från C# till Q # för att representera en term i Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d2278-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="d2278-106">Innebörden av de data som representeras bestäms av algoritmen som tar emot den.</span><span class="sxs-lookup"><span data-stu-id="d2278-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

