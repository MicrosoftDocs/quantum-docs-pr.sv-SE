---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: Funktionen BlochSphereCoordinates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 62643f64a6b829949fa708e300d9d262527dbb29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855905"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="1f7ae-102">Funktionen BlochSphereCoordinates</span><span class="sxs-lookup"><span data-stu-id="1f7ae-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="1f7ae-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1f7ae-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1f7ae-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f7ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f7ae-105">Beräknar Bloch-sfär koordinaterna för ett enda qubit-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="1f7ae-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="1f7ae-106">Med två komplexa tal $a 0, a1 $ som representerar qubit-läget, beräknar koordinaterna för Bloch-sfären så att $a 0 \ket {0} + a1 \ket {1} = r e ^ {IT} (e ^ {-i \phi/2}\cos{(\ theta/2)} \ket {0} + e ^ {i \phi/2}\sin{(\ theta/2)} \ket {1} ) $.</span><span class="sxs-lookup"><span data-stu-id="1f7ae-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="1f7ae-107">Indata</span><span class="sxs-lookup"><span data-stu-id="1f7ae-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="1f7ae-108">a0: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1f7ae-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1f7ae-109">Komplex koefficient för State $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="1f7ae-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="1f7ae-110">a1: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1f7ae-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1f7ae-111">Komplex koefficient för State $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="1f7ae-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="1f7ae-112">Utdata: ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[dubbel](xref:microsoft.quantum.lang-ref.double),[dubbel](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="1f7ae-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="1f7ae-113">En tupel som innehåller `(ComplexPolar(r, t), phi, theta)` .</span><span class="sxs-lookup"><span data-stu-id="1f7ae-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>