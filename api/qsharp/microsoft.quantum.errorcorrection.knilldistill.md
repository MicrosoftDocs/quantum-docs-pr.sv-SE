---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853104"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="1fb55-102">KnillDistill-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1fb55-102">KnillDistill operation</span></span>

<span data-ttu-id="1fb55-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1fb55-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1fb55-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fb55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fb55-105">Implementerar algoritmen för Knill Magic State.</span><span class="sxs-lookup"><span data-stu-id="1fb55-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="1fb55-106">Description</span><span class="sxs-lookup"><span data-stu-id="1fb55-106">Description</span></span>

<span data-ttu-id="1fb55-107">Med 15 ungefärliga kopior av ett Magic State $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} {8} {1} , $ $ får du en kopia med högre kvalitet.</span><span class="sxs-lookup"><span data-stu-id="1fb55-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="1fb55-108">Indata</span><span class="sxs-lookup"><span data-stu-id="1fb55-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="1fb55-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1fb55-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1fb55-110">Ett register över femton qubits som innehåller ungefärliga kopior av ett magiskt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="1fb55-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="1fb55-111">Efter tillämpning av den här destillations processen `roughMagic[0]` kommer att innehålla en kopia av högre kvalitet och resten av registreringen återställs till $ \ket{00\cdots 0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="1fb55-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1fb55-112">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1fb55-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1fb55-113">Om `true` proceduren lyckades och den högre kvalitets kopian ska godkännas.</span><span class="sxs-lookup"><span data-stu-id="1fb55-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="1fb55-114">Om `false` , proceduren misslyckades och status för registret ska anses vara odefinierad.</span><span class="sxs-lookup"><span data-stu-id="1fb55-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fb55-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1fb55-115">Remarks</span></span>

<span data-ttu-id="1fb55-116">Vi följer algoritmen för Knill.</span><span class="sxs-lookup"><span data-stu-id="1fb55-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="1fb55-117">Den nuvarande implementeringen är dock inte optimal, eftersom den använder för många qubits.</span><span class="sxs-lookup"><span data-stu-id="1fb55-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="1fb55-118">Magic-tillstånden injiceras i den här rutinen, i vilket fall finns det bättre protokoll.</span><span class="sxs-lookup"><span data-stu-id="1fb55-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="1fb55-119">Referenser</span><span class="sxs-lookup"><span data-stu-id="1fb55-119">References</span></span>

- [<span data-ttu-id="1fb55-120">Knill</span><span class="sxs-lookup"><span data-stu-id="1fb55-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)