---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731467"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="ff62c-102">LittleEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="ff62c-102">LittleEndian user defined type</span></span>

<span data-ttu-id="ff62c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ff62c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ff62c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff62c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff62c-105">Registrera att koda ett osignerat heltal i litet endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="ff62c-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="ff62c-106">Qubit med index `0` kodar den lägsta biten i ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="ff62c-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ff62c-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ff62c-107">Remarks</span></span>

<span data-ttu-id="ff62c-108">Vi förkortar `LittleEndian` som `LE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="ff62c-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>