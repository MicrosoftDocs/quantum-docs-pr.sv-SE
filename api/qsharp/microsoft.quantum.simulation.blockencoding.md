---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732470"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="85e8d-102">BlockEncoding-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="85e8d-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="85e8d-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="85e8d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="85e8d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="85e8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="85e8d-105">Representerar en topp där en operator av intresse är kodad i det övre vänstra blocket.</span><span class="sxs-lookup"><span data-stu-id="85e8d-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="85e8d-106">Det vill säga att det är `BlockEncoding` en topp $U $ där en godtycklig operatör $H $ av intresse som agerar på system registret `s` är kodad i det övre vänstra blocket som motsvarar hjälp tillstånd $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="85e8d-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="85e8d-107">Det är</span><span class="sxs-lookup"><span data-stu-id="85e8d-107">That is,</span></span>

<span data-ttu-id="85e8d-108">$ $ \begin{align} (\bra {0} _A \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="85e8d-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```
