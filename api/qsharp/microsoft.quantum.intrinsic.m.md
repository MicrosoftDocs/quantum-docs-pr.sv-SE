---
uid: Microsoft.Quantum.Intrinsic.M
title: M-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731395"
---
# <a name="m-operation"></a><span data-ttu-id="a3192-102">M-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a3192-102">M operation</span></span>

<span data-ttu-id="a3192-103">Namnrymd: [Microsoft. Quantum. inbyggt](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a3192-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a3192-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3192-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3192-105">Utför en mätning av en enskild qubit i Pauli-$Z $ bas.</span><span class="sxs-lookup"><span data-stu-id="a3192-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="a3192-106">Resultatet av utdata anges av distributionen \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span><span class="sxs-lookup"><span data-stu-id="a3192-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="a3192-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a3192-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="a3192-108">Indata</span><span class="sxs-lookup"><span data-stu-id="a3192-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="a3192-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3192-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3192-110">Qubit som ska mätas.</span><span class="sxs-lookup"><span data-stu-id="a3192-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a3192-111">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="a3192-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a3192-112">`Zero` om $ + $1-eigenvalue observeras och `One` om $-$1-eigenvalue observeras.</span><span class="sxs-lookup"><span data-stu-id="a3192-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3192-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a3192-113">Remarks</span></span>

<span data-ttu-id="a3192-114">Motsvarar:</span><span class="sxs-lookup"><span data-stu-id="a3192-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```