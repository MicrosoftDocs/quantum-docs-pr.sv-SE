---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: Funktionen MultiplexerBruteForceFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad388bd34a778a7d774cd2a5118399b3db45267d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728584"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a><span data-ttu-id="b53b2-102">Funktionen MultiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="b53b2-102">MultiplexerBruteForceFromGenerator function</span></span>

<span data-ttu-id="b53b2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b53b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b53b2-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b53b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b53b2-105">Returnerar en multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar en enhetlig $V _j $ när den styrs av n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="b53b2-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="b53b2-106">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="b53b2-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b53b2-107">Indata</span><span class="sxs-lookup"><span data-stu-id="b53b2-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a><span data-ttu-id="b53b2-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL)</span><span class="sxs-lookup"><span data-stu-id="b53b2-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="b53b2-109">En tupel där det första elementet `Int` är antalet unitaries $N $, och det andra elementet `(Int -> ('T => () is Adj + Ctl))` är en funktion som tar ett heltal $j $ i $ [0, N-1] $ och utvärderar den enhetliga åtgärden $V _J $.</span><span class="sxs-lookup"><span data-stu-id="b53b2-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="b53b2-110">Utdata: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="b53b2-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b53b2-111">En multiplicering-kontrollerad enhetlig åtgärd $U $ som tillämpar unitaries som beskrivs i `unitaryGenerator` .</span><span class="sxs-lookup"><span data-stu-id="b53b2-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b53b2-112">Se även</span><span class="sxs-lookup"><span data-stu-id="b53b2-112">See Also</span></span>

- [<span data-ttu-id="b53b2-113">Microsoft. Quantum. Canon. MultiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="b53b2-113">Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)