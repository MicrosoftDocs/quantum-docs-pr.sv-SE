---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: Funktionen TableLookupRecovery
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726934"
---
# <a name="tablelookuprecovery-function"></a>Funktionen TableLookupRecovery

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


För en specifik tabell med Pauli-åtgärder på ett angivet register av qubits returnerar den här funktionen ett objekt av typen `RecoveryFn` som innehåller all information som behövs för att utföra en tabells öknings avkodning i förhållande till den aktuella matrisen med Pauli-åtgärder.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Indata

### <a name="table--pauli"></a>Tabell: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabell med Pauli-åtgärder som fungerar på en specifik qubit-registrering



## <a name="output--recoveryfn"></a>Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Ett objekt av typen `RecoveryFn` , t. ex. en karta `Syndrome -> Pauli[]` som associeras med en bestämd Syndrome-matris motsvarande Pauli korrigerings åtgärd.