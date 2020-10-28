---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727282"
---
# <a name="dumpoperation-operation"></a>DumpOperation-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


Med en åtgärd visas diagnostiken för den åtgärd som görs tillgängliga av det aktuella körnings målet.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som den aktuella åtgärden agerar på.


### <a name="op--qubit--unit-adj"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering

Den åtgärd som ska diagnostiseras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Anrop av den här åtgärden har ingen underrättsering i Q #. Den exakta diagnostik som visas, om det finns, är beroende av det aktuella körnings målet och redigerings miljön.
När den används i den fullständiga Quantum-simulatorn visas till exempel en enhetlig matris som används som representerar `op` .

Observera att när den körs på simulatorer som beviljar en global fas tvetydighet (t. ex.: full tillstånds simulatorn), kan returnerade representationer variera till en global fas.

På samma sätt kan sortering av matriser för rader och kolumner variera med de konventioner som används av varje simulator som stöder den här åtgärden.