---
uid: Microsoft.Quantum.Simulation._AddGeneratorSystems
title: _AddGeneratorSystems funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: 3bce9faf229f3b1f683e060437ec08da795ef185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726361"
---
# <a name="_addgeneratorsystems-function"></a><span data-ttu-id="9c32e-102">_AddGeneratorSystems funktion</span><span class="sxs-lookup"><span data-stu-id="9c32e-102">_AddGeneratorSystems function</span></span>

<span data-ttu-id="9c32e-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9c32e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9c32e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c32e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c32e-105">Lägger till två `GeneratorSystem` s för att skapa en ny `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="9c32e-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function _AddGeneratorSystems (idxTerm : Int, nTermsA : Int, nTermsB : Int, generatorIndexFunctionA : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), generatorIndexFunctionB : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="9c32e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9c32e-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="9c32e-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c32e-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ntermsa--int"></a><span data-ttu-id="9c32e-108">nTermsA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c32e-108">nTermsA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ntermsb--int"></a><span data-ttu-id="9c32e-109">nTermsB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c32e-109">nTermsB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorindexfunctiona--int---generatorindex"></a><span data-ttu-id="9c32e-110">generatorIndexFunctionA: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9c32e-110">generatorIndexFunctionA : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="generatorindexfunctionb--int---generatorindex"></a><span data-ttu-id="9c32e-111">generatorIndexFunctionB: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9c32e-111">generatorIndexFunctionB : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="9c32e-112">Utdata: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9c32e-112">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="9c32e-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9c32e-113">Remarks</span></span>

<span data-ttu-id="9c32e-114">Detta är ett mellanliggande steg och ska inte anropas.</span><span class="sxs-lookup"><span data-stu-id="9c32e-114">This is an intermediate step and should not be called.</span></span>