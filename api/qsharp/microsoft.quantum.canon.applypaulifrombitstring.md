---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841579"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="d5c3c-102">ApplyPauliFromBitString-åtgärd</span><span class="sxs-lookup"><span data-stu-id="d5c3c-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="d5c3c-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5c3c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5c3c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5c3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5c3c-105">Använder en Pauli-operator för varje qubit i en matris om motsvarande bit i en boolesk matris matchar ett angivet inflöde.</span><span class="sxs-lookup"><span data-stu-id="d5c3c-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d5c3c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d5c3c-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="d5c3c-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="d5c3c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="d5c3c-108">Pauli-operatör som ska gälla för `qubits[idx]` var `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="d5c3c-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="d5c3c-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d5c3c-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d5c3c-110">Använd Pauli om biten är det här värdet</span><span class="sxs-lookup"><span data-stu-id="d5c3c-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="d5c3c-111">bitar: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d5c3c-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d5c3c-112">Booleskt register som anger vilka motsvarande qubit i som `qubits` ska användas</span><span class="sxs-lookup"><span data-stu-id="d5c3c-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d5c3c-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5c3c-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5c3c-114">Quantum register som den angivna Pauli-operatorn ska tillämpas på selektivt</span><span class="sxs-lookup"><span data-stu-id="d5c3c-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5c3c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5c3c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5c3c-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="d5c3c-116">Remarks</span></span>

<span data-ttu-id="d5c3c-117">Den booleska matrisen och Quantum-registret måste vara lika långa.</span><span class="sxs-lookup"><span data-stu-id="d5c3c-117">The Boolean array and the quantum register must be of equal length.</span></span>