---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209204"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="ea814-102">ApplyMultiplyControlledLowDepthAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ea814-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="ea814-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea814-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea814-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea814-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea814-105">Implementerar en Toffoli-grind med flera regler, förutsatt att mål qubit initieras 0.</span><span class="sxs-lookup"><span data-stu-id="ea814-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="ea814-106">Den angränsande aktiviteten förutsätter att mål-qubit kommer att återställas till 0.</span><span class="sxs-lookup"><span data-stu-id="ea814-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="ea814-107">Kräver ett RZ djup på 1, medan antalet hjälp program qubits är exponentiellt i antalet qubits.</span><span class="sxs-lookup"><span data-stu-id="ea814-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ea814-108">Indata</span><span class="sxs-lookup"><span data-stu-id="ea814-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="ea814-109">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea814-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ea814-110">Kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="ea814-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ea814-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea814-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea814-112">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="ea814-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea814-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea814-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

