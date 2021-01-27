---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: Funktionen ContinuedFractionConvergentL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 14f0eee5565b3e80f4090a2d3763ef96c928368d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856395"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="85f52-102">Funktionen ContinuedFractionConvergentL</span><span class="sxs-lookup"><span data-stu-id="85f52-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="85f52-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="85f52-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="85f52-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85f52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85f52-105">Söker efter den fortsatta fraktions Convergent som ligger närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="85f52-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="85f52-106">Indata</span><span class="sxs-lookup"><span data-stu-id="85f52-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="85f52-107">bråk: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="85f52-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="85f52-108">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="85f52-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="85f52-109">Utdata: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="85f52-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="85f52-110">Fortsatt bråk som är närmast `fraction` med nämnaren mindre än eller lika med `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="85f52-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>