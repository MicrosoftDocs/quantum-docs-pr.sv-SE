---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853443"
---
# <a name="assertqubit-operation"></a>AssertQubit-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Förutsätter att qubit `q` finns i den förväntade eigenstate för Pauli Z-operatorn.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Indata

### <a name="expected--__invalidresult__"></a>förväntat: __ogiltigt <Result>__

Vilket tillstånd som qubit förväntas vara i: `Zero` eller `One` .


### <a name="q--qubit"></a>f: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit vars tillstånd är kontrollerad.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> gör det möjligt att kontrollera godtyckliga qubit i stället för att bara $Z $ eigenstates.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)