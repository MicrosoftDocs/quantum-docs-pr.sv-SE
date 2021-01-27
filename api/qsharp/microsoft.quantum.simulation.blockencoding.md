---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857639"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="24278-102">BlockEncoding-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="24278-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="24278-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="24278-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="24278-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24278-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24278-105">Representerar en topp där en operator av intresse är kodad i det övre vänstra blocket.</span><span class="sxs-lookup"><span data-stu-id="24278-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="24278-106">Det vill säga att det är `BlockEncoding` en topp $U $ där en godtycklig operatör $H $ av intresse som agerar på system registret `s` är kodad i det övre vänstra blocket som motsvarar hjälp tillstånd $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="24278-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="24278-107">Det är</span><span class="sxs-lookup"><span data-stu-id="24278-107">That is,</span></span>

<span data-ttu-id="24278-108">$ $ \begin{align} (\bra {0} _A \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="24278-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

