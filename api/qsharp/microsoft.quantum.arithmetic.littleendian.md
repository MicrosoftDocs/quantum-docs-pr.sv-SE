---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846571"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="3b3a0-102">LittleEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="3b3a0-102">LittleEndian user defined type</span></span>

<span data-ttu-id="3b3a0-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3b3a0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3b3a0-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b3a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b3a0-105">Registrera att koda ett osignerat heltal i litet endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="3b3a0-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="3b3a0-106">Qubit med index `0` kodar den lägsta biten i ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="3b3a0-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="3b3a0-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3b3a0-107">Remarks</span></span>

<span data-ttu-id="3b3a0-108">Vi förkortar `LittleEndian` som `LE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="3b3a0-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>