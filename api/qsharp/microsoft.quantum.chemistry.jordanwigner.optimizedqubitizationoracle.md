---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: Funktionen OptimizedQubitizationOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: da569e8ddad575b1ba1bbc2081a6a948cb675d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837048"
---
# <a name="optimizedqubitizationoracle-function"></a>Funktionen OptimizedQubitizationOracle

Namnrymd: [Microsoft. Quantum. kemi. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Returnerar den optimerade Qubitization-åtgärden för T-count och de parametrar som krävs för att köra den.

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Indata

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian som beskrivs i `JordanWignerEncodingData` format.


### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Fel i steget för förberedelse av auxillary-tillstånd.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL))

En tupel där: `Int` är antalet allokerade qubits, `Double` är en-norm av Hamiltonian-koefficienter och åtgärden är den Quantum-funktion som skapats av Qubitization.