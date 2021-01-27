---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851101"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="4d4cb-102">ApplyDeltaParity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="4d4cb-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="4d4cb-103">Namnrymd: [Microsoft. Quantum. Research. kemi](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4d4cb-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="4d4cb-104">Paket: [Microsoft. Quantum. Research. kemi](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4d4cb-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="4d4cb-105">Beräknar skillnad i paritet mellan en tidigare PQRS... villkor och nästa PQRS... löp.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="4d4cb-106">Den här skillnaden beräknas på en extra qubit.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4d4cb-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4d4cb-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="4d4cb-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4d4cb-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4d4cb-109">Lista över index för tidigare PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="4d4cb-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4d4cb-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4d4cb-111">Lista över index till nästa PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="4d4cb-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4d4cb-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4d4cb-113">Tilläggs-qubit till vilka paritets beräknings resultat lagras.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4d4cb-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d4cb-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d4cb-115">Qubit handlade av alla PQRS... begreppen.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d4cb-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d4cb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d4cb-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4d4cb-117">Remarks</span></span>

<span data-ttu-id="4d4cb-118">Detta förutsätter att index på P < Q < R < S <... för både prevPQ och nextPQ.</span><span class="sxs-lookup"><span data-stu-id="4d4cb-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>