---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: Funktionen DumpRegister
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829220"
---
# <a name="dumpregister-function"></a>Funktionen DumpRegister

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dumpar den aktuella mål datorns status som är associerad med den angivna qubits.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="location--t"></a>plats: ' t '

Innehåller information om var tillståndets dump ska skapas.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Listan över qubits som ska rapporteras.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)

Inga.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte



## <a name="remarks"></a>Kommentarer

Med den här metoden kan du dumpa den information som är associerad med statusen för den aktuella qubits till en fil eller någon annan plats.
Den faktiska informationen som genereras och semantiken för `location` är specifika för varje måldator. Men att tillhandahålla en tom tupel som en plats ( `()` ) innebär vanligt vis att generera utdata till-konsolen.

För att den lokala fullständiga tillstånds simulatorn ska distribueras som en del av Quantum Development Kit förväntar den här metoden en sträng med sökvägen till en fil där den skriver den angivna qubits (d.v.s. våg funktionen i motsvarande del system) som en endimensionell matris med komplexa tal, där varje element representerar amplituderna för sannolikheten för att mäta motsvarande tillstånd.
Om den aktuella qubits är Entangled med vissa andra qubit och deras status inte kan avgränsas, så rapporterar den bara att qubits är Entangled.