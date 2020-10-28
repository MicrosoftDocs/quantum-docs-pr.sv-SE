---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733206"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="6af4a-102">ApplyDeltaParity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6af4a-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="6af4a-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6af4a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="6af4a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6af4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6af4a-105">Beräknar skillnad i paritet mellan en tidigare PQRS... villkor och nästa PQRS... löp.</span><span class="sxs-lookup"><span data-stu-id="6af4a-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="6af4a-106">Den här skillnaden beräknas på en extra qubit.</span><span class="sxs-lookup"><span data-stu-id="6af4a-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6af4a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="6af4a-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="6af4a-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6af4a-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6af4a-109">Lista över index för tidigare PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="6af4a-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="6af4a-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6af4a-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6af4a-111">Lista över index till nästa PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="6af4a-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="6af4a-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6af4a-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6af4a-113">Tilläggs-qubit till vilka paritets beräknings resultat lagras.</span><span class="sxs-lookup"><span data-stu-id="6af4a-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6af4a-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6af4a-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6af4a-115">Qubit handlade av alla PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="6af4a-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6af4a-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6af4a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6af4a-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6af4a-117">Remarks</span></span>

<span data-ttu-id="6af4a-118">Detta förutsätter att index på P < Q < R < S <... för både prevPQ och nextPQ.</span><span class="sxs-lookup"><span data-stu-id="6af4a-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>