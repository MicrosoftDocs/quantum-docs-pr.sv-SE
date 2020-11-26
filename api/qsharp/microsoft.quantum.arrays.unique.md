---
uid: Microsoft.Quantum.Arrays.Unique
title: Unik funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220016"
---
# <a name="unique-function"></a>Unik funktion

Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en ny matris som inte har lika intilliggande element.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Beskrivning

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

## <a name="remarks"></a>Kommentarer

Om det finns flera element som är identiska men inte bredvid varandra, kommer det att finnas flera förekomster i den utgående matrisen.  Använd den här funktionen tillsammans med `Sorted` för att hämta en matris med övergripande unika element.