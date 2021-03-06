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
# <a name="blochspherecoordinates-function"></a>Funktionen BlochSphereCoordinates

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar Bloch-sfär koordinaterna för ett enda qubit-tillstånd.

Med två komplexa tal $a 0, a1 $ som representerar qubit-läget, beräknar koordinaterna för Bloch-sfären så att $a 0 \ket {0} + a1 \ket {1} = r e ^ {IT} (e ^ {-i \phi/2}\cos{(\ theta/2)} \ket {0} + e ^ {i \phi/2}\sin{(\ theta/2)} \ket {1} ) $.

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>Indata

### <a name="a0--complexpolar"></a>a0: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Komplex koefficient för State $ \ket {0} $.


### <a name="a1--complexpolar"></a>a1: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Komplex koefficient för State $ \ket {1} $.



## <a name="output--complexpolardoubledouble"></a>Utdata: ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[dubbel](xref:microsoft.quantum.lang-ref.double),[dubbel](xref:microsoft.quantum.lang-ref.double))

En tupel som innehåller `(ComplexPolar(r, t), phi, theta)` .