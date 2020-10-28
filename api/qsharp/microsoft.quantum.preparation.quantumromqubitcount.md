---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Funktionen QuantumROMQubitCount
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732606"
---
# <a name="quantumromqubitcount-function"></a>Funktionen QuantumROMQubitCount

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paketfilerna [](https://nuget.org/packages/)


Returnerar det totala antalet qubits som måste allokeras till den åtgärd som returnerades av `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="ncoeffs--int"></a>nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)

Antalet koefficienter som anges i `QuantumROM` .



## <a name="output--intintint"></a>Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>Första parametern

En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.