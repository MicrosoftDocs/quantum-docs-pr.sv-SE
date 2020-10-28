---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727408"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="aad73-102">_assertEqualOnBasisVector åtgärd</span><span class="sxs-lookup"><span data-stu-id="aad73-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="aad73-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="aad73-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="aad73-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aad73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aad73-105">Kontrollerar om resultatet av att tillämpa två åtgärder `givenU` och `expectedU` till gång till ett delstats tillstånd är detsamma.</span><span class="sxs-lookup"><span data-stu-id="aad73-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="aad73-106">Bas status beskrivs av `basis` parameter.</span><span class="sxs-lookup"><span data-stu-id="aad73-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="aad73-107">Se <xref:microsoft.quantum.extensions.fliptobasis> funktion för mer information om den här beskrivningen.</span><span class="sxs-lookup"><span data-stu-id="aad73-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="aad73-108">Indata</span><span class="sxs-lookup"><span data-stu-id="aad73-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="aad73-109">bas: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aad73-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aad73-110">Det grundläggande tillstånd som anges av ett ID för en enskild qubit-basis (0 <= ID <= 3) för var och en av $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="aad73-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="aad73-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aad73-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="aad73-112">Åtgärden på $n $ qubits ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="aad73-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="aad73-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="aad73-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aad73-114">Referens åtgärd på $n $ qubits som givenU ska jämföras med.</span><span class="sxs-lookup"><span data-stu-id="aad73-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aad73-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aad73-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

