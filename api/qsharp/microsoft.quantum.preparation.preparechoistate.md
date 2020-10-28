---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733219"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState-åtgärd

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paketfilerna [](https://nuget.org/packages/)


Förbereder Choi – Jamiłkowski-tillstånd för en specifik åtgärd på den angivna referensen och mål registren.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Indata

### <a name="op--qubit--unit"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärd $ \Lambda $ vars Choi – Jamiłkowski State $J (\Lambda)/2 ^ N $ ska förberedas, där $N $ är antalet qubits som `op` fungerar.


### <a name="reference--qubit"></a>Referens: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register över qubits som startar i $ \ket{00\cdots 0} $ State som ska användas som referens för åtgärden `op` .


### <a name="target--qubit"></a>mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register över qubits inlednings vis i den $ \ket{00\cdots 0} $-status som ska `op` tillämpas.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Choi – Jamiłkowski State $J (\Lambda) $ av en Quantum-process definieras som $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ är *vectorization* för en matris $X $ i kolumn-Staplings konventionen. Lär dig en klassisk Beskrivning av det här tillståndet ger fullständig information om effekterna av $ \Lambda $ som fungerar på godtyckliga ingångs tillstånd och utgör grunden för *Quantum process tomography* .

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. preparation. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. preparation. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. preparation. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)