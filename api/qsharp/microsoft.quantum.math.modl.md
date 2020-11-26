---
uid: Microsoft.Quantum.Math.ModL
title: Funktionen ModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227802"
---
# <a name="modl-function"></a><span data-ttu-id="a00f5-102">Funktionen ModL</span><span class="sxs-lookup"><span data-stu-id="a00f5-102">ModL function</span></span>

<span data-ttu-id="a00f5-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a00f5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a00f5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a00f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a00f5-105">Returnerar Modulus av ett tal med avseende på ett annat tal.</span><span class="sxs-lookup"><span data-stu-id="a00f5-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="a00f5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a00f5-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a00f5-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a00f5-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a00f5-108">Indatamängden $a $ vars Modulus ska returneras.</span><span class="sxs-lookup"><span data-stu-id="a00f5-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a00f5-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a00f5-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a00f5-110">Talet som används för att returnera modulen för $a $.</span><span class="sxs-lookup"><span data-stu-id="a00f5-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a00f5-111">Utdata: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a00f5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a00f5-112">Modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="a00f5-112">The modulus $a \bmod b$.</span></span>