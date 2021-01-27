---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825948"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="648a7-102">InjectPi4YRotation-åtgärd</span><span class="sxs-lookup"><span data-stu-id="648a7-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="648a7-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="648a7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="648a7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="648a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="648a7-105">Roterar en enskild qubit från π/4 om Y-axeln.</span><span class="sxs-lookup"><span data-stu-id="648a7-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="648a7-106">Description</span><span class="sxs-lookup"><span data-stu-id="648a7-106">Description</span></span>

<span data-ttu-id="648a7-107">Utför en π/4-rotation om `Y` .</span><span class="sxs-lookup"><span data-stu-id="648a7-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="648a7-108">Rotationen utförs genom att konsumera ett magiskt tillstånd; det vill säga en kopia av tillstånd $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="648a7-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="648a7-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="648a7-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="648a7-110">Indata</span><span class="sxs-lookup"><span data-stu-id="648a7-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="648a7-111">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="648a7-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="648a7-112">En qubit som ska roteras om $Y $ med $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="648a7-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="648a7-113">Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="648a7-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="648a7-114">En qubit inlednings vis i Magic State.</span><span class="sxs-lookup"><span data-stu-id="648a7-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="648a7-115">Följande åtgärds program `magic` returneras till $ \ket {0} $-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="648a7-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="648a7-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="648a7-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="648a7-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="648a7-117">Remarks</span></span>

<span data-ttu-id="648a7-118">Följande är likvärdiga:</span><span class="sxs-lookup"><span data-stu-id="648a7-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="648a7-119">och</span><span class="sxs-lookup"><span data-stu-id="648a7-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="648a7-120">Den här åtgärden stöder `Adjoint` Functor, vilket innebär att samma magiska tillstånd förbrukas, men påverkan på data qubit är en $-\ PI/4 $ $Y $-rotation.</span><span class="sxs-lookup"><span data-stu-id="648a7-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>