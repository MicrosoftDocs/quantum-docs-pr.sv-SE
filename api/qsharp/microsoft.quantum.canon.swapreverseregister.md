---
uid: Microsoft.Quantum.Canon.SwapReverseRegister
title: SwapReverseRegister-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: SwapReverseRegister
qsharp.summary: Uses SWAP gates to Reversed the order of the qubits in a register.
ms.openlocfilehash: 9df62c4ef97a186b274a62bd493fa9e7bbb74fa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204988"
---
# <a name="swapreverseregister-operation"></a><span data-ttu-id="1f6a9-102">SwapReverseRegister-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1f6a9-102">SwapReverseRegister operation</span></span>

<span data-ttu-id="1f6a9-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f6a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f6a9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f6a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f6a9-105">Använder VÄXLINGs portar för att vända ordningen på qubits i en register.</span><span class="sxs-lookup"><span data-stu-id="1f6a9-105">Uses SWAP gates to Reversed the order of the qubits in a register.</span></span>

```qsharp
operation SwapReverseRegister (register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1f6a9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1f6a9-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="1f6a9-107">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f6a9-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f6a9-108">Den qubits ordning som ska återföras med hjälp av VÄXLINGs portar</span><span class="sxs-lookup"><span data-stu-id="1f6a9-108">The qubits order of which should be reversed using SWAP gates</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f6a9-109">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f6a9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

