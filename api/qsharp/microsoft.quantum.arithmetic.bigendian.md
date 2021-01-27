---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843382"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="becb9-102">BigEndian-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="becb9-102">BigEndian user defined type</span></span>

<span data-ttu-id="becb9-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="becb9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="becb9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="becb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="becb9-105">Registrera att koda ett osignerat heltal i big-endian-ordning.</span><span class="sxs-lookup"><span data-stu-id="becb9-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="becb9-106">Qubit med index `0` kodar den högsta biten av ett osignerat heltal.</span><span class="sxs-lookup"><span data-stu-id="becb9-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="becb9-107">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="becb9-107">Remarks</span></span>

<span data-ttu-id="becb9-108">Vi förkortar `BigEndian` som `BE` i dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="becb9-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>