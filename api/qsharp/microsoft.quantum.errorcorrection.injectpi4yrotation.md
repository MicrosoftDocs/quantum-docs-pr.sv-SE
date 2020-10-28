---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727051"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation-åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


Roterar en enskild qubit från π/4 om Y-axeln.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a>Beskrivning

Utför en π/4-rotation om `Y` .

Rotationen utförs genom att konsumera ett magiskt tillstånd; det vill säga en kopia av tillstånd $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Indata

### <a name="data--qubit"></a>data: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En qubit som ska roteras om $Y $ med $ \pi/$4.


### <a name="magic--qubit"></a>Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)

En qubit inlednings vis i Magic State. Följande åtgärds program `magic` returneras till $ \ket {0} $-tillstånd.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Följande är likvärdiga:

```qsharp
Ry(PI() / 4.0, data);
```

och

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Den här åtgärden stöder `Adjoint` Functor, vilket innebär att samma magiska tillstånd förbrukas, men påverkan på data qubit är en $-\ PI/4 $ $Y $-rotation.