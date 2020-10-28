---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced-åtgärd
ms.date: 10/26/2020 12:00:00 AM
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
ms.openlocfilehash: 2d39f74c68e48d2f2b8003b76885c9444056f8d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726751"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="930a9-102">AssertOperationsEqualReferenced-åtgärd</span><span class="sxs-lookup"><span data-stu-id="930a9-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="930a9-103">Namnrymd: [Microsoft. Quantum. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="930a9-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="930a9-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="930a9-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="930a9-105">AssertOperationsEqualReferenced är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="930a9-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="930a9-106">Använd <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> i stället.</span><span class="sxs-lookup"><span data-stu-id="930a9-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="930a9-107">Använd @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span><span class="sxs-lookup"><span data-stu-id="930a9-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="930a9-108">Observera att ordningen på argumenten för åtgärden har ändrats.</span><span class="sxs-lookup"><span data-stu-id="930a9-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="930a9-109">Indata</span><span class="sxs-lookup"><span data-stu-id="930a9-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="930a9-110">faktiskt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="930a9-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="930a9-111">förväntat: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="930a9-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="930a9-112">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="930a9-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="930a9-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="930a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

