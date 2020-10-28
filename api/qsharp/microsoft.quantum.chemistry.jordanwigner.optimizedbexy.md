---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727732"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="e044c-102">OptimizedBEXY-åtgärd</span><span class="sxs-lookup"><span data-stu-id="e044c-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="e044c-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e044c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e044c-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e044c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e044c-105">En enhetlig $U $ som tillämpar Pauli-strängen på $ (X ^ {z + 1} \_ pY ^ {z} \_ p) z \_ {p-1}... Z_0 $ på qubits $0. p $ som villkoras på ett index $z \in \{ 0, 1 \} $ och $p $.</span><span class="sxs-lookup"><span data-stu-id="e044c-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="e044c-106">Det vill säga $ $ \begin{align} U\ket {z} \ ket {p} \ ket {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ pY ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e044c-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e044c-107">Indata</span><span class="sxs-lookup"><span data-stu-id="e044c-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="e044c-108">pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e044c-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e044c-109">När den här qubit är i tillstånd $ \ket {0} $ tillämpas $X $.</span><span class="sxs-lookup"><span data-stu-id="e044c-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="e044c-110">När det är i tillstånd $ \ket {1} $ tillämpas $Y $.</span><span class="sxs-lookup"><span data-stu-id="e044c-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="e044c-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e044c-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e044c-112">I status $ \ket{p} $ i detta register bestäms den qubit som $X $ eller $Y $ tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e044c-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="e044c-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e044c-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e044c-114">Registrera qubits som Pauli-operatörerna tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="e044c-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e044c-115">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e044c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e044c-116">Referenser</span><span class="sxs-lookup"><span data-stu-id="e044c-116">References</span></span>

- <span data-ttu-id="e044c-117">Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e044c-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>