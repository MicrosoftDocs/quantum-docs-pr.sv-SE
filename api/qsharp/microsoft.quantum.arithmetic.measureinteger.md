---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843109"
---
# <a name="measureinteger-operation"></a>MeasureInteger-åtgärd

Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mäter innehållet i ett Quantum-register och konverterar det till ett heltal. Mätningen utförs med avseende på standard beräknings basen, d.v.s. eigenbasis `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Indata

### <a name="target--littleendian"></a>mål: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Ett Quantum-register i den lilla endian-kodningen.



## <a name="output--int"></a>Utdata: [int](xref:microsoft.quantum.lang-ref.int)

Ett osignerat heltal som innehåller det uppmätta värdet `target` .

## <a name="remarks"></a>Kommentarer

Den här åtgärden återställer ingångs register till $ \ket{00\cdots 0} $ State, vilket är lämpligt för att frigöra tillbaka till en måldator.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)