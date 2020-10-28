---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: Funktionen TrotterStepOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727672"
---
# <a name="trottersteporacle-function"></a><span data-ttu-id="2a983-102">Funktionen TrotterStepOracle</span><span class="sxs-lookup"><span data-stu-id="2a983-102">TrotterStepOracle function</span></span>

<span data-ttu-id="2a983-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2a983-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2a983-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a983-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a983-105">Returnerar Trotter steg-åtgärd och de parametrar som krävs för att köra den.</span><span class="sxs-lookup"><span data-stu-id="2a983-105">Returns Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="2a983-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2a983-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="2a983-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="2a983-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="2a983-108">Hamiltonian som beskrivs i `JordanWignerEncodingData` format.</span><span class="sxs-lookup"><span data-stu-id="2a983-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="2a983-109">trotterStepSize: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a983-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a983-110">Steg storlek för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="2a983-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2a983-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a983-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a983-112">Ordning för Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="2a983-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="2a983-113">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL))</span><span class="sxs-lookup"><span data-stu-id="2a983-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="2a983-114">En tupel där: `Int` är antalet allokerade qubits, `Double` är `1.0/trotterStepSize` och åtgärden är Trotter-steget.</span><span class="sxs-lookup"><span data-stu-id="2a983-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>