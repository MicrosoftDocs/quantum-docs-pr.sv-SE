---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: Funktionen DumpRegister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 9623d6d881f1f0ec048c3a951fe259bdfac84766
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202030"
---
# <a name="dumpregister-function"></a><span data-ttu-id="f61e4-102">Funktionen DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f61e4-102">DumpRegister function</span></span>

<span data-ttu-id="f61e4-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f61e4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f61e4-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f61e4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f61e4-105">Dumpar den aktuella mål datorns status som är associerad med den angivna qubits.</span><span class="sxs-lookup"><span data-stu-id="f61e4-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f61e4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="f61e4-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="f61e4-107">plats: ' t '</span><span class="sxs-lookup"><span data-stu-id="f61e4-107">location : 'T</span></span>

<span data-ttu-id="f61e4-108">Innehåller information om var tillståndets dump ska skapas.</span><span class="sxs-lookup"><span data-stu-id="f61e4-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f61e4-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f61e4-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f61e4-110">Listan över qubits som ska rapporteras.</span><span class="sxs-lookup"><span data-stu-id="f61e4-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f61e4-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f61e4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="f61e4-112">Inga.</span><span class="sxs-lookup"><span data-stu-id="f61e4-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f61e4-113">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="f61e4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f61e4-114">Inte</span><span class="sxs-lookup"><span data-stu-id="f61e4-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f61e4-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="f61e4-115">Remarks</span></span>

<span data-ttu-id="f61e4-116">Med den här metoden kan du dumpa den information som är associerad med statusen för den aktuella qubits till en fil eller någon annan plats.</span><span class="sxs-lookup"><span data-stu-id="f61e4-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="f61e4-117">Den faktiska informationen som genereras och semantiken för `location` är specifika för varje måldator.</span><span class="sxs-lookup"><span data-stu-id="f61e4-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="f61e4-118">Men att tillhandahålla en tom tupel som en plats ( `()` ) innebär vanligt vis att generera utdata till-konsolen.</span><span class="sxs-lookup"><span data-stu-id="f61e4-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="f61e4-119">För att den lokala fullständiga tillstånds simulatorn ska distribueras som en del av Quantum Development Kit förväntar den här metoden en sträng med sökvägen till en fil där den skriver den angivna qubits (d.v.s. våg funktionen i motsvarande del system) som en endimensionell matris med komplexa tal, där varje element representerar amplituderna för sannolikheten för att mäta motsvarande tillstånd.</span><span class="sxs-lookup"><span data-stu-id="f61e4-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="f61e4-120">Om den aktuella qubits är Entangled med vissa andra qubit och deras status inte kan avgränsas, så rapporterar den bara att qubits är Entangled.</span><span class="sxs-lookup"><span data-stu-id="f61e4-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>