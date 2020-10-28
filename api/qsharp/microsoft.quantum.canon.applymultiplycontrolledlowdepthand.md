---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729463"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="dbdcd-102">ApplyMultiplyControlledLowDepthAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="dbdcd-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="dbdcd-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dbdcd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dbdcd-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbdcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbdcd-105">Implementerar en Toffoli-grind med flera regler, förutsatt att mål qubit initieras 0.</span><span class="sxs-lookup"><span data-stu-id="dbdcd-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="dbdcd-106">Den angränsande aktiviteten förutsätter att mål-qubit kommer att återställas till 0.</span><span class="sxs-lookup"><span data-stu-id="dbdcd-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="dbdcd-107">Kräver ett RZ djup på 1, medan antalet hjälp program qubits är exponentiellt i antalet qubits.</span><span class="sxs-lookup"><span data-stu-id="dbdcd-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="dbdcd-108">Indata</span><span class="sxs-lookup"><span data-stu-id="dbdcd-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="dbdcd-109">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dbdcd-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dbdcd-110">Kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="dbdcd-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dbdcd-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dbdcd-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dbdcd-112">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="dbdcd-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="dbdcd-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dbdcd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

