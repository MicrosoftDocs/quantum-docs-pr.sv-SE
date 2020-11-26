---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216123"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="6a764-102">MeasureIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="6a764-102">MeasureIdentity operation</span></span>

<span data-ttu-id="6a764-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="6a764-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="6a764-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a764-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a764-105">Mäter identitets operatören på ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="6a764-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="6a764-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6a764-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="6a764-107">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6a764-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6a764-108">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="6a764-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6a764-109">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="6a764-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6a764-110">Resultatvärdet `Zero` .</span><span class="sxs-lookup"><span data-stu-id="6a764-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a764-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6a764-111">Remarks</span></span>

<span data-ttu-id="6a764-112">Eftersom $ \boldone $ endast har eigenvalue $1 $, och inte har ett negativt eigenvalue, returnerar den här åtgärden alltid `Zero` , som motsvarar eigenvalue $ + 1 = (-1) ^ 0 $, och orsakar ingen komprimering av status för `register` .</span><span class="sxs-lookup"><span data-stu-id="6a764-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="6a764-113">Den här åtgärden är inte användbar, men är användbar i samband med process-Tomography, eftersom den ger information om spårning av väntande processer i en Quantum-process.</span><span class="sxs-lookup"><span data-stu-id="6a764-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="6a764-114">I synnerhet bör en mål dator med förlust mått ersätta den här åtgärden med en faktisk mätning på $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="6a764-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>