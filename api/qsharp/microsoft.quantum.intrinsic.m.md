---
uid: Microsoft.Quantum.Intrinsic.M
title: M-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818876"
---
# <a name="m-operation"></a><span data-ttu-id="5f109-102">M-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5f109-102">M operation</span></span>

<span data-ttu-id="5f109-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5f109-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5f109-104">Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5f109-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5f109-105">Utför en mätning av en enskild qubit i Pauli-$Z $ bas.</span><span class="sxs-lookup"><span data-stu-id="5f109-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="5f109-106">Resultatet av utdata anges av distributionen \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="5f109-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="5f109-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5f109-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="5f109-108">Indata</span><span class="sxs-lookup"><span data-stu-id="5f109-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="5f109-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5f109-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5f109-110">Qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="5f109-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5f109-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="5f109-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5f109-112">`Zero` om $ + $1-eigenvalue observeras och `One` om $-$1-eigenvalue observeras.</span><span class="sxs-lookup"><span data-stu-id="5f109-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f109-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="5f109-113">Remarks</span></span>

<span data-ttu-id="5f109-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="5f109-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```