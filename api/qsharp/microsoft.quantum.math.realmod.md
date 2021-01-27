---
uid: Microsoft.Quantum.Math.RealMod
title: Funktionen RealMod
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848351"
---
# <a name="realmod-function"></a>Funktionen RealMod

Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Beräknar modulen mellan två reella tal.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Indata

### <a name="value--double"></a>värde: [Double](xref:microsoft.quantum.lang-ref.double)

Ett reellt tal $x $ för att ta modulen.


### <a name="modulo--double"></a>modulo: [dubbel](xref:microsoft.quantum.lang-ref.double)

Ett reellt tal som ska ta modulen med $x $ med avseende på.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Det minsta värde som ska returneras av den här funktionen.



## <a name="output--double"></a>Utdata: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="example"></a>Exempel

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Kommentarer

Den här funktionen beräknar den verkliga modulen genom att figursätta den verkliga linjen om enhets cirkeln och sedan hitta vinkeln på den enhets cirkel som motsvarar indatan.
`minValue`Inmatarna anger sedan i praktiken var du vill klippa ut enhets cirkeln.