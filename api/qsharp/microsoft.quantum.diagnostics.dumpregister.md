---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: Funktionen DumpRegister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727273"
---
# <a name="dumpregister-function"></a>Funktionen DumpRegister

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paketfilerna [](https://nuget.org/packages/)


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