---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Återställ åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727003"
---
# <a name="recover-operation"></a><span data-ttu-id="3f8e1-102">Återställ åtgärd</span><span class="sxs-lookup"><span data-stu-id="3f8e1-102">Recover operation</span></span>

<span data-ttu-id="3f8e1-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3f8e1-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f8e1-105">Utför en enskild avrundning av fel korrigering med en Quantum-kod som beskrivs av en `QECC` typ.</span><span class="sxs-lookup"><span data-stu-id="3f8e1-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="3f8e1-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3f8e1-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="3f8e1-107">kod: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="3f8e1-108">Ett Quantum-fel – korrigering av kod paketerad som en `QECC` typ beskriver kodning och avkodning av Quantum-data och hur fel syndromes ska mätas.</span><span class="sxs-lookup"><span data-stu-id="3f8e1-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="3f8e1-109">FN: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="3f8e1-110">En `RecoveryFn` som mappar varje fel Syndrome till de `Pauli[]` åtgärder som korrigerar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="3f8e1-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="3f8e1-111">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3f8e1-112">En matris med qubits där stabiliserings koden definieras.</span><span class="sxs-lookup"><span data-stu-id="3f8e1-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f8e1-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f8e1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3f8e1-114">Se även</span><span class="sxs-lookup"><span data-stu-id="3f8e1-114">See Also</span></span>

- [<span data-ttu-id="3f8e1-115">Microsoft. Quantum. ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="3f8e1-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="3f8e1-116">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="3f8e1-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="3f8e1-117">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3f8e1-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)