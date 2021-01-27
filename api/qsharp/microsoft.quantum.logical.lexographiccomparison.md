---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: Funktionen LexographicComparison
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814384"
---
# <a name="lexographiccomparison-function"></a>Funktionen LexographicComparison

Namnrymd: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Med en jämförelse funktion returnerar en ny funktion som lexographically jämför två matriser.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Indata

### <a name="elementcomparison--tt---bool"></a>elementComparison: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion som jämför två element `x` och `y` returnerar om `x` är mindre än eller lika med `y` .



## <a name="output--tt---bool"></a>Utdata: (inte [], inte [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion som jämför två matriser `xs` och `ys` returnerar om `xs` inträffar före eller lika med `ys` i lexographical-ordningen.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typ av element i de matriser som jämförs.

## <a name="remarks"></a>Kommentarer

Lexographic-jämförelsen mellan två matriser `xs` och `ys` definieras av följande procedur. Vi säger att två element `x` och `y` är likvärdiga om `elementComparison(x, y)` och `elementComparison(y, x)` båda är sanna.

- Båda matriserna jämförs element för element tills det första paret element som inte är likvärdigt. Matrisen som innehåller det element som inträffar först enligt `elementComparison` inträffar först i lexographical-ordning.
- Om inga icke-likvärdiga element hittas och en matris är längre än den andra, sägs att den kortare matrisen inträffar först.

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. arrayer. sorterat](xref:Microsoft.Quantum.Arrays.Sorted)