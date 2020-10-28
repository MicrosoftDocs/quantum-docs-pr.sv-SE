---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727033"
---
# <a name="knilldistill-operation"></a>KnillDistill-åtgärd

Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paketfilerna [](https://nuget.org/packages/)


Implementerar algoritmen för Knill Magic State.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Beskrivning

Med 15 ungefärliga kopior av ett Magic State $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} {8} {1} , $ $ får du en kopia med högre kvalitet.

## <a name="input"></a>Indata

### <a name="roughmagic--qubit"></a>roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ett register över femton qubits som innehåller ungefärliga kopior av ett magiskt tillstånd. Efter tillämpning av den här destillations processen `roughMagic[0]` kommer att innehålla en kopia av högre kvalitet och resten av registreringen återställs till $ \ket{00\cdots 0} $-tillstånd.



## <a name="output--bool"></a>Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)

Om `true` proceduren lyckades och den högre kvalitets kopian ska godkännas. Om `false` , proceduren misslyckades och status för registret ska anses vara odefinierad.

## <a name="remarks"></a>Kommentarer

Vi följer algoritmen för Knill.
Den nuvarande implementeringen är dock inte optimal, eftersom den använder för många qubits.
Magic-tillstånden injiceras i den här rutinen, i vilket fall finns det bättre protokoll.

## <a name="references"></a>Referenser

- [Knill](https://arxiv.org/abs/quant-ph/0402171)