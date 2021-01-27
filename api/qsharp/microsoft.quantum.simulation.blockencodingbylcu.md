---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: Funktionen BlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858163"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="dd092-102">Funktionen BlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="dd092-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="dd092-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dd092-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dd092-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd092-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd092-105">Kodar en operatör av intresse till en `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="dd092-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="dd092-106">Detta skapar en `BlockEncoding` enhetlig $U = P\cdot V\cdot P ^ \dagger $ som kodar vissa operatorer $H = \ sum_ {j} | \ alpha_j | U_j $ intresse som är en linjär kombination av unitaries.</span><span class="sxs-lookup"><span data-stu-id="dd092-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="dd092-107">$P $ är vanligt vis en enhetlig tillstånds förberedelse som $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ och $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="dd092-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="dd092-108">Indata</span><span class="sxs-lookup"><span data-stu-id="dd092-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="dd092-109">statePreparation: t => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="dd092-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dd092-110">En enhetlig $P $ som förbereder ett visst mål tillstånd.</span><span class="sxs-lookup"><span data-stu-id="dd092-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="dd092-111">väljare: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="dd092-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dd092-112">En enhetlig $V $ som kodar komponenten unitaries i $H $.</span><span class="sxs-lookup"><span data-stu-id="dd092-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="dd092-113">Utdata: (s) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL</span><span class="sxs-lookup"><span data-stu-id="dd092-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dd092-114">En enhetlig $U $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och uppfyller $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="dd092-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dd092-115">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="dd092-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd092-116">Inte</span><span class="sxs-lookup"><span data-stu-id="dd092-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="dd092-117">Formulär</span><span class="sxs-lookup"><span data-stu-id="dd092-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="dd092-118">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="dd092-118">Remarks</span></span>

<span data-ttu-id="dd092-119">Den här `BlockEncoding` implementeringen ger den egenskaperna för en `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="dd092-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd092-120">Se även</span><span class="sxs-lookup"><span data-stu-id="dd092-120">See Also</span></span>

- [<span data-ttu-id="dd092-121">Microsoft. Quantum. simulering. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="dd092-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="dd092-122">Microsoft. Quantum. simulering. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="dd092-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)