---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853773"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="d9145-102">MeasurePaulis-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d9145-102">MeasurePaulis operation</span></span>

<span data-ttu-id="d9145-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d9145-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d9145-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9145-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9145-105">Med en matris med qubit Pauli-operatörer, mäter varje användning av en angiven mått-gadget och returnerar sedan mat ris resultatet.</span><span class="sxs-lookup"><span data-stu-id="d9145-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="d9145-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d9145-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="d9145-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="d9145-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="d9145-108">Matris med multi-qubit Pauli-operatörer att mäta.</span><span class="sxs-lookup"><span data-stu-id="d9145-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d9145-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d9145-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d9145-110">Registrera dig för att mäta de tilldelade operatörerna.</span><span class="sxs-lookup"><span data-stu-id="d9145-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="d9145-111">gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="d9145-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="d9145-112">Åtgärd som utför mätningen av en specifik multi-qubit-operator.</span><span class="sxs-lookup"><span data-stu-id="d9145-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d9145-113">Utdata: __ogiltigt <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="d9145-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="d9145-114">Matrisen med resultat som erhålls från mätning av varje element i `paulis` på `target` .</span><span class="sxs-lookup"><span data-stu-id="d9145-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>