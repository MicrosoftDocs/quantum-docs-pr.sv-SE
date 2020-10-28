---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725905"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="2c3d2-102">ComplexPolar-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="2c3d2-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="2c3d2-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2c3d2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2c3d2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c3d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c3d2-105">Representerar ett komplext tal i polär form.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="2c3d2-106">Den polära representationen av ett komplext tal är $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="2c3d2-107">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="2c3d2-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="2c3d2-108">Storlek: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c3d2-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c3d2-109">Det absoluta värdet $r \ge $0 av $c $.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="2c3d2-110">Argument: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c3d2-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c3d2-111">Fasen $t \in \mathbb R $ av $c $.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-111">The phase $t \in \mathbb R$ of $c$.</span></span>