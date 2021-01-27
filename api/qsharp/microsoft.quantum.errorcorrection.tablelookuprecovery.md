---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: Funktionen TableLookupRecovery
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824401"
---
# <a name="tablelookuprecovery-function"></a>Funktionen TableLookupRecovery

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


För en specifik tabell med Pauli-åtgärder på ett angivet register av qubits returnerar den här funktionen ett objekt av typen `RecoveryFn` som innehåller all information som behövs för att utföra en tabells öknings avkodning i förhållande till den aktuella matrisen med Pauli-åtgärder.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Indata

### <a name="table--pauli"></a>Tabell: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabell med Pauli-åtgärder som fungerar på en specifik qubit-registrering



## <a name="output--recoveryfn"></a>Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Ett objekt av typen `RecoveryFn` , t. ex. en karta `Syndrome -> Pauli[]` som associeras med en bestämd Syndrome-matris motsvarande Pauli korrigerings åtgärd.