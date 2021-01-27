---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829280"
---
# <a name="dumpoperation-operation"></a>DumpOperation-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en åtgärd visas diagnostiken för den åtgärd som görs tillgängliga av det aktuella körnings målet.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som den aktuella åtgärden agerar på.


### <a name="op--qubit--unit--is-adj"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just

Den åtgärd som ska diagnostiseras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exempel

När körs på Quantum Simulator-målet kommer följande fragment att resultera i matrisen $ $ \begin{Aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 1 & 0 & 0) \end{Aligned}.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>Kommentarer

Anrop av den här åtgärden har ingen underrättsering i Q #. Den exakta diagnostik som visas, om det finns, är beroende av det aktuella körnings målet och redigerings miljön.
När den används i den fullständiga Quantum-simulatorn visas till exempel en enhetlig matris som används som representerar `op` .

Observera att när den körs på simulatorer som beviljar en global fas tvetydighet (t. ex.: full tillstånds simulatorn), kan returnerade representationer variera till en global fas.

På samma sätt kan sortering av matriser för rader och kolumner variera med de konventioner som används av varje simulator som stöder den här åtgärden.