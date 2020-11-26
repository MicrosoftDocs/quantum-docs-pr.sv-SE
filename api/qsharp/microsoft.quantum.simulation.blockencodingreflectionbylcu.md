---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: Funktionen BlockEncodingReflectionByLCU
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: e1247d961a7ebce798106c24c46d924dd6e6d347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229485"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="edab7-102">Funktionen BlockEncodingReflectionByLCU</span><span class="sxs-lookup"><span data-stu-id="edab7-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="edab7-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="edab7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="edab7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edab7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edab7-105">Kodar en operatör av intresse till en `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="edab7-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="edab7-106">Detta skapar en `BlockEncodingReflection` enhetlig $U = P\cdot V\cdot P ^ \dagger $ som kodar vissa operatorer $H = \ sum_ {j} | \ alpha_j | U_j $ intresse som är en linjär kombination av unitaries.</span><span class="sxs-lookup"><span data-stu-id="edab7-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="edab7-107">$P $ är vanligt vis en enhetlig tillstånds förberedelse som $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ och $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="edab7-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="edab7-108">Indata</span><span class="sxs-lookup"><span data-stu-id="edab7-108">Input</span></span>

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a><span data-ttu-id="edab7-109">statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="edab7-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edab7-110">En enhetlig $P $ som förbereder ett visst mål tillstånd.</span><span class="sxs-lookup"><span data-stu-id="edab7-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="edab7-111">väljare: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="edab7-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edab7-112">En enhetlig $V $ som kodar komponenten unitaries i $H $.</span><span class="sxs-lookup"><span data-stu-id="edab7-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="edab7-113">Utdata: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="edab7-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="edab7-114">En enhetlig $U $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och uppfyller $U ^ {-1} = U $.</span><span class="sxs-lookup"><span data-stu-id="edab7-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="edab7-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="edab7-115">Remarks</span></span>

<span data-ttu-id="edab7-116">Den här `BlockEncoding` implementeringen ger den egenskaperna för en `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="edab7-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="edab7-117">Se även</span><span class="sxs-lookup"><span data-stu-id="edab7-117">See Also</span></span>

- [<span data-ttu-id="edab7-118">Microsoft. Quantum. simulering. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="edab7-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="edab7-119">Microsoft. Quantum. simulering. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="edab7-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)