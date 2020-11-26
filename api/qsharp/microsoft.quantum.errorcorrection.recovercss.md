---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: eb01b1b9fccc19f0e3f1fd5ee596b95d0d61563f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200551"
---
# <a name="recovercss-operation"></a><span data-ttu-id="6bcab-102">RecoverCSS-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6bcab-102">RecoverCSS operation</span></span>

<span data-ttu-id="6bcab-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6bcab-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6bcab-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bcab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bcab-105">Utför en enskild avrundning av fel korrigering med en Quantum-kod som beskrivs av en `CSS` typ.</span><span class="sxs-lookup"><span data-stu-id="6bcab-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="6bcab-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6bcab-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="6bcab-107">kod: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="6bcab-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="6bcab-108">En Quantum CSS-felkorrigering kod paketerad som en `CSS` typ beskriver kodning och avkodning av Quantum-data och hur fel syndromes ska mätas.</span><span class="sxs-lookup"><span data-stu-id="6bcab-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="6bcab-109">fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="6bcab-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="6bcab-110">En `RecoveryFn` som mappar varje $X $-fel Syndrome till de `Pauli[]` åtgärder som korrigerar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="6bcab-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="6bcab-111">fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="6bcab-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="6bcab-112">En `RecoveryFn` som mappar varje $Z $-fel Syndrome till de `Pauli[]` åtgärder som korrigerar det identifierade felet.</span><span class="sxs-lookup"><span data-stu-id="6bcab-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="6bcab-113">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="6bcab-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="6bcab-114">En matris med qubits där stabiliserings koden definieras.</span><span class="sxs-lookup"><span data-stu-id="6bcab-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bcab-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bcab-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6bcab-116">Se även</span><span class="sxs-lookup"><span data-stu-id="6bcab-116">See Also</span></span>

- [<span data-ttu-id="6bcab-117">Microsoft. Quantum. ErrorCorrection. CSS</span><span class="sxs-lookup"><span data-stu-id="6bcab-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="6bcab-118">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="6bcab-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="6bcab-119">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="6bcab-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)