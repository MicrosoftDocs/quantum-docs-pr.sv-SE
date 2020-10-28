---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731675"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="245b1-102">BigEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="245b1-102">BigEndian user defined type</span></span>

<span data-ttu-id="245b1-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="245b1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="245b1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="245b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="245b1-105">Registrera att koda ett osignerat heltal i big-endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="245b1-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="245b1-106">Qubit med index `0` kodar den högsta biten av ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="245b1-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="245b1-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="245b1-107">Remarks</span></span>

<span data-ttu-id="245b1-108">Vi förkortar `BigEndian` som `BE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="245b1-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>