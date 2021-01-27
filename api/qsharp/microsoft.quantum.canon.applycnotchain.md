---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841965"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="7024e-102">ApplyCNOTChain-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7024e-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="7024e-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7024e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7024e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7024e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7024e-105">Beräknar pariteten för ett register över qubits på plats.</span><span class="sxs-lookup"><span data-stu-id="7024e-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7024e-106">Description</span><span class="sxs-lookup"><span data-stu-id="7024e-106">Description</span></span>

<span data-ttu-id="7024e-107">Den här åtgärden transformerar statusen för indatamängden som $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="7024e-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="7024e-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7024e-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7024e-109">Indata</span><span class="sxs-lookup"><span data-stu-id="7024e-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="7024e-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7024e-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7024e-111">Matris med qubits vars paritet ska beräknas och lagras.</span><span class="sxs-lookup"><span data-stu-id="7024e-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7024e-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7024e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

