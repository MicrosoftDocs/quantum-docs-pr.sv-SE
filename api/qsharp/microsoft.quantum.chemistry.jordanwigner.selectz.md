---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224725"
---
# <a name="selectz-operation"></a><span data-ttu-id="e1672-102">SelectZ-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e1672-102">SelectZ operation</span></span>

<span data-ttu-id="e1672-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e1672-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e1672-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e1672-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e1672-105">En enhetlig $U $ som tillämpar Pauli $Z $-grind på en qubits $p $ i ett index tillstånd $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="e1672-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="e1672-106">Det vill säga $ $ \begin{align} U\ket {p} \ ket {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e1672-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e1672-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e1672-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="e1672-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1672-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1672-109">I status $ \ket{p} $ i detta register bestäms den qubit som $Z $ tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e1672-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="e1672-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1672-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e1672-111">Registrera qubits som Pauli-operatörerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e1672-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1672-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1672-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

