---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: Funktionen EmptyArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846182"
---
# <a name="emptyarray-function"></a>Funktionen EmptyArray

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Returnerar den tomma matrisen av en specifik typ.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Utdata: ' TElein []

Den tomma matrisen.

## <a name="type-parameters"></a>Typparametrar

### <a name="telement"></a>"Teleteleering"

Typ av element i matrisen.

## <a name="example"></a>Exempel

```qsharp
let empty = EmptyArray<Int>();
```