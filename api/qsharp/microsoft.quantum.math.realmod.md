---
uid: Microsoft.Quantum.Math.RealMod
title: Funktionen RealMod
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228261"
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



## <a name="remarks"></a>Kommentarer

Den här funktionen beräknar den verkliga modulen genom att figursätta den verkliga linjen om enhets cirkeln och sedan hitta vinkeln på den enhets cirkel som motsvarar indatan.
`minValue`Inmatarna anger sedan i praktiken var du vill klippa ut enhets cirkeln.