---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726517"
---
# <a name="measureallz-operation"></a><span data-ttu-id="5e426-102">MeasureAllZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5e426-102">MeasureAllZ operation</span></span>

<span data-ttu-id="5e426-103">Namnrymd: [Microsoft. Quantum. mått](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5e426-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5e426-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e426-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e426-105">I gemensamma fall åtgärdas ett register över qubits i Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="5e426-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="5e426-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5e426-106">Description</span></span>

<span data-ttu-id="5e426-107">Mäter ett register över qubits i $Z \otimes Z \otimes \cdots \otimes Z $, som representerar pariteten för hela registreringen.</span><span class="sxs-lookup"><span data-stu-id="5e426-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="5e426-108">Indata</span><span class="sxs-lookup"><span data-stu-id="5e426-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="5e426-109">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5e426-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5e426-110">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="5e426-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5e426-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="5e426-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5e426-112">Resultatet av mätningen $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="5e426-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>