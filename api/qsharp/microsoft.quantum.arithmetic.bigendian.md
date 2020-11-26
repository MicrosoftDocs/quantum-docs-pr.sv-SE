---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223671"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="c8745-102">BigEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="c8745-102">BigEndian user defined type</span></span>

<span data-ttu-id="c8745-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c8745-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c8745-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8745-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8745-105">Registrera att koda ett osignerat heltal i big-endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="c8745-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="c8745-106">Qubit med index `0` kodar den högsta biten av ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="c8745-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c8745-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c8745-107">Remarks</span></span>

<span data-ttu-id="c8745-108">Vi förkortar `BigEndian` som `BE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="c8745-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>