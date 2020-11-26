---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210989"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="78cbf-102">ComplexPolar-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="78cbf-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="78cbf-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="78cbf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="78cbf-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78cbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78cbf-105">Representerar ett komplext tal i polär form.</span><span class="sxs-lookup"><span data-stu-id="78cbf-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="78cbf-106">Den polära representationen av ett komplext tal är $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="78cbf-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="78cbf-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="78cbf-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="78cbf-108">Storlek: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78cbf-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78cbf-109">Det absoluta värdet $r \ge $0 av $c $.</span><span class="sxs-lookup"><span data-stu-id="78cbf-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="78cbf-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78cbf-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78cbf-111">Fasen $t \in \mathbb R $ av $c $.</span><span class="sxs-lookup"><span data-stu-id="78cbf-111">The phase $t \in \mathbb R$ of $c$.</span></span>