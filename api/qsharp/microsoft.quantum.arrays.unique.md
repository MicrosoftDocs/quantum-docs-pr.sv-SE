---
uid: Microsoft.Quantum.Arrays.Unique
title: Unik funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850910"
---
# <a name="unique-function"></a>Unik funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en ny matris som inte har lika intilliggande element.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Description

Funktionen returnerar en matris med element och en funktion för att testa likheten. den här funktionen returnerar en ny matris där den relativa ordningen på elementen behålls, men alla intilliggande element som är lika med filtreras till bara ett enda element.

## <a name="input"></a>Indata

### <a name="equal--tt---bool"></a>lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

En funktion som jämför två element som `a` anses vara lika med `b` om `equal(a, b)` är `true` .


### <a name="array--t"></a>matris: ' ' []

Matrisen som ska filtreras för unika element.



## <a name="output--t"></a>Utdata: ' t []

Matris utan lika intilliggande element.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen för varje element i `array` .

## <a name="example"></a>Exempel

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Kommentarer

Om det finns flera element som är identiska men inte bredvid varandra, kommer det att finnas flera förekomster i den utgående matrisen.  Använd den här funktionen tillsammans med `Sorted` för att hämta en matris med övergripande unika element.