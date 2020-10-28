---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728596"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="87515-102">LogicalANDMeasAndFix-åtgärd</span><span class="sxs-lookup"><span data-stu-id="87515-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="87515-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87515-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87515-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87515-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87515-105">Beräknar det logiska och flera qubits.</span><span class="sxs-lookup"><span data-stu-id="87515-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="87515-106">Indata</span><span class="sxs-lookup"><span data-stu-id="87515-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="87515-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="87515-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="87515-108">Qubits in i flera ingångar och grindar.</span><span class="sxs-lookup"><span data-stu-id="87515-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="87515-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="87515-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="87515-110">Qubit som utdata från och skrivs till.</span><span class="sxs-lookup"><span data-stu-id="87515-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="87515-111">Detta förutsätter att alltid starta i $ \ket {0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="87515-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87515-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87515-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="87515-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="87515-113">Remarks</span></span>

<span data-ttu-id="87515-114">När `ctrlRegister` har exakt $2 $ qubits motsvarar detta `CCNOT` åtgärden men fasen med en fas $e ^ {i \ Pi/2} $ på $ \ket {001} $ och $-e ^ {i \ Pi/2} $ på $ \ket {101} $ och $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="87515-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="87515-115">Det angränsande är också en metod för att mäta och korrigera som är inversen till den ursprungliga åtgärden endast i specialfall (se referenser), men använder färre T-grindar.</span><span class="sxs-lookup"><span data-stu-id="87515-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="87515-116">Referenser</span><span class="sxs-lookup"><span data-stu-id="87515-116">References</span></span>

- [<span data-ttu-id="87515-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="87515-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)