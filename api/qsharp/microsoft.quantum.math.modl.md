---
uid: Microsoft.Quantum.Math.ModL
title: Funktionen ModL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732707"
---
# <a name="modl-function"></a><span data-ttu-id="6d7f9-102">Funktionen ModL</span><span class="sxs-lookup"><span data-stu-id="6d7f9-102">ModL function</span></span>

<span data-ttu-id="6d7f9-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6d7f9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6d7f9-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d7f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d7f9-105">Returnerar Modulus av ett tal med avseende på ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="6d7f9-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="6d7f9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6d7f9-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6d7f9-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6d7f9-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6d7f9-108">Indatamängden $a $ vars Modulus ska returneras.</span><span class="sxs-lookup"><span data-stu-id="6d7f9-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="6d7f9-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6d7f9-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6d7f9-110">Talet som används för att returnera modulen för $a $.</span><span class="sxs-lookup"><span data-stu-id="6d7f9-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="6d7f9-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6d7f9-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6d7f9-112">Modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="6d7f9-112">The modulus $a \bmod b$.</span></span>