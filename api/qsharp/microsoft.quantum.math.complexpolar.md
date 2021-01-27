---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847353"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="cfe43-102">ComplexPolar-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="cfe43-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="cfe43-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cfe43-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cfe43-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfe43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfe43-105">Representerar ett komplext tal i polär form.</span><span class="sxs-lookup"><span data-stu-id="cfe43-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="cfe43-106">Den polära representationen av ett komplext tal är $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="cfe43-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="cfe43-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="cfe43-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="cfe43-108">Storlek: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfe43-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfe43-109">Det absoluta värdet $r \ge $0 av $c $.</span><span class="sxs-lookup"><span data-stu-id="cfe43-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="cfe43-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfe43-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfe43-111">Fasen $t \in \mathbb R $ av $c $.</span><span class="sxs-lookup"><span data-stu-id="cfe43-111">The phase $t \in \mathbb R$ of $c$.</span></span>