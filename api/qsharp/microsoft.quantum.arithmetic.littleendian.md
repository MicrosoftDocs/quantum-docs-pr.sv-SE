---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222787"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="2f35c-102">LittleEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="2f35c-102">LittleEndian user defined type</span></span>

<span data-ttu-id="2f35c-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2f35c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2f35c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f35c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f35c-105">Registrera att koda ett osignerat heltal i litet endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="2f35c-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="2f35c-106">Qubit med index `0` kodar den lägsta biten i ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="2f35c-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="2f35c-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="2f35c-107">Remarks</span></span>

<span data-ttu-id="2f35c-108">Vi förkortar `LittleEndian` som `LE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="2f35c-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>