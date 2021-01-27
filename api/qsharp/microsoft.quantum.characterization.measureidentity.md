---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851812"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="c63dd-102">MeasureIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c63dd-102">MeasureIdentity operation</span></span>

<span data-ttu-id="c63dd-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="c63dd-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="c63dd-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c63dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c63dd-105">Mäter identitets operatören på ett register över qubits.</span><span class="sxs-lookup"><span data-stu-id="c63dd-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="c63dd-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c63dd-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="c63dd-107">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c63dd-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c63dd-108">Registret som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="c63dd-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c63dd-109">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="c63dd-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c63dd-110">Resultatvärdet `Zero` .</span><span class="sxs-lookup"><span data-stu-id="c63dd-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c63dd-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c63dd-111">Remarks</span></span>

<span data-ttu-id="c63dd-112">Eftersom $ \boldone $ endast har eigenvalue $1 $, och inte har ett negativt eigenvalue, returnerar den här åtgärden alltid `Zero` , som motsvarar eigenvalue $ + 1 = (-1) ^ 0 $, och orsakar ingen komprimering av status för `register` .</span><span class="sxs-lookup"><span data-stu-id="c63dd-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="c63dd-113">Den här åtgärden är inte användbar, men är användbar i samband med process-Tomography, eftersom den ger information om spårning av väntande processer i en Quantum-process.</span><span class="sxs-lookup"><span data-stu-id="c63dd-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="c63dd-114">I synnerhet bör en mål dator med förlust mått ersätta den här åtgärden med en faktisk mätning på $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="c63dd-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>