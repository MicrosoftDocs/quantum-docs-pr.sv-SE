---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844849"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="177d5-102">ApplyMultiplyControlledAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="177d5-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="177d5-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="177d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="177d5-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="177d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="177d5-105">Implementerar en Toffoli-grind med flera regler, förutsatt att mål qubit initieras 0.</span><span class="sxs-lookup"><span data-stu-id="177d5-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="177d5-106">Den angränsande aktiviteten förutsätter att mål-qubit kommer att återställas till 0.</span><span class="sxs-lookup"><span data-stu-id="177d5-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="177d5-107">Indata</span><span class="sxs-lookup"><span data-stu-id="177d5-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="177d5-108">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="177d5-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="177d5-109">Kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="177d5-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="177d5-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="177d5-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="177d5-111">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="177d5-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="177d5-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="177d5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

