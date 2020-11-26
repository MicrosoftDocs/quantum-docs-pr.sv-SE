---
uid: Microsoft.Quantum.Math.InverseModL
title: Funktionen InverseModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228193"
---
# <a name="inversemodl-function"></a><span data-ttu-id="e6d1a-102">Funktionen InverseModL</span><span class="sxs-lookup"><span data-stu-id="e6d1a-102">InverseModL function</span></span>

<span data-ttu-id="e6d1a-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e6d1a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e6d1a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6d1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6d1a-105">Returnerar $b $ så att $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="e6d1a-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="e6d1a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e6d1a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e6d1a-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e6d1a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e6d1a-108">Talet inverteras</span><span class="sxs-lookup"><span data-stu-id="e6d1a-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="e6d1a-109">Modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e6d1a-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e6d1a-110">Den modul enligt vilken talen inverteras</span><span class="sxs-lookup"><span data-stu-id="e6d1a-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e6d1a-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e6d1a-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e6d1a-112">Integer $b $ så att $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="e6d1a-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>