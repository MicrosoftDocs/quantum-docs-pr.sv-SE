---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: Funktionen DumpMachine
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727288"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="8bcb9-102">Funktionen DumpMachine</span><span class="sxs-lookup"><span data-stu-id="8bcb9-102">DumpMachine function</span></span>

<span data-ttu-id="8bcb9-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8bcb9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8bcb9-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bcb9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bcb9-105">Dumpar den aktuella mål datorns status.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="8bcb9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8bcb9-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="8bcb9-107">plats: ' t '</span><span class="sxs-lookup"><span data-stu-id="8bcb9-107">location : 'T</span></span>

<span data-ttu-id="8bcb9-108">Innehåller information om var datorns dump ska genereras.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8bcb9-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bcb9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="8bcb9-110">Inga.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8bcb9-111">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="8bcb9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8bcb9-112">Inte</span><span class="sxs-lookup"><span data-stu-id="8bcb9-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="8bcb9-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="8bcb9-113">Remarks</span></span>

<span data-ttu-id="8bcb9-114">Med den här metoden kan du dumpa information om mål datorns aktuella status till en fil eller någon annan plats.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="8bcb9-115">Den faktiska informationen som genereras och semantiken för `location` är specifika för varje måldator.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="8bcb9-116">Men att ange en tom tupel som en plats ( `()` ) eller utesluta `location` parametern vanligt vis innebär att du genererar utdata till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="8bcb9-117">För att den lokala fullständiga tillstånds simulatorn ska distribueras som en del av Quantum Development Kit förväntar den här metoden en sträng med sökvägen till en fil där den skriver vågen som en endimensionell matris med komplexa tal, där varje element representerar amplituderna för sannolikheten för att mäta motsvarande tillstånd.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>