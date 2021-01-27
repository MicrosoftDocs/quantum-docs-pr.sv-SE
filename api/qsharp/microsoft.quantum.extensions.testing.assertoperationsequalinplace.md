---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 64cc1e5c78af100b652ced24f00f3097c35ea5d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820228"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="515b2-102">AssertOperationsEqualInPlace-åtgärd</span><span class="sxs-lookup"><span data-stu-id="515b2-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="515b2-103">Namnrymd: [Microsoft. Quantum. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="515b2-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="515b2-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="515b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="515b2-105">AssertOperationsEqualInPlace är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="515b2-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="515b2-106">Använd <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> i stället.</span><span class="sxs-lookup"><span data-stu-id="515b2-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="515b2-107">Använd @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span><span class="sxs-lookup"><span data-stu-id="515b2-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="515b2-108">Observera att ordningen på argumenten för åtgärden har ändrats.</span><span class="sxs-lookup"><span data-stu-id="515b2-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="515b2-109">Indata</span><span class="sxs-lookup"><span data-stu-id="515b2-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="515b2-110">faktiskt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="515b2-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="515b2-111">förväntat: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = just> [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="515b2-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="515b2-112">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="515b2-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="515b2-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="515b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

