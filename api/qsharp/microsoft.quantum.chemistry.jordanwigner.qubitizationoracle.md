---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: Funktionen QubitizationOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: 326bebfc1cfd839082732898167c20ecf105a266
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727690"
---
# <a name="qubitizationoracle-function"></a><span data-ttu-id="43b01-102">Funktionen QubitizationOracle</span><span class="sxs-lookup"><span data-stu-id="43b01-102">QubitizationOracle function</span></span>

<span data-ttu-id="43b01-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="43b01-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="43b01-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43b01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43b01-105">Returnerar Qubitization-åtgärden och de parametrar som krävs för att köra den.</span><span class="sxs-lookup"><span data-stu-id="43b01-105">Returns Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="43b01-106">Indata</span><span class="sxs-lookup"><span data-stu-id="43b01-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="43b01-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="43b01-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="43b01-108">Hamiltonian som beskrivs i `JordanWignerEncodingData` format.</span><span class="sxs-lookup"><span data-stu-id="43b01-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="43b01-109">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL))</span><span class="sxs-lookup"><span data-stu-id="43b01-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="43b01-110">En tupel där: `Int` är antalet allokerade qubits, `Double` är en-norm av Hamiltonian-koefficienter och åtgärden är den Quantum-funktion som skapats av Qubitization.</span><span class="sxs-lookup"><span data-stu-id="43b01-110">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>