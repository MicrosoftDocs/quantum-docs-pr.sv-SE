---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 1cb3a3cf1e16b194eebd1574da6f9934fc34e5f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734222"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="a1b6e-102">TimeDependentBlockEncoding-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="a1b6e-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="a1b6e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a1b6e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a1b6e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1b6e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1b6e-105">Representerar en `BlockEncoding` som styrs av en klock registrering.</span><span class="sxs-lookup"><span data-stu-id="a1b6e-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="a1b6e-106">Det vill säga att en `TimeDependentBlockEncoding` är en topp $U $ som styrs av ett tillstånd $ \ket{k} _D $ i klock registrering `d` , så att en godtycklig operatör $H _k $ av intresse som agerar i system registret `s` är kodad i det övre vänstra blocket som motsvarar hjälp läget $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="a1b6e-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="a1b6e-107">Det är</span><span class="sxs-lookup"><span data-stu-id="a1b6e-107">That is,</span></span>

<span data-ttu-id="a1b6e-108">$ $ \begin{align} (\bra {0} \_ a\otimes I_ {DS}) U (\ket {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="a1b6e-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="a1b6e-109">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="a1b6e-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

