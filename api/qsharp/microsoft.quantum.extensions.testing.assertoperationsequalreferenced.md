---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 1f4d98006677dc532d45ffb797fe0a8e05496640
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820092"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="612c6-102">AssertOperationsEqualReferenced-åtgärd</span><span class="sxs-lookup"><span data-stu-id="612c6-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="612c6-103">Namnrymd: [Microsoft. Quantum. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="612c6-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="612c6-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="612c6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="612c6-105">AssertOperationsEqualReferenced är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="612c6-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="612c6-106">Använd <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> i stället.</span><span class="sxs-lookup"><span data-stu-id="612c6-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="612c6-107">Använd @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span><span class="sxs-lookup"><span data-stu-id="612c6-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="612c6-108">Observera att ordningen på argumenten för åtgärden har ändrats.</span><span class="sxs-lookup"><span data-stu-id="612c6-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="612c6-109">Indata</span><span class="sxs-lookup"><span data-stu-id="612c6-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="612c6-110">faktiskt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="612c6-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="612c6-111">förväntat: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = just> [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="612c6-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="612c6-112">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="612c6-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="612c6-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="612c6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

