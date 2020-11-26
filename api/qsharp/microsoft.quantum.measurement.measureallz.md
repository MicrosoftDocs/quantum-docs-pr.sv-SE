---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227088"
---
# <a name="measureallz-operation"></a><span data-ttu-id="11661-102">MeasureAllZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="11661-102">MeasureAllZ operation</span></span>

<span data-ttu-id="11661-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="11661-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="11661-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11661-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11661-105">I gemensamma fall åtgärdas ett register över qubits i Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="11661-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="11661-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="11661-106">Description</span></span>

<span data-ttu-id="11661-107">Mäter ett register över qubits i $Z \otimes Z \otimes \cdots \otimes Z $, som representerar pariteten för hela registreringen.</span><span class="sxs-lookup"><span data-stu-id="11661-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="11661-108">Indata</span><span class="sxs-lookup"><span data-stu-id="11661-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="11661-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="11661-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="11661-110">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="11661-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="11661-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="11661-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="11661-112">Resultatet av mätningen $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="11661-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>