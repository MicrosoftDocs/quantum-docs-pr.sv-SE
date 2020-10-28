---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: Funktionen IdxToUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: a142d8a5af56a43de6341e3c0bdc77f50030f06e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726313"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="2dbbc-102">Funktionen IdxToUnitary</span><span class="sxs-lookup"><span data-stu-id="2dbbc-102">IdxToUnitary function</span></span>

<span data-ttu-id="2dbbc-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2dbbc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2dbbc-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2dbbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2dbbc-105">Används vid implementering av `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="2dbbc-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2dbbc-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2dbbc-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="2dbbc-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2dbbc-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="2dbbc-108">genFun: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2dbbc-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit-adj--ctl"></a><span data-ttu-id="2dbbc-109">genIdxToUnitary: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) rejust + CTL</span><span class="sxs-lookup"><span data-stu-id="2dbbc-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="2dbbc-110">Utdata: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="2dbbc-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="2dbbc-111">Se även</span><span class="sxs-lookup"><span data-stu-id="2dbbc-111">See Also</span></span>

- [<span data-ttu-id="2dbbc-112">Microsoft. Quantum. simulering. PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="2dbbc-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)