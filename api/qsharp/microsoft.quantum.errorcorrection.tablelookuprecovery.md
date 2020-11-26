---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: Funktionen TableLookupRecovery
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213675"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="9b84a-102">Funktionen TableLookupRecovery</span><span class="sxs-lookup"><span data-stu-id="9b84a-102">TableLookupRecovery function</span></span>

<span data-ttu-id="9b84a-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9b84a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9b84a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b84a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b84a-105">För en specifik tabell med Pauli-åtgärder på ett angivet register av qubits returnerar den här funktionen ett objekt av typen `RecoveryFn` som innehåller all information som behövs för att utföra en tabells öknings avkodning i förhållande till den aktuella matrisen med Pauli-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9b84a-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="9b84a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9b84a-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="9b84a-107">Tabell: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="9b84a-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="9b84a-108">Tabell med Pauli-åtgärder som fungerar på en specifik qubit-registrering</span><span class="sxs-lookup"><span data-stu-id="9b84a-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="9b84a-109">Utdata: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="9b84a-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="9b84a-110">Ett objekt av typen `RecoveryFn` , t. ex. en karta `Syndrome -> Pauli[]` som associeras med en bestämd Syndrome-matris motsvarande Pauli korrigerings åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9b84a-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>