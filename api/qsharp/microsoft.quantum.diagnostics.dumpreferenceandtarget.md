---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: ef7e59b1561be04cba5839ebc397702b6c1df5bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202047"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="fc4bd-102">DumpReferenceAndTarget-åtgärd</span><span class="sxs-lookup"><span data-stu-id="fc4bd-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="fc4bd-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fc4bd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc4bd-105">Använder DumpRegister för att ge diagnostik för status för en referens-och mål registrering.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="fc4bd-106">Skriven som separat åtgärd för att tillåta åsidosättning och tolkning som separata register, i stället för en enda kombinerad registrering.</span><span class="sxs-lookup"><span data-stu-id="fc4bd-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fc4bd-107">Indata</span><span class="sxs-lookup"><span data-stu-id="fc4bd-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="fc4bd-108">Referens: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fc4bd-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="fc4bd-109">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fc4bd-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc4bd-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc4bd-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

