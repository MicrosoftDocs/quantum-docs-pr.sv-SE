---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859264"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="87eb6-102">ApplyUnitary-åtgärd</span><span class="sxs-lookup"><span data-stu-id="87eb6-102">ApplyUnitary operation</span></span>

<span data-ttu-id="87eb6-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="87eb6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="87eb6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87eb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87eb6-105">Tillämpar den grind som definieras av 2 ^ n x 2 ^ n, enhetlig matris.</span><span class="sxs-lookup"><span data-stu-id="87eb6-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="87eb6-106">Miss lyckas om matrisen inte är enhetlig eller har fel storlek.</span><span class="sxs-lookup"><span data-stu-id="87eb6-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="87eb6-107">Indata</span><span class="sxs-lookup"><span data-stu-id="87eb6-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="87eb6-108">enhetligt: [komplex](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="87eb6-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="87eb6-109">2 ^ n x 2 ^ n en enhetlig matris som beskriver åtgärden.</span><span class="sxs-lookup"><span data-stu-id="87eb6-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="87eb6-110">Om matrisen inte är enhetlig eller inte av lämplig storlek, utlöses ett undantag.</span><span class="sxs-lookup"><span data-stu-id="87eb6-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="87eb6-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="87eb6-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="87eb6-112">Qubits som använder åtgärden-registrera för längd n.</span><span class="sxs-lookup"><span data-stu-id="87eb6-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87eb6-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87eb6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

