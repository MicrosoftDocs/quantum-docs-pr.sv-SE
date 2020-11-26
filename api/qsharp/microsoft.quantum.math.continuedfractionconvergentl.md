---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: Funktionen ContinuedFractionConvergentL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c10fcbbe63d3d4c7d6c56196768c1062be1ca350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210938"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="6ea14-102">Funktionen ContinuedFractionConvergentL</span><span class="sxs-lookup"><span data-stu-id="6ea14-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="6ea14-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ea14-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ea14-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ea14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ea14-105">Söker efter den fortsatta fraktions Convergent som ligger närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6ea14-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="6ea14-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6ea14-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="6ea14-107">bråk: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="6ea14-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="6ea14-108">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ea14-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="6ea14-109">Utdata: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="6ea14-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="6ea14-110">Fortsatt bråk som är närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6ea14-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>