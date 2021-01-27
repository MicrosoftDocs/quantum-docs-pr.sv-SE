---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841663"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="a882e-102">ApplyMultiplyControlledLowDepthAnd-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a882e-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="a882e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a882e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a882e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a882e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a882e-105">Implementerar en Toffoli-grind med flera regler, förutsatt att mål qubit initieras 0.</span><span class="sxs-lookup"><span data-stu-id="a882e-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="a882e-106">Den angränsande aktiviteten förutsätter att mål-qubit kommer att återställas till 0.</span><span class="sxs-lookup"><span data-stu-id="a882e-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="a882e-107">Kräver ett RZ djup på 1, medan antalet hjälp program qubits är exponentiellt i antalet qubits.</span><span class="sxs-lookup"><span data-stu-id="a882e-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a882e-108">Indata</span><span class="sxs-lookup"><span data-stu-id="a882e-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="a882e-109">kontroller: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a882e-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a882e-110">Kontroll qubits</span><span class="sxs-lookup"><span data-stu-id="a882e-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a882e-111">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a882e-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a882e-112">Mål qubit</span><span class="sxs-lookup"><span data-stu-id="a882e-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="a882e-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a882e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

