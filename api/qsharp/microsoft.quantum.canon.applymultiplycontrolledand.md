---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729466"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="deffd-102">ApplyMultiplyControlledAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="deffd-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="deffd-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="deffd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="deffd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="deffd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="deffd-105">Implementerar en Toffoli-grind med flera regler, förutsatt att mål qubit initieras 0.</span><span class="sxs-lookup"><span data-stu-id="deffd-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="deffd-106">Den angränsande aktiviteten förutsätter att mål-qubit kommer att återställas till 0.</span><span class="sxs-lookup"><span data-stu-id="deffd-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="deffd-107">Indata</span><span class="sxs-lookup"><span data-stu-id="deffd-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="deffd-108">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="deffd-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="deffd-109">Kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="deffd-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="deffd-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="deffd-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="deffd-111">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="deffd-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="deffd-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="deffd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

