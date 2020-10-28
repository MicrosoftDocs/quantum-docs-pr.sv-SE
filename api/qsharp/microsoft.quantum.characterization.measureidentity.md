---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728185"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="29675-102">MeasureIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="29675-102">MeasureIdentity operation</span></span>

<span data-ttu-id="29675-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="29675-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="29675-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29675-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29675-105">Mäter identitets operatören på ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="29675-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="29675-106">Indata</span><span class="sxs-lookup"><span data-stu-id="29675-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="29675-107">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="29675-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="29675-108">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="29675-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="29675-109">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="29675-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="29675-110">Resultatvärdet `Zero` .</span><span class="sxs-lookup"><span data-stu-id="29675-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="29675-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="29675-111">Remarks</span></span>

<span data-ttu-id="29675-112">Eftersom $ \boldone $ endast har eigenvalue $1 $, och inte har ett negativt eigenvalue, returnerar den här åtgärden alltid `Zero` , som motsvarar eigenvalue $ + 1 = (-1) ^ 0 $, och orsakar ingen komprimering av status för `register` .</span><span class="sxs-lookup"><span data-stu-id="29675-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="29675-113">Den här åtgärden är inte användbar, men är användbar i samband med process-Tomography, eftersom den ger information om spårning av väntande processer i en Quantum-process.</span><span class="sxs-lookup"><span data-stu-id="29675-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="29675-114">I synnerhet bör en mål dator med förlust mått ersätta den här åtgärden med en faktisk mätning på $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="29675-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>